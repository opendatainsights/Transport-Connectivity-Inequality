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
| **DfT Connectivity Metric** | Overall, walking, cycling, public transport, and driving scores across six destination types (employment, healthcare, education, shopping, leisure, social) | OA, LSOA, LAD, Region | [GOV.UK](https://www.gov.uk/government/publications/transport-connectivity-metric/transport-connectivity-metric) |
| **IMD 2019** | Index of Multiple Deprivation: overall rank, decile, and domain scores including Health Deprivation & Disability | LSOA (England) | [GOV.UK](https://www.gov.uk/government/statistics/english-indices-of-deprivation-2019) |
| **Census 2021: Disability (TS038)** | Long-term health problems or disabilities: limited a lot, limited a little, not limited | OA, LSOA, LAD | [ONS](https://www.ons.gov.uk/datasets/TS038/editions/2021/versions/2) |
| **Census 2021: Car Availability (TS045)** | Households by number of cars or vans (0, 1, 2, 3+) | OA, LSOA, LAD | [Nomis](https://www.nomisweb.co.uk/datasets/c2021ts045) |
| **Census 2021: Population & Age** | Usual residents by age and sex | OA, LSOA, LAD | [Nomis Bulk Downloads](https://www.nomisweb.co.uk/sources/census_2021_bulk) |
| **ONS Rural-Urban Classification 2021** | Urban, Larger Rural, Smaller Rural with Relative Access (Nearer/Further) | OA, LSOA, MSOA, LAD | [ONS](https://www.ons.gov.uk/methodology/geography/geographicalproducts/ruralurbanclassifications/2021ruralurbanclassification) |
| **ONS Geographic Lookup Tables** | OA to LSOA to MSOA to LAD mapping (May 2025 edition) | All levels | [ONS Open Geography Portal](https://geoportal.statistics.gov.uk/) |
| **ONS Population Estimates** | Mid-year population estimates by LAD | LAD | [ONS](https://www.ons.gov.uk/peoplepopulationandcommunity/populationandmigration/populationestimates) |

### Data Notes

**DfT Connectivity Metric** uses Q4 2024/Q1 2025 data on 2021 OA boundaries. Public ODS tables cover OA, LSOA, LAD, and Region. The metric scores four transport modes (walking, cycling, public transport, driving) across six travel purposes on a 0 to 100 relative scale. The default "overall" score excludes driving and weights sustainable modes at roughly 52% public transport, 40% walking, 8% cycling.

**IMD 2019** covers England only. The Welsh Index of Multiple Deprivation (WIMD 2019) uses a different methodology and is not directly comparable. This is acknowledged throughout the analysis.

**Rural-Urban Classification 2021** is a major update from 2011, with three simplified settlement categories and a new Relative Access dimension based on estimated 30-minute car travel to Built-Up Areas with 75,000+ residents.

**Known limitations of the DfT metric:** assumes perfect timetable adherence (areas with unreliable services appear better connected than they are), does not model travel cost or affordability, and uses pre-COVID travel behaviour data from the National Travel Survey 2011 to 2020.

---

## Methodology

### 1. Geographic Harmonisation

All datasets are linked through ONS 2021 Census geography using the OA to LSOA to MSOA to LAD best-fit lookup (May 2025 edition). LSOA is the primary unit of analysis because all data sources are available at this level. OA-level analysis is used for local case studies. LAD and Regional aggregation uses population-weighted averages, consistent with the DfT's own approach.

### 2. Data Integration

At LSOA level, the master dataset merges:
- DfT connectivity scores (overall, by mode, by destination type)
- IMD 2019 rank, decile, and Health Deprivation domain score
- Census 2021 disability prevalence
- Census 2021 car/van availability (% households with no car)
- ONS 2021 Rural-Urban Classification
- Mid-year population estimates

### 3. Derived Indices

| Index | Formula | What it captures |
|-------|---------|------------------|
| **Car Dependency Index** | `Driving Score - Public Transport Score` | Areas where driving far outperforms public transport, indicating structural car dependency |
| **Active Travel Gap** | `Mean(Walking, Cycling) - Driving` | Negative values flag areas where driving dominates and active travel provision is weak |
| **Need-Connectivity Mismatch** | `Disability Rate x (1 - Healthcare PT Score / 100)` | High-need areas with poor public transport access to health services |
| **Deprivation-Connectivity Gradient** | `Mean PT Score at IMD Decile 10 - Mean PT Score at Decile 1` | The size of the accessibility gap between the least and most deprived communities |

### 4. Inequality Gradient Analysis

For each region and nationally: calculate mean public transport connectivity by IMD decile, test for gradient linearity, and compute the Decile 10 minus Decile 1 gap. This shows whether transport inequality tracks deprivation systematically or varies by regional context.

### 5. LAD Policy Ranking

Aggregate LSOA metrics to LAD using population-weighted means. Rank Local Authorities by:
- Mean public transport connectivity
- Share of LSOAs in the national bottom 20%
- Car Dependency Index
- Need-Connectivity Mismatch score

### 6. Limitations

- The DfT metric does not include travel cost, so affordability barriers are invisible
- Pre-COVID travel behaviour data may not reflect current commuting and travel patterns
- IMD 2019 uses 2015/16 indicators and deprivation patterns may have shifted
- Timetable adherence assumptions mean areas with poor service reliability look better connected than they are
- Wales analysis is constrained by IMD incompatibility; WIMD results are reported separately

---

## Outputs

### Datasets

| File | Description |
|------|-------------|
| `master_lsoa_dataset.csv` | LSOA-level master dataset with connectivity, deprivation, disability, car ownership, and rurality |
| `master_oa_dataset.csv` | OA-level dataset for local case studies |
| `lad_summary.csv` | LAD-level summary with policy rankings |
| `region_summary.csv` | Regional structural analysis |

### Visualisations and Dashboards

- National inequality dashboard with IMD vs connectivity scatter plots, region filters, and LAD ranking tables
- Car dependency map at LSOA level with the 50 most car-dependent councils highlighted
- Healthcare access mismatch map showing the top 10% worst areas overlaid with disability prevalence
- Urban vs rural connectivity comparison charts
- Regional inequality gradient profiles

Interactive dashboards will be published at [OpenDataInsights.org](https://opendatainsights.org).

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

- [ ] Data acquisition and harmonisation
- [ ] Master LSOA dataset construction
- [ ] Derived indices and national inequality analysis
- [ ] LAD and Regional aggregation
- [ ] Dashboard development
- [ ] Policy brief
- [ ] Publication

---

## Reproducibility

All code, data processing steps, and methodology documentation will be published in this repository. Raw data sources are publicly available from the links above. The project is designed to be fully reproducible by any analyst with access to R or Python and the listed open datasets.

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

> *Open data should lead to open decisions.*
