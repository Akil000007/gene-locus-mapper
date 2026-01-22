# Gene Locus Position Extractor

## Overview

This repository contains a Python script that extracts **start and end genomic positions** for a selected list of genes. It matches gene locus names from one Excel file with their corresponding coordinates stored in another Excel file and generates a new Excel file with the results.

---

## Input Files

### 1. `X1.xlsx`

Contains the list of genes of interest.

**Required column:**

* `Locus`

Example:

| Locus    |
| -------- |
| gene_001 |
| gene_045 |

---

### 2. `X2.xlsx`

Contains gene coordinates.

**Required columns:**

* `Locus`
* `Start`
* `End`

Example:

| Locus    | Start | End  |
| -------- | ----- | ---- |
| gene_001 | 120   | 980  |
| gene_045 | 2100  | 2750 |

---

## Output File

### `X3_extracted_positions.xlsx`

Generated automatically.
Contains the loci from `X1.xlsx` with their matched start and end positions.

Example:

| Locus    | Start | End  |
| -------- | ----- | ---- |
| gene_001 | 120   | 980  |
| gene_045 | 2100  | 2750 |

Unmatched loci will have empty (`NaN`) values.

---

## Requirements

* Python 3.7 or higher
* pandas

Install pandas if needed:

```bash
pip install pandas
```

---

## How to Run

1. Place `X1.xlsx`, `X2.xlsx`, and the Python script in the same folder
2. Open a terminal in that folder
3. Run:

```bash
python extract_gene_positions.py
```

---

## How It Works

* Reads both Excel files
* Validates required columns
* Performs a **left join** on the `Locus` column
* Writes matched gene positions to a new Excel file
* Reports matched and unmatched genes

---

## Use Cases

* Gene annotation lookup
* Genome analysis pipelines
* Bioinformatics data cleaning
* Preparing coordinate tables for downstream analysis

---

## Notes

* Matching is **exact** (case-sensitive)
* One row per locus is expected in the coordinate file
* Designed for Excel-based genomic workflows

---

Just tell me.
