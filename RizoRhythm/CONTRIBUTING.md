# GUÍA PARA CONTRIBUIR A RIZORHYTHM

## IMPORTANTE: LECTURA PREVIA OBLIGATORIA

Antes de considerar cualquier contribución, debes leer y comprender:
1.  El archivo `LEGAL_CLAIM.md` - Declara la propiedad intelectual exclusiva del concepto.
2.  El archivo `AUTHORS.md` - Establece la autoría principal y la política de contribuciones.
3.  Los archivos `LICENSE.md` y `LICENSE_DOCS.md` - Definen los términos bajo los cuales se comparte el trabajo.

Al contribuir, aceptas que tu contribución se regirá por estos documentos.

## 1. ALCANCE DE LAS CONTRIBUCIONES ACEPTADAS

Se aceptan **contribuciones limitadas y específicas** que no comprometan la propiedad intelectual del concepto central.

### 1.1. SE ACEPTAN (Ejemplos)
-   Corrección de errores tipográficos o gramaticales en la documentación.
-   Mejoras en la claridad de frases o párrafos existentes.
-   Traducciones de documentos a otros idiomas (que serán publicados como obras derivadas separadas).
-   Correcciones de bugs en el código de ejemplo o prototipo.
-   Adición de ejemplos de código que ilustren el uso de una librería externa con los sensores propuestos.

### 1.2. NO SE ACEPTAN SIN ACUERDO PREVIO POR ESCRITO (Ejemplos)
-   Modificaciones a la arquitectura central del sistema descrita en `docs/ARCHITECTURE.md`.
-   Propuestas que alteren sustancialmente el concepto de diagnóstico fitorrítmico.
-   Nuevos módulos principales o algoritmos que pudieran considerarse innovación central.
-   Cualquier contribución que pudiera generar dudas sobre la propiedad intelectual del proyecto.

## 2. PROCESO DE CONTRIBUCIÓN

### Paso 1: Discusión Previa (Obligatoria)
1.  Abre un **Issue** en el repositorio describiendo la contribución que deseas hacer.
2.  El mantenedor (**Enrique Aguayo H.**) evaluará si la contribución cae dentro del alcance aceptado.
3.  **No** trabajes en la contribución hasta que el mantenedor dé su aprobación explícita en el Issue.

### Paso 2: Trabajo en una Rama
1.  Si se aprueba, crea un **fork** del repositorio.
2.  Crea una **rama** con un nombre descriptivo (ej: `fix-typo-readme`, `add-sensor-example`).
3.  Realiza tus cambios **solo en los archivos aprobados**.

### Paso 3: Envío del Pull Request (PR)
1.  Envía un Pull Request desde tu rama hacia la rama `main` del repositorio original.
2.  En la descripción del PR, referencia el número del Issue de discusión.
3.  Describe claramente y de forma concisa los cambios realizados.

### Paso 4: Revisión y Aceptación
1.  El mantenedor revisará los cambios.
2.  Si se requieren modificaciones, se solicitarán en el PR.
3.  Una vez aprobado, el mantenedor fusionará (`merge`) los cambios.

## 3. ACUERDO LEGAL IMPLÍCITO AL CONTRIBUIR

Al enviar un Pull Request, confirmas que:

1.  Tu contribución es de tu propia autoría original, o tienes el derecho de licenciarla bajo los términos del proyecto.
2.  **Licencias tu contribución bajo los mismos términos del proyecto:**
    -   **Código/Firmware:** Bajo la `LICENSE.md` (Apache 2.0 con Restricción Comercial).
    -   **Documentación/Texto:** Bajo la `LICENSE_DOCS.md` (CC BY-NC-ND 4.0).
3.  **Reconoces y aceptas que tu contribución NO te otorga ningún derecho de propiedad intelectual, crédito de autoría o compensación económica** sobre el concepto RizoRhythm, su arquitectura o sus posibles desarrollos comerciales futuros.
4.  Aceptas que el mantenedor tiene el derecho exclusivo de aceptar, rechazar o modificar tu contribución sin obligación de explicación.

## 4. CONTRIBUCIONES SIGNIFICATIVAS Y ACUERDOS ADICIONALES

Para contribuciones que, a discreción del mantenedor, sean consideradas significativas (p.ej., un driver completo para un sensor crítico, un algoritmo de procesamiento de señal), se podrá requerir la firma de un **Acuerdo de Contribución de Código Abierto (Contributor Agreement)** que reafirmará los puntos de la sección 3 de manera explícita.

## 5. CONTACTO PARA DUDAS

Si tienes dudas sobre si tu contribución sería aceptable, o sobre los términos legales, contacta antes de realizar ningún trabajo a través del Issue tracker o en: **eaguayo@migst.cl**.

---

*Esta guía está diseñada para proteger la integridad conceptual y la propiedad intelectual de RizoRhythm mientras permite colaboraciones útiles y de buena fe. Su interpretación final corresponde al mantenedor del proyecto.*
