# Research context and objectives

## Academic context

- **Degree:** Automation Engineering (undergraduate diploma thesis).
- **Institution:** Universidad Central “Marta Abreu” de Las Villas, Faculty of Electrical Engineering, Department of Automatic Control.
- **Location:** Santa Clara, Cuba.
- **Date:** July 2025.
- **Author:** Miguel Garcés Vázquez.
- **Thesis supervisor:** Dr. Iván Santana Ching.
- **Thesis title (Spanish):** *Aplicación móvil para el registro de datos fenotípicos de cultivos protegidos*.

## Motivation

At protected-crop farms in Valle del Yabú, agrometeorological measurements were already available through sensor infrastructure, but phenotypic observations were manually collected and were irregular or incomplete. Those observations are needed for subsequent yield analysis and possible model training. Limited connectivity complicates the use of online-only forms.

The study therefore addresses a **data acquisition and continuity problem**, not the direct development of an agricultural prediction algorithm.

## Thesis objective

Develop a mobile application to collect phenotypic data from protected crops and support their later visualization and consultation for decision-making.

## Specific objectives (adapted from the thesis)

1. Review the literature on mobile data collection approaches.
2. Define the application's design requirements.
3. Design and implement its software architecture.
4. Verify the system's operation through technical tests.

## Methods and research contribution

The thesis uses a waterfall development approach, draws requirements from specialists and relevant literature, and documents a modular Flutter implementation. Key contributions are crop-specific manual data entry, local persistence, deferred ThingsBoard synchronization, and measurements of application/SQLite behavior.

## What the thesis does *not* demonstrate

- New predictive machine-learning models trained on the collected records.
- Autonomous irrigation actuation developed by this application.
- Statistical proof of improved agricultural yield.
- A publicly reproducible build from this documentation-only repository.

## Source provenance

Based on the 2025 thesis: Introduction and objectives (printed pages 1–5), Materials and Methods (25–35), Results and Discussion (36–59), and Conclusions (60).
