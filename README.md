# Soil Water Stable Isotope Datasets for Cross-Domain Transfer Learning

This repository hosts the soil water stable isotope (δD and δ18O) datasets used in:

> Xu, J., Yu, Y., Yang, L., Wei, X., Wang, S., Liu, B., Shi, Y. Cross-prediction of soil water isotopes in data-scarce arid agricultural systems: integrating in-situ process analysis, transfer learning, and mechanistic interpretation.

The datasets cover two arid agricultural regions in northwestern China: the Shiyang River Basin (source domain, data-rich) and Hongqi Farm, Xinjiang (target domain, observation-limited).

## Dataset overview

### Source domain: Shiyang River Basin (SRB)

Farmland records extracted from the Global Soil Water Stable Isotope Dataset, collected at five farmland sites in the central plain of the SRB from September 2016 to August 2023. Depth stratification was harmonized to 20, 40, 60, and 100 cm to match the target-domain observational design. Total: 1,172 records.

| File | Depth | Records | Period | δD range (‰) | δ18O range (‰) |
|---|---|---|---|---|---|
| SRB_20cm.xlsx | 20 cm | 321 | 2016-09 to 2023-08 | -93.8 to 31.4 | -13.1 to 16.6 |
| SRB_40cm.xlsx | 40 cm | 324 | 2016-09 to 2023-08 | -94.1 to 12.7 | -14.0 to 14.5 |
| SRB_60cm.xlsx | 60 cm | 293 | 2016-09 to 2023-08 | -90.2 to 11.2 | -13.1 to 10.7 |
| SRB_100cm.xlsx | 100 cm | 234 | 2016-09 to 2023-08 | -93.1 to -1.5 | -12.7 to 10.5 |

### Target domain: Hongqi Farm (HQ), Xinjiang

Primary field data from a dedicated sampling campaign conducted from May to December 2024. The experiment comprised three adjacent plots with uniform moderate saline-alkali soil under three treatments: sorghum under flood irrigation (HQ1), sorghum under drip irrigation (HQ2), and cotton under drip irrigation (HQ3). Each depth file contains 13 records; for model evaluation, replicate records per sampling date and depth were averaged into 7 daily-mean samples.

| File | Depth | Records | Period | δD range (‰) | δ18O range (‰) |
|---|---|---|---|---|---|
| HQ_20cm.xlsx | 20 cm | 13 | 2024-06 to 2024-09 | -58.0 to -49.1 | -8.0 to -5.8 |
| HQ_40cm.xlsx | 40 cm | 13 | 2024-06 to 2024-09 | -79.5 to -56.4 | -12.9 to -7.1 |
| HQ_60cm.xlsx | 60 cm | 13 | 2024-06 to 2024-09 | -80.7 to -52.4 | -12.9 to -5.5 |
| HQ_100cm.xlsx | 100 cm | 13 | 2024-06 to 2024-09 | -78.7 to -51.9 | -11.7 to -6.7 |

## Variable description

| Column | Unit | Description |
|---|---|---|
| Sample Date | YYYY-MM-DD | Date of soil sampling |
| Longitude | °E | Sampling site longitude (WGS 1984) |
| Latitude | °N | Sampling site latitude (WGS 1984) |
| Sampling deepth | cm | Soil sampling depth (source-domain files only) |
| δD | ‰ | Hydrogen isotopic composition of soil water (VSMOW) |
| δ18O | ‰ | Oxygen isotopic composition of soil water (VSMOW) |
| NDVI | - | Normalized Difference Vegetation Index |
| Temperature | °C | Mean air temperature of the sampling month |
| Precipitation | mm | Monthly precipitation |
| DEM | m | Elevation |
| Soil moisture | m³ m⁻³ | Volumetric soil water content |
| Es | mm | Soil evaporation |
| PDSI | - | Palmer Drought Severity Index |
| HIP | ‰ | Hydrogen isotopic composition of precipitation input |
| OIP | ‰ | Oxygen isotopic composition of precipitation input |
| SAND | % | Sand content of the soil |
| SILT | % | Silt content of the soil |
| CLAY | % | Clay content of the soil |
| PH_WATER | - | Soil pH (water extraction) |

Dynamic features (NDVI, Temperature, Precipitation, Soil moisture, Es, PDSI) were extracted or spatially interpolated from gridded remote sensing and reanalysis products to the sampling site coordinates, and monthly values were aligned to the sampling month of each isotope observation. Static soil properties (SAND, SILT, CLAY, PH_WATER) represent intrinsic pedological characteristics of each site and depth.

## Measurement protocol

Soil water was extracted by a fully automated vacuum cryogenic extraction system (BJJL-2200, Beijing Jianling Technology Ltd., Beijing, China). Given the high salinity of samples in this arid region, extracted water was filtered through a 0.22 µm membrane with spectral calibration to correct for saline interference. Isotope ratios were measured with a liquid water isotope analyzer (TIWA-45-EP, Los Gatos Research, USA) using a six-injection protocol, with the first two injections discarded. All isotope values are reported relative to VSMOW.

## Usage notes

- Each Excel file contains a single sheet with one record per row.
- Missing values were removed during preprocessing; all listed records are complete.
- If you use these datasets, please cite the associated manuscript.
