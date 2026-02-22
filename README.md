# Transport Connectivity & Inequality

## Overview

This project builds a multi-level analytical framework that quantifies structural transport inequality across England and Wales.

Using the Department for Transport's national Connectivity Metric, launched in September 2025 as the first standardised measure of how easily people can reach jobs, healthcare, education, shopping, leisure, and social engagements, we link connectivity scores with deprivation, disability, rurality, and car ownership data to show where and why accessibility gaps exist.

The analysis runs across four nested geographic levels: Output Area (OA), Lower Super Output Area (LSOA), Local Authority District (LAD), and Region. The outputs are designed for councils, NHS Integrated Care Boards, and transport authorities to use directly.

---

## Core Impact Question

> **Which communities face the largest structural barriers to mobility, healthcare access, employment, and essential services, and what drives those barriers?**

---

## Research Questions

### Geographic Variation
1. How does transport connectivity vary across OA, LSOA, LAD, and Region?
2. What structural characteristics do the worst-performing 10% of areas share?

### The Deprivation Gap
3. What is the public transport accessibility gap between IMD Decile 1 (most deprived) and Decile 10 (least deprived)?
4. Does that gap widen or narrow when aggregated from LSOA to LAD or Region?

### Urban and Rural Structure
5. How much of poor connectivity is explained by rurality versus deprivation?
6. Which urban areas perform worse than expected given their population density?

### Healthcare Access and Disability
7. How many disabled people live in areas with low public transport access to healthcare?
8. Where are the largest mismatches between healthcare need and public transport provision?
9. Which NHS Integrated Care Board areas have the highest concentration of need-connectivity gaps?

### Car Dependency and Structural Exclusion
10. Where does high driving connectivity mask weak or absent public transport?
11. Which Local Authorities are structurally car-dependent, and what does that mean for households without a car?
12. In the most deprived LSOAs, what proportion of households have no car and also fall in the bottom 20% for public transport connectivity?

### Transport Deserts
13. How many people live in areas that CPRE would classify as transport deserts, and what is their demographic profile?
14. Are transport deserts concentrated in particular regions or spread across the country?

---

## Policy Context

This work connects to several live policy debates:

**DfT Connectivity Metric (September 2025)** is the Government's first nationally agreed connectivity score, now the official "national metric of connectivity" for planning decisions. The Transport Secretary has positioned it as central to housing delivery and sustainable transport planning.

**Bus Services Act 2025** received Royal Assent in October 2025, introducing new obligations on local authorities to consider socially necessary bus services, with measures on bus franchising and minimum connectivity standards.

**Transport Committee Report (August 2025)** found that 56% of small towns are in a "transport desert" (CPRE data), bus journeys outside London fell 21.7% between 2009 and 2024, and some young people in Somerset face three to four hours of daily travel to reach education.

**NHS Missed Appointments:** An estimated 10% of hospital outpatient appointments are missed due to transport problems. In 2021/22, nearly 7.5 million outpatient appointments were missed nationally. Missed appointments cost the NHS over £216 million per year.

**IPPR Transport Roundtables (August 2025)** documented disabled people taking three or four buses to access healthcare, young people in temporary accommodation making long costly journeys to school, and transport costs as a significant driver of poverty, particularly in the North East.

**Parliamentary Debate on Regional Transport Inequality (September 2025):** MPs described constituencies 40 miles from London where buses run 30 to 90 minutes apart and disappear entirely after 7 pm, while London has a bus stop every 400 metres.

Bus services have declined sharply: urban services down 48% and rural services down 52% since 2008, with some local authority areas losing up to 80% of routes.

---

## Data Sources

All datasets are open-access:

| Dataset | Detail | Geography | Source |
|---------|--------|-----------|--------|
| **DfT Connectivity Metric** | Overall, walking, cycling, public transport, and driving scores across six destination types (employment, healthcare, education, shopping, leisure, social) | OA, LSOA, LAD, Region | [GOV.UK](https://www.gov.uk/government/publications/transport-connectivity-metric) |
| **IMD 2025** | Index of Multiple Deprivation 2025: overall rank and decile | LSOA (England) | [GOV.UK](https://www.gov.uk/government/statistics/english-indices-of-deprivation-2025) |
| **Census 2021: Disability (TS038)** | Long-term health problems or disabilities: limited a lot, limited a little, not limited | Lower Tier Local Authority | [ONS](https://www.ons.gov.uk/datasets/TS038/editions/2021/versions/2) |
| **Census 2021: Car Availability (TS045)** | Households by number of cars or vans (0, 1, 2, 3+) | OA | [ONS](https://www.ons.gov.uk/datasets/TS045/editions/2021/versions/4) |
| **Census 2021: Sex by Age (RM121)** | Usual residents by sex and age — used to derive OA population totals | OA | [UK Data Service](https://statistics.ukdataservice.ac.uk/dataset/england-and-wales-census-2021-rm121-sex-by-age) |
| **ONS Rural-Urban Classification 2021** | Urban, Larger Rural, Smaller Rural with Relative Access (Nearer/Further), classified at LAD level | LAD | [data.gov.uk](https://www.data.gov.uk/dataset/8daa9988-f4e6-40e3-82df-58bb0ae947a3/rural-urban-classification-2021-of-local-authority-districts-2024-in-ew) |
| **ONS Geographic Lookup Tables** | LSOA (2021) to Electoral Ward (2024) to LAD (2024) best-fit lookup | LSOA → LAD | [ONS Open Geography Portal](https://geoportal.statistics.gov.uk/datasets/ons::lsoa-2021-to-electoral-ward-2024-to-lad-2024-best-fit-lookup-in-ew/about) |
| **Postcode to OA/LSOA/MSOA/LAD Lookup** | Best-fit mapping between UK postcodes and census geographies (Nov 2024) | Postcode → OA → LSOA → LAD | [ONS Open Geography Portal](https://geoportal.statistics.gov.uk/datasets/068ee476727d47a3a7a0d976d4343c59/about) |
| **ONS Population Estimates** | Mid-year population estimates by LAD — used to derive region-to-LAD hierarchy and population weights | LAD | [ONS](https://www.ons.gov.uk/peoplepopulationandcommunity/populationandmigration/populationestimates/datasets/estimatesofthepopulationforenglandandwales) |

### Data Notes

**DfT Connectivity Metric** uses Q4 2024/Q1 2025 data on 2021 OA boundaries. Public ODS tables cover OA, LSOA, LAD, and Region. The metric scores four transport modes (walking, cycling, public transport, driving) across six travel purposes on a 0 to 100 relative scale. The default "overall" score excludes driving and weights sustainable modes at roughly 52% public transport, 40% walking, 8% cycling.

**IMD 2025** covers England only and uses 2021 LSOA boundaries with 2024 LAD codes. The Welsh Index of Multiple Deprivation (WIMD) uses a different methodology and is not directly comparable. Wales LSOAs are included in connectivity analysis but IMD deprivation fields are England-only throughout.

**Census 2021 Disability (TS038)** is published at Lower Tier Local Authority level and classifies disability under the Equality Act 2010. It is joined to LSOAs via LAD code and treated as a LAD-level covariate in the master dataset.

**Census 2021 Car Availability (TS045)** is used at OA level with all five categories (no car, 1 car, 2 cars, 3+ cars, does not apply). OA-level data are aggregated to LSOA using the postcode best-fit lookup, enabling precise % no-car household estimates for each LSOA.

**ONS Population Estimates (Mid-2024)** are used for population-weighted aggregation from LSOA to LAD and Region, consistent with the DfT's own approach. The region-to-LAD hierarchy is parsed directly from the structured ONS file.

**Known limitations of the DfT metric:** assumes perfect timetable adherence (areas with unreliable services appear better connected than they are), does not model travel cost or affordability, and uses pre-COVID travel behaviour data from the National Travel Survey 2011 to 2020.

---

## Methodology

### 1. Geographic Harmonisation

All datasets are linked through ONS 2021 Census geography. LSOA is the primary unit of analysis because all data sources are available at this level. OA-level vehicle and population data are aggregated to LSOA using the Postcode to OA/LSOA/MSOA/LAD best-fit lookup (November 2024 edition). LAD and Regional aggregation uses population-weighted averages, consistent with the DfT's own approach. The region-to-LAD hierarchy is derived by parsing the structured ONS mid-year population estimates file.

### 2. Data Integration

At LSOA level, the master dataset merges:
- DfT connectivity scores (overall, by mode, by destination type)
- IMD 2025 rank and decile (England only)
- Census 2021 disability prevalence (TS038, joined at LAD level)
- Census 2021 car/van availability (TS045, aggregated OA → LSOA)
- ONS 2021 Rural-Urban Classification (LAD level)
- Mid-year population estimates (used as aggregation weights)

### 3. Derived Indices

| Index | Formula | What it captures |
|-------|---------|------------------|
| **Car Dependency Index** | `Driving Score − Public Transport Score` | Areas where driving far outperforms public transport, indicating structural car dependency |
| **Active Travel Gap** | `Mean(Walking, Cycling) − Driving` | Negative values flag areas where driving dominates and active travel provision is weak |
| **Need-Connectivity Mismatch** | `Disability Rate × (1 − Healthcare PT Score / 100)` | High-need areas with poor public transport access to health services |
| **Deprivation-Connectivity Gradient** | `Mean PT Score at IMD Decile 10 − Mean PT Score at Decile 1` | The size of the accessibility gap between the least and most deprived communities |

### 4. Classification Flags

Each LSOA is assigned a set of binary classification flags:

| Flag | Definition |
|------|-----------|
| `is_transport_desert` | Bottom national quintile for PT connectivity (≤ 20th percentile) |
| `is_car_dependent_poor_pt` | Driving in top 40% nationally and PT in bottom 40% |
| `is_structurally_excluded` | IMD Deciles 1–4 AND majority no-car households AND bottom 20% PT |

### 5. Inequality Gradient Analysis

For each region and nationally: calculate mean public transport connectivity by IMD decile, test for gradient linearity, and compute the Decile 10 minus Decile 1 gap. Gradients are also computed separately for each destination type (employment, healthcare, education, shopping, leisure) to identify where deprivation-related gaps are sharpest. This shows whether transport inequality tracks deprivation systematically or varies by regional context.

### 6. LAD Policy Ranking

Aggregate LSOA metrics to LAD using population-weighted means. Rank Local Authorities on four dimensions, each ranked 1 (worst) to n (best):
- Mean public transport connectivity
- Share of LSOAs in the national bottom 20%
- Car Dependency Index
- Need-Connectivity Mismatch score

A composite priority score is the simple mean of all four ranks. Rank 1 indicates the greatest need for policy intervention.

### 7. Limitations

- The DfT metric does not include travel cost, so affordability barriers are invisible
- Pre-COVID travel behaviour data may not reflect current commuting and travel patterns
- Timetable adherence assumptions mean areas with poor service reliability appear better connected than they are
- IMD 2025 covers England only; Wales LSOAs have no deprivation decile in the master dataset
- Disability data (TS038) is available at LTLA level only and is applied as a LAD-level covariate rather than an LSOA-level measure

---

### Policy Brief

A standalone brief (10 pages maximum) covering:
1. Problem statement
2. Data and method
3. National findings
4. Regional variation
5. LAD-level rankings
6. Policy implications

---

## Intended Audiences

**Primary:** Local Authorities, Combined Authorities, Department for Transport, NHS Integrated Care Boards, Office for Health Improvement and Disparities (OHID), Active Travel England

**Secondary:** Sustrans, Transport for All, Campaign for Better Transport, Disability Rights UK, Wheels for Wellbeing, IPPR, Resolution Foundation, Joseph Rowntree Foundation, Parliamentary Transport Committee

---

## Project Status

> 🚧 Under active development

- [x] Data acquisition and harmonisation
- [x] Master LSOA dataset construction
- [x] Derived indices and national inequality analysis
- [x] LAD and Regional aggregation
- [ ] Dashboard development
- [ ] Policy brief
- [ ] Publication

---

## Reproducibility

All code, data processing steps, and methodology documentation are published in this repository. Raw data sources are publicly available from the links above. The project is fully reproducible by any analyst with access to R and the listed open datasets. The main analysis script requires the following R packages: `rio`, `tidyverse`, `janitor`, `scales`, `ggrepel`, `patchwork`, `sf`, `ggplot2`, `viridis`, `glue` (all installable via `pacman::p_load()`).

---

## Licence

[![MIT License](https://img.shields.io/badge/Code-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![OGL v3.0](https://img.shields.io/badge/Data-OGL_v3.0-brightgreen.svg)](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/)
[![Crown Copyright](https://img.shields.io/badge/Census-Crown_Copyright-yellow.svg)](https://www.ons.gov.uk/methodology/geography/licences)

Analysis code is licensed under the [MIT Licence](https://opensource.org/licenses/MIT).
Contains public sector information licensed under the [Open Government Licence v3.0](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/).
Census data: [© Crown copyright](https://www.ons.gov.uk/methodology/geography/licences).

---

## About Open Data Insights

[Open Data Insights](https://opendatainsights.org) is a UK-focused open-access research initiative that turns public datasets into analysis that councils, health bodies, and civil society organisations can act on.

> *We believe open data should lead to open decisions!*
