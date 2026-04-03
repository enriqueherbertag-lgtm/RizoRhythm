# RizoRhythm: Diagnóstico agrícola por ritmo de plantas

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19394115.svg)](https://doi.org/10.5281/zenodo.19394115)
[![License](https://img.shields.io/badge/License-Proprietary-red.svg)](LICENSE)
[![EN](https://img.shields.io/badge/English-version-blue.svg)](./README.en.md)

**Un sistema que detecta estrés en plantas antes de que se vean afectadas, midiendo su movimiento y el suelo.**

## ¿Qué problema resuelve?

Los sistemas agrícolas actuales detectan el estrés cuando la planta ya está dañada (hojas amarillas, marchitamiento). Para entonces, ya se perdió producción.

**RizoRhythm detecta el estrés antes. Mucho antes.**

## ¿Qué hace?

Mide dos cosas al mismo tiempo:
- **Ritmo de la planta**: movimientos del tallo y hojas (acelerómetro MPU-6050).
- **Condiciones del suelo**: humedad y nitrógeno (sensores capacitivos + ISE).

Una IA en el edge (ESP32 o Raspberry Pi) correlaciona ambos flujos. Si el ritmo se desvía del patrón normal para las condiciones de suelo, alerta automáticamente.

## ¿Qué estrés detecta?

- **Estrés hídrico**: la planta modifica su ritmo antes de marchitarse.
- **Deficiencia de nitrógeno**: cambios en movimiento foliar antes de que amarillee.

## ¿Para quién es?

- Agricultores que quieren regar o fertilizar solo cuando es necesario.
- Empresas agrícolas que buscan reducir costos de insumos.
- Invernaderos automatizados.
- Investigación en fisiología vegetal.

## Estado actual

- Concepto definido.
- Especificaciones técnicas completas.
- Sensores seleccionados.
- Prototipo en desarrollo.
- Validación en cultivos reales pendiente.

## Licencia

Copyright © 2026 Enrique Aguayo. Todos los derechos reservados.

## Autor

Enrique Aguayo H. – Mackiber Labs
