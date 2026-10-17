# Phenotypic data dictionary

The application supports three types of protected crops, each with five phenotypic variables. The definitions below follow **Thesis Table 3.1 (printed page 37)**.

| Crop | Variable | Expected data type | Units / scale |
| --- | --- | --- | --- |
| Cucumber (*pepino*) | Stem diameter | Decimal, one decimal place | cm |
| Cucumber | Number of flowers | Positive integer | Count |
| Cucumber | Number of fruits | Positive integer | Count |
| Cucumber | Fruit weight | Decimal, one decimal place | g |
| Cucumber | Fruit length | Decimal, one decimal place | cm |
| Tomato (*tomate*) | Stem diameter | Decimal, one decimal place | cm |
| Tomato | Number of flowers | Positive integer | Count |
| Tomato | Number of fruits | Positive integer | Count |
| Tomato | Fruit weight | Decimal, one decimal place | g |
| Tomato | Fruit firmness | Ordinal value | 1 (very soft) to 10 (very firm) |
| Bell pepper (*pimiento*) | Stem diameter | Decimal, one decimal place | cm |
| Bell pepper | Number of flowers | Positive integer | Count |
| Bell pepper | Number of fruits | Positive integer | Count |
| Bell pepper | Fruit weight | Decimal, one decimal place | g |
| Bell pepper | Number of lobes | Positive integer | Count |

[Machine-readable CSV](../results/phenotypic-variables.csv)

## How data are managed

Records are created and updated through crop-specific UI forms and stored locally with timestamps and a synchronization status. The thesis describes the use of separate SQLite crop tables related to a central sessions/collections table; exact column-level SQL DDL is not contained in this repository.

The mobile application validates field requirements before saving and provides reading, editing, and deletion of stored observations.

## Data privacy

**No real observations or participant information are published in this repository.** This page documents the form schema only. The real thesis images should be reviewed before use in other research or published datasets.

**Thesis sources:** Table 3.1, Section 3.1 (printed pages 36–39); Sections 2.2.5 and 3.2.3 for persistence and association.
