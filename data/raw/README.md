# Raw data for
# "What matters when? Temporal development of drivers and sources of nitrous oxide emissions in winter wheat"

This folder contains the **raw input data** used in the analyses for:

Turco F., Feigenwinter I., Allemann J., Hörtnagl L., Liebisch F., Buchmann N. (YEAR PLACEHOLDER).  
*What matters when? Temporal development of drivers and sources of nitrous oxide emissions in winter wheat.*  
*Journal Name PLACEHOLDER*.

All files are plain-text CSV files (comma-separated) with a header row.

---

## 1. Content of this folder

- `data_raw.zip` – Archive containing all raw data files listed below.  
  If you cloned the repository, unzip this file here so that the CSV files appear directly in `data/raw/`.

After unzipping, you should see the following files:

| File name                    | Description (short) |
|-----------------------------|---------------------|
| `fluxes.csv`                | Ecosystem fluxes measured by the eddy-covariance method (CO₂, H₂O, H, N₂O, CH₄), meteorological data, and detailed management information for the cropland site Oensingen (Switzerland), collected between 2021 and 2023. See also the dataset description at [https://doi.org/10.3929/ethz-c-000782868](https://doi.org/10.3929/ethz-c-000782868). |
| `meteo.csv`                 | Meteorological and environmental data (e.g. radiation, temperature, humidity, precipitation, soil water content) collected between 2021 and 2023 at the cropland site Oensingen. |
| `management.csv`            | Field management information (e.g. fertilization, tillage, sowing and harvest dates). |
| `Nmin.csv`                  | Soil mineral nitrogen measurements (NO₃⁻, NH₄⁺, and Nmin in kg N ha⁻¹) for 0–30, 30–60, and 60–90 cm soil depths based on soil sampling and subsequent lab analysis. |
| `PRS_nutrients.csv`         | Plant Root Simulator (PRS) nutrient data (time-integrated nutrient supply). |
| `crop_biomass.csv`          | Aboveground crop biomass measurements (dbm: dry biomass in kg ha⁻¹, fbm: fresh biomass in kg ha⁻¹, n_percent: N %, c_percent: C %, d15n: δ¹⁵N in ‰, d13c: δ¹³C in ‰, crop_n: N content in kg ha⁻¹, crop_c: C content in kg ha⁻¹, c_n_ratio: C/N ratio). |
| `LAI_measurements.csv`      | Leaf area index (LAI) measurements from field campaigns. |
| `LAI_model.csv`             | LAI time series interpolated with cubic splines (used only for visualization in Fig. 2 of the manuscript). |
| `n2o_isotopes.csv`          | N₂O isotopic composition (δ¹⁵N bulk, δ¹⁸O, site preference) and N₂O concentration at chamber closure and one hour after closure. |
| `soil_water_isotopes.csv`   | Isotopic composition (δ¹⁸O) of soil water at 0–10 cm soil depth. |
| `n2o_mixing_endmembers.csv` | Endmember information used for N₂O isotopic mixing/source partitioning derived from Yu et al. (2020). Standard deviations were suggested by Dominika Lewicka-Szczebak. |

For details on the exact variables, units, and measurement methods, please refer to the manuscript.  
If you need further information, you can contact the author(s).

---

## 2. How these data are used

The Jupyter notebooks in `../notebooks/` read these files directly from `data/raw/` and:

- perform data preprocessing,
- merge flux, meteorological, management, and ancillary measurements,
- derive variables used in the driver and source analyses,
- and generate the figures and tables included in the manuscript.

No manual modification of the raw CSV files is required to reproduce the analysis.

---

## 3. Citation

If you use these data, please cite the paper:

Turco F. et al. (YEAR PLACEHOLDER). *What matters when? Temporal development of drivers and sources of nitrous oxide emissions in winter wheat.* *Journal Name PLACEHOLDER*.
