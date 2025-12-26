# ARQUITECTURA DEL SISTEMA RIZORHYTHM
## Documento Técnico Central - v1.0

> **PROPIEDAD INTELECTUAL PROTEGIDA**

> Este documento y la arquitectura que describe son propiedad intelectual de Enrique Aguayo H.
> Se comparten bajo licencia CC BY-NC-ND 4.0 únicamente para fines de investigación y estudio.

> **Cualquier uso comercial requiere acuerdo de licencia por escrito.**

## 1. Visión General y Principio de Operación

RizoRhythm es un marco para un **sistema de diagnóstico agrícola en lazo cerrado**. Su premisa fundamental es que el estrés en las plantas (hídrico, nutricional, patológico) se manifiesta primero en la **alteración de sus ritmos mecánicos ultralentos** (movimientos de nutación, pulsación foliar) antes de ser visible en hojas o tallos.

El sistema opera en tres pasos cíclicos:

1.  **Sensado Concurrente:** Mide variables de suelo (humedad, N) y el ritmo mecánico de la planta.

2.  **Diagnóstico Contextual:** Correlaciona ambas fuentes de datos para identificar el tipo y gravedad del estrés.

3.  **Acción Adaptativa y Retroalimentación:** Sugiere o ejecuta una intervención (ej: riego) y monitorea la recuperación del ritmo para validar su eficacia.

## 2. Arquitectura de Tres Capas

### Capa 1: Sensado de Suelo (Rizósfera)
**Objetivo:** Medir las *causas potenciales* del estrés.
-   **Sensor de Humedad Volumétrica:** Sonda capacitiva para medir el agua disponible en la zona radical.

-   **Sensor de Nitrógeno/Nitrato:** Electrodo iónico-selectivo o sensor óptico para estimar disponibilidad de N.

-   **Características:** Sensores enterrados, de bajo costo y bajo consumo. La data se transmite de forma inalámbrica.

### Capa 2: Sensado de Ritmo Fitorrítmico (Planta)
**Objetivo:** Medir la *respuesta sintomática* de la planta al estrés.
-   **Sensor Principal:** Acelerómetro MEMS (ej: MPU6050) de ultra baja potencia, acoplado de forma no invasiva al tallo principal o a una hoja joven.
-   **Métrica Principal:** Se procesa la señal para extraer la **frecuencia dominante** y la **amplitud** de los movimientos en ventanas de tiempo (ej: 15-90 minutos).
-   **Alternativa No Invasiva:** Cámara de eventos (*event camera*) o técnica de visión por computadora para capturar el movimiento sin contacto.

### Capa 3: Unidad de Procesamiento y Diagnóstico (Edge/IA)

**Objetivo:** Integrar los datos, diagnosticar y decidir.
-   **Hardware:** Microcontrolador (ESP32) o Single-Board Computer (Raspberry Pi) en el borde del campo.

-   **Lógica de Diagnóstico:**
    1.  Establece una **línea base** del ritmo normal de esa planta en sus condiciones actuales de suelo.
    2.  Detecta **desviaciones significativas** del ritmo.
    3.  **Correlaciona** la desviación con los datos de suelo:
        -   Ritmo lento + Humedad baja → Probable estrés hídrico.
        -   Ritmo lento + N bajo → Probable deficiencia nutricional.
        -   Ritmo errático + Humedad/N normales → Posible estrés biótico (patógeno).

-   **Salida:** Comando de actuación (ej: activar válvula de riego para la planta #X) o alerta para el agricultor.

## 3. Flujo de Datos y Comunicaciones


[Sensor Suelo] --(LoRa/Bluetooth)--> [Unidad Edge] <--(Cable/ADC)-- [Sensor Ritmo]
| |
| |
`---------> [Fusión de Datos & IA] <-------'
|
v
[Diagnóstico: "Estrés Hídrico Leve en Planta #7"]
|
v
[Actuador: Riego Localizado] OR [Alerta: App/ Dashboard]


-   **Comunicaciones Inalámbricas:** Se priorizan protocolos de largo alcance y bajo consumo (LoRaWAN) para sensores de suelo y ritmo.

-   **Procesamiento en el Edge:** La diagnosis ocurre localmente, sin necesidad de conectividad a internet constante, lo que reduce latencia y costos.

## 4. Especificaciones Técnicas Preliminares (Objetivo)

| Parámetro | Especificación Objetivo | Notas |
| :--- | :--- | :--- |
| **Resolución Temporal Ritmo** | 1 muestra/minuto | Suficiente para movimientos ultralentos. |

| **Rango Frecuencia Ritmo** | 0.1 mHz - 10 mHz | (Ciclos cada ~15 min a ~2.5 horas). |

| **Precisión Humedad Suelo** | ±3% | En rango de 0-100% HR. |

| **Autonomía Energética Nodos** | > 6 meses (campo) | Con baterías y/o micro-paneles solares. |

| **Latencia Diagnóstico** | < 5 minutos | Desde la detección de anomalía hasta la alerta. |

| **Costo Objetivo por Nodo Sensor** | < USD $50 | Para componentes en escala. |

## 5. Componentes Críticos y Desafíos Técnicos

### 5.1. Sensado de Ritmo
-   **Desafío:** Aislar la señal biológica del ruido (viento, vibraciones ambientales).

-   **Estrategia:** Uso de filtros digitales (pasa-bajos) y análisis en el dominio de la frecuencia (FFT).

### 5.2. Correlación Suelo-Ritmo
-   **Desafío:** Crear modelos de "ritmo esperado" para diferentes especies y estados fenológicos.

-   **Estrategia:** Aprendizaje de máquina supervisado inicial, con ajuste continuo (*online learning*) para adaptarse a la parcela específica.

### 5.3. Robustez en Campo
-   **Desafío:** Proteger electrónica de humedad, polvo, insectos y temperaturas extremas.
-   **Estrategia:** Encapsulados IP67, uso de materiales resistentes a UV, y lógica de *watchdog* para recuperación automática de fallos.

## 6. Hoja de Ruta de Desarrollo Técnico (Propuesta)

1.  **Fase Alfa (Laboratorio):** Validar la hipótesis del ritmo. Usar acelerómetros comerciales y plantas en maceta bajo estrés controlado. Generar el primer conjunto de datos.

2.  **Fase Beta (Invernadero):** Integrar un nodo sensor de suelo+ritmo. Desarrollar el algoritmo básico de correlación. Pruebas con cultivos reales en ambiente semi-controlado.

3.  **Fase Piloto (Campo):** Desplegar una red de 5-10 nodos en una parcela real. Testear comunicaciones, durabilidad y utilidad del diagnóstico.

4.  **Fase Producto:** Refinar diseño para fabricación, buscar certificaciones y desarrollar la interfaz de usuario final.

---

**Documento v1.0 - Diciembre 2024** 
**Autor y Propietario Intelectual:** Enrique Aguayo H. (ORCID: 0009-0004-4615-6825) 
**Licencia para este documento:** CC BY-NC-ND 4.0 (Ver `../LICENSE_DOCS.md`).

