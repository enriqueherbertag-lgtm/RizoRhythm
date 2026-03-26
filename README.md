# RizoRhythm: Sistema de Diagnóstico Fitorrítmico Adaptativo

**Sistema de diagnóstico agrícola basado en ritmos fitomecánicos y sensado de suelo, con IA en el edge.**

RizoRhythm correlaciona ritmos mecánicos de las plantas (fitomecánica) con variables de suelo (humedad, nitrógeno) para detectar estrés de forma proactiva y adaptativa.

---

## Problema que Resuelve

- **Diagnóstico reactivo:** Los sistemas actuales detectan estrés cuando la planta ya está afectada.
- **Sensado aislado:** La humedad o nutrientes se miden sin contexto del estado mecánico de la planta.
- **Alta complejidad:** Soluciones agrícolas de precisión requieren equipos costosos y conectividad constante.

**RizoRhythm permite diagnosticar estrés antes de que se manifieste visiblemente, correlacionando ritmo de la planta con condiciones de suelo.**

---

## Arquitectura en Tres Capas

| Capa | Función | Especificación |
|------|---------|----------------|
| **1. Sensado de Suelo** | Mide humedad y nitrógeno en la rizósfera | Sensores capacitivos + electrodos ISE, muestreo cada 15–60 min |
| **2. Sensado de Ritmo** | Mide movimientos fitomecánicos (tallo, hojas) | Acelerómetro (MPU-6050), muestreo 10–100 Hz |
| **3. IA Contextual** | Diagnóstico y sugerencia de acción en el edge | Modelo liviano (Random Forest / TinyML) en ESP32 o Raspberry Pi |

---

## Principio de Operación


[Sensor de suelo] ──┐
├── [IA en el edge] ──→ [Diagnóstico] ──→ [Acción (riego, alerta)]
[Sensor de ritmo] ──┘



El sistema correlaciona:
- **Ritmo de la planta:** Patrones de movimiento del tallo/hojas (crecimiento, respuesta a luz, estrés hídrico)
- **Condiciones de suelo:** Humedad, nitrógeno, temperatura

**Detecta estrés cuando el ritmo se desvía de su patrón normal para condiciones de suelo conocidas.**

---

## Especificaciones Técnicas

### Sensado de Suelo

| Parámetro | Valor |
|-----------|-------|
| Humedad | Rango 0–100%, precisión ±3% |
| Nitrógeno | Rango 0–500 ppm, precisión ±10% |
| Frecuencia de muestreo | 15–60 min (configurable) |

### Sensado de Ritmo

| Parámetro | Valor |
|-----------|-------|
| Sensor | Acelerómetro MPU-6050 (3 ejes) |
| Rango | ±2g / ±4g / ±8g (configurable) |
| Frecuencia de muestreo | 10–100 Hz |
| Resolución | 16 bits por eje |

### Procesamiento (IA en el edge)

| Parámetro | Valor |
|-----------|-------|
| Plataforma | ESP32 (Bajo costo) / Raspberry Pi (Mayor capacidad) |
| Modelo | Random Forest / TinyML (TensorFlow Lite) |
| Entrenamiento | Patrones de ritmo vs condiciones de suelo |
| Salida | Diagnóstico (estrés hídrico, deficiencia de nitrógeno, normal) + acción sugerida |

---

## Estado actual

✅ Concepto arquitectónico definido  
✅ Especificaciones técnicas preliminares  
✅ Selección de sensores validada  
🔲 Prototipo de hardware integrado  
🔲 Recolección de datos para entrenamiento  
🔲 Modelo de IA entrenado  
🔲 Validación en cultivos reales

---

## Estructura del repositorio


RizoRhythm/
├── README.md
├── LICENSE.md
├── LICENSE_DOCS.md
├── CHANGELOG.md
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── SECURITY.md
├── AUTHORS.md
├── LEGAL_CLAIM.md
├── docs/ # Documentación técnica
├── firmware/ # Código para sensores y procesamiento
├── hardware/ # Diseños de PCB, esquemáticos
├── simulations/ # Modelos de crecimiento y estrés
└── media/ # Gráficos, diagrama



---

## Próximos pasos

1. **Prototipo hardware** — Integrar sensores de suelo y acelerómetro en una placa ESP32.
2. **Recolección de datos** — Registrar ritmos de plantas bajo distintas condiciones de suelo.
3. **Entrenamiento de modelo** — Entrenar IA para clasificar estrés.
4. **Validación en campo** — Probar en cultivos reales (ej. tomate, maíz).

---

## Proyectos relacionados

- **OsteoFlux** — sistema de intervención ósea basado en resonancia  
  [Repositorio](https://github.com/enriqueherbertag-lgtm/osteoflux)
- **Resonador-432** — dispositivo médico de resonancia dual  
  [Repositorio](https://github.com/enriqueherbertag-lgtm/Resonador-432)
- **CORPUS** — sistema corporal artificial para IA  
  [Repositorio](https://github.com/enriqueherbertag-lgtm/Corpus)

---

## Licencia

**Código/Firmware:** Apache 2.0 con restricción de uso comercial.  
**Documentación/Diseños:** Creative Commons BY-NC-ND 4.0 (Atribución-NoComercial-SinDerivadas).

*Este es un framework base open-source. El que quiera más precisión, menor latencia o features avanzadas… que lo modifique y contribuya.*

---

## Autor

**Enrique Aguayo H.**  
Investigador independiente, Mackiber Labs  
Contacto: eaguayo@migst.cl  
ORCID: 0009-0004-4615-6825  
GitHub: [@enriqueherbertag-lgtm](https://github.com/enriqueherbertag-lgtm)








