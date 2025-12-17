# Code and data for: "What matters when? Temporal development of drivers and sources of nitrous oxide emissions in winter wheat"

This repository contains the code and data used in the analysis for:

> Turco F., Feigenwinter I., Allemann J., Hörtnagl L., Liebisch F., Buchmann N. (YEAR PLACEHOLDER).  
> What matters when? Temporal development of drivers and sources of nitrous oxide emissions in winter wheat. *Journal Name PLACEHOLDER*.

---

## Repository structure

- `notebooks/` – Jupyter notebooks used for all analyses and to generate figures and tables.
- `data/raw/` – Input data (as used in the paper).  
  All raw data are stored in a single archive: `data/raw/data_raw.zip`.  
  See `data/raw/README.md` for details on file contents.
- `data/processed/` – Intermediate data created by the notebooks.
- `figures/` – Output figures corresponding to the manuscript (and additional diagnostic figures).
- `environment.yml` – Conda environment file to reproduce the software setup.

---

## Software environment

Create and activate the conda environment:

```bash
conda env create -f environment.yml
conda activate n2o-paper-env
