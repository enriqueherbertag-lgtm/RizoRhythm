# RizoRhythm: Plant-based agricultural diagnosis

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.19394115.svg)](https://doi.org/10.5281/zenodo.19394115)
[![License](https://img.shields.io/badge/License-Proprietary-red.svg)](LICENSE)
[![ES](https://img.shields.io/badge/Spanish-version-green.svg)](./README.md)

**A system that detects stress in plants before they show damage, by measuring their movement and soil conditions.**

## What problem does it solve?

Current agricultural systems detect stress when the plant is already damaged (yellow leaves, wilting). By then, production is already lost.

**RizoRhythm detects stress earlier. Much earlier.**

## What does it do?

It measures two things simultaneously:
- **Plant rhythm**: movement of stems and leaves (MPU-6050 accelerometer).
- **Soil conditions**: moisture and nitrogen (capacitive sensors + ISE).

An AI on the edge (ESP32 or Raspberry Pi) correlates both streams. If the rhythm deviates from the normal pattern for the soil conditions, it automatically alerts.

## What stress does it detect?

- **Water stress**: the plant changes its rhythm before wilting.
- **Nitrogen deficiency**: changes in leaf movement before yellowing.

## Who is it for?

- Farmers who want to water or fertilize only when needed.
- Agricultural companies looking to reduce input costs.
- Automated greenhouses.
- Plant physiology research.

## Current status

- Concept defined.
- Complete technical specifications.
- Sensors selected.
- Prototype in development.
- Field validation pending.

## License

Copyright © 2026 Enrique Aguayo. All rights reserved.

## Author

Enrique Aguayo H. – Mackiber Labs
