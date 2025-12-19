# Notebooks for
# "What matters when? Temporal development of drivers and sources of nitrous oxide emissions in winter wheat"

This folder contains the Jupyter notebooks used to preprocess the data, run the analyses, and generate the figures and tables for the manuscript:

Turco F., Feigenwinter I., Allemann J., Hörtnagl L., Liebisch F., Buchmann N. (YEAR PLACEHOLDER).  
*What matters when? Temporal development of drivers and sources of nitrous oxide emissions in winter wheat.*  
*Journal Name PLACEHOLDER*.

All notebooks are designed to be run with the conda environment defined in `../environment.yml`.  
For general setup and data description, see the top-level `README.md` and `../data/raw/README.md`.

---

## Notebook naming and order

Notebooks with the prefix `DRIVERS` are related to ecosystem fluxes and driver analyses.  
Notebooks with the prefix `SOURCES` are related to stable isotope data and source partitioning.

Notebooks are numbered to indicate their recommended execution order:

- `00_*.ipynb` – data import and preprocessing  
- `10_*.ipynb` – main manuscript figures and tables  
- `20_*.ipynb` – supplementary figures

To fully reproduce the results, run the notebooks in ascending numerical order (starting from `00_...`).

---

## Notebooks description

- `DRIVERS_00_prep_data.ipynb`  
  - Reads raw data from `../data/raw/`.  
  - Processes and merges datasets (fluxes, meteorological and environmental data, LAI, management).  
  - Computes engineered features for management (e.g., days after management events, rolling sum of applied N).  
  - Aggregates data to 4-h, 8-h, and daily resolution.  
  - Computes lagged, rolling, and rate-of-change variants of selected variables.  
  - Writes `DRIVERS_dataset_*` files to `../data/processed/`.

- `DRIVERS_01_feature_selection.ipynb`  
  - Uses recursive feature elimination to define an importance ranking of features and identify the best feature set (with an option to instead use permutation importance for feature selection).  
  - Writes `best_features*` and `ranked_features*` to `../data/processed/`.

- `DRIVERS_02_hyperparameter_optimization.ipynb`  
  - Implements `GridSearchCV` to find the optimal set of XGBoost hyperparameters.  
  - Writes `best_hyperparameters*` to `../data/processed/`.

- `DRIVERS_10_shap_analysis.ipynb`  
  - Trains XGBoost models based on the selected feature set and optimized hyperparameters.  
  - Evaluates model performance in cross-validation.  
  - Trains the final model used for SHAP analysis.  
  - Computes SHAP values and related summaries.  
  - Generates figures based on the SHAP analysis.  
  - Saves all figure files to `../figures/`.

- `DRIVERS_10_env_fig.ipynb`  
  - Generates the figure showing precipitation, water-filled pore space (WFPS), soil temperature, and LAI.  
  - Saves the figure file to `../figures/`.

- `DRIVERS_10_fluxes_fig.ipynb`  
  - Generates the figure of gap-filled NEE, N₂O, and CH₄ fluxes.  
  - Saves the figure file to `../figures/`.

- `DRIVERS_10_emission_factor_ghg_budgets.ipynb`  
  - Converts fluxes to appropriate units for nitrogen and greenhouse gas (GHG) budgets.  
  - Calculates the N₂O emission factor.  
  - Calculates GHG budgets.

- `DRIVERS_10_GPP_vs_N2O.ipynb`  
  - Generates the figure of GPP vs. N₂O flux for different WFPS classes and computes related statistics.  
  - Saves the figure file to `../figures/`.

- `DRIVERS_10_Nmin_vs_N2O.ipynb`  
  - Accumulates N₂O fluxes over the periods corresponding to soil mineral N measurements (PRS probes or soil sampling).  
  - Generates the figure of NO₃⁻ (PRS) and Nmin vs. N₂O fluxes and computes related statistics.  
  - Saves the figure file to `../figures/`.

- `DRIVERS_20_cumGPP_vs_cropN.ipynb`  
  - Generates the supplementary figure of cumulative GPP vs. aboveground crop N in wheat.  
  - Saves the figure file to `../figures/`.

- `SOURCES_00_prep_data.ipynb`  
  - Reads raw data from `../data/raw/`.  
  - Processes and merges datasets (N₂O isotope data, soil water isotope data, and meteorological data).  
  - Computes the isotopic signature of emitted N₂O.  
  - Computes N₂O flux in nmol m⁻² s⁻¹.  
  - Writes `SOURCES_dataset*` to `../data/processed/`.

- `SOURCES_01_prep_inputs_FRAME.ipynb`  
  - Reads raw data from `../data/raw/` and `SOURCES_dataset*` from `../data/processed/`.  
  - Adjusts δ¹⁸O mixing endmember ranges reported by Yu et al. (2020) using the average δ¹⁸O of soil water.  
  - Processes and formats the data as required for the input files of the FRAME model (Lewicki et al., 2022).  
  - Writes `N2O_sources_FRAME`, `N2O_samples_FRAME`, and `N2O_fractionation_FRAME` to `../data/processed/`.

- `SOURCES_10_analysis.ipynb`  
  - Generates dual-isotope plots and violin plots of source fractions based on FRAME output.  
  - Saves all figure files to `../figures/`.

---

## Outputs

- **Processed data** are written to: `../data/processed/`  
- **Figures** are written to: `../figures/`

No manual editing of notebooks is required to reproduce the manuscript results; all paths assume the repository root as the working directory.

---

## Reproducibility notes

- All notebooks are intended to be run top-to-bottom without skipping cells.  
- Random processes (if any) are controlled via fixed random seeds within the notebooks.

If you encounter any issues when running the notebooks, please contact the author(s) or open an issue in the GitHub repository.
