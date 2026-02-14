# Transport Connectivity & Inequality

## Overview

This project builds a multi-level, policy-ready analytical framework that quantifies structural transport inequality across England and Wales.

Using the Department for Transport's new national Connectivity Metric — launched in September 2025 as the first standardised measure of how easily people can reach jobs, healthcare, education, shopping, leisure, and social engagements — we integrate connectivity scores with deprivation, disability, rurality, and car ownership data to expose where and why accessibility gaps exist.

The analysis operates across four nested geographic levels: Output Area (OA), Lower Super Output Area (LSOA), Local Authority District (LAD), and Region. The goal is to produce outputs that councils, NHS Integrated Care Boards, and transport authorities can act on directly.

---

## Core Impact Question

> **Which communities face the largest structural barriers to mobility, healthcare access, employment, and essential services — and what role do deprivation, rurality, and car dependency play?**

---

## Research Questions

### Geographic Variation
1. How does transport connectivity vary across OA → LSOA → LAD → Region?
2. Where are the worst-performing 10% of areas, and what structural characteristics do they share?

### Inequality Gradient
3. What is the public transport accessibility gap between IMD Decile 1 (most deprived) and Decile 10 (least deprived)?
4. Does the inequality gradient widen or narrow when aggregated from LSOA to LAD or Region?

### Urban–Rural Structure
5. How much of poor connectivity is explained by rurality versus deprivation?
6. Are there urban areas performing worse than expected given their density?

### Healthcare Access
7. Are high-disability areas also low in public transport access to healthcare services?
8. Where is the largest need–connectivity mismatch?

### Car Dependency
9. Does high driving connectivity mask weak public transport provision?
10. Which Local Authorities are structurally car-dependent, and what are the equity implications?

---

## Policy Context

This project is directly relevant to several active policy agendas:

- **DfT Connectivity Metric (September 2025):** The Government's first nationally agreed connectivity score, intended for annual reporting and described as the new "national metric of connectivity" for planning decisions. The Transport Secretary has positioned it as central to housing delivery and sustainable transport planning.
- **Bus Services Bill (2025):** Progressing through Parliament with measures on bus franchising, accessibility, and minimum connectivity standards for underserved areas.
- **Transport Committee Report (August 2025):** Called for urgent bus funding reform, minimum public transport connectivity standards, and protection of socially necessary rural routes.
- **IPPR Transport Roundtables (August 2025):** Highlighted that disabled people, young people, and those in temporary accommodation are disproportionately affected by poor connectivity — with some changing three or four buses to access healthcare.
- **Parliamentary Debate on Regional Transport Inequality (September 2025):** MPs cited stark examples — constituencies 40 miles from London where buses are 30–90 minutes apart, disappearing entirely after 7 pm.
- **Integrated National Transport Strategy:** Government aim to put people at the heart of the transport system, with connectivity improvements measured against a London benchmark.

Urban bus services have declined by 48% and rural bus services by 52% since 2008, with some local authority areas experiencing declines of up to 80%.

---

## Data Sources

All datasets are open-access and publicly available:

| Dataset | Detail | Geography | Source |
|---------|--------|-----------|--------|
| **DfT Connectivity Metric** | Overall, walking, cycling, public transport, and driving scores by six destination types (employment, healthcare, education, shopping, leisure, social) | OA, LSOA, LAD, Region | [GOV.UK — Transport Connectivity Metric](https://www.gov.uk/government/publications/transport-connectivity-metric/transport-connectivity-metric) |
| **IMD 2019** | Index of Multiple Deprivation — overall rank, decile, and domain scores including Health Deprivation & Disability | LSOA (England) | [GOV.UK — English Indices of Deprivation 2019](https://www.gov.uk/government/statistics/english-indices-of-deprivation-2019) |
| **Census 2021 — Disability (TS038)** | Long-term health problems or disabilities: limited a lot, limited a little, not limited | OA, LSOA, LAD | [ONS — Disability](https://www.ons.gov.uk/datasets/TS038/editions/2021/versions/2) |
| **Census 2021 — Car Availability (TS045)** | Households with 0, 1, 2, 3+ cars or vans | OA, LSOA, LAD | [Nomis — TS045](https://www.nomisweb.co.uk/datasets/c2021ts045) |
| **Census 2021 — Population & Age** | Usual residents by age and sex | OA, LSOA, LAD | [Nomis — Census 2021 Bulk Downloads](https://www.nomisweb.co.uk/sources/census_2021_bulk) |
| **ONS Rural–Urban Classification 2021** | Urban, Larger Rural Settlement, Smaller Rural Settlement — with Relative Access (Nearer/Further) | OA, LSOA, MSOA, LAD | [ONS — 2021 Rural Urban Classification](https://www.ons.gov.uk/methodology/geography/geographicalproducts/ruralurbanclassifications/2021ruralurbanclassification) |
| **ONS Geographic Lookup Tables** | OA → LSOA → MSOA → LAD mapping (May 2025 edition) | All levels | [ONS Open Geography Portal](https://geoportal.statistics.gov.uk/) |
| **ONS Population Estimates** | Mid-year population estimates by LAD | LAD | [ONS — Population Estimates](https://www.ons.gov.uk/peoplepopulationandcommunity/populationandmigration/populationestimates) |

### Data Notes

- **DfT Connectivity Metric** uses Q4 2024/Q1 2025 data on 2021 OA boundaries. Public ODS tables are available at OA/LSOA/LAD/Region level. The metric covers four transport modes (walking, cycling, public transport, driving) across six travel purposes, scored on a 0–100 relative scale. The default "overall" score excludes driving, weighting sustainable modes approximately 52% public transport, 40% walking, 8% cycling.
- **IMD 2019** covers England only. Welsh equivalents (WIMD 2019) use a different methodology and are not directly comparable, which is acknowledged in the analysis.
- **Rural–Urban Classification 2021** is a significant update from the 2011 version, now using three simplified categories with a new Relative Access dimension based on estimated 30-minute car travel times to Built-Up Areas with 75,000+ population.
- The DfT metric assumes perfect timetable adherence, does not model travel costs, and uses pre-COVID travel behaviour data (NTS 2011–2020). These limitations are noted throughout.

---

## Methodology

### 1. Geographic Harmonisation

All datasets are linked via ONS 2021 Census geography using the OA → LSOA → MSOA → LAD best-fit lookup (May 2025 edition). The LSOA is the primary analytical unit due to data availability across all sources. OA-level analysis is used for hyper-local case studies; LAD and Regional aggregation uses population-weighted averages consistent with the DfT's own methodology.

### 2. Multi-Level Data Integration

At LSOA level, merge:
- DfT connectivity scores (overall, by mode, by destination type)
- IMD 2019 rank, decile, and Health Deprivation domain
- Census 2021 disability prevalence
- Census 2021 car/van availability (% of households with no car)
- ONS 2021 Rural–Urban Classification
- Population estimates

### 3. Derived Indices

| Index | Formula | Interpretation |
|-------|---------|----------------|
| **Car Dependency Index** | `Driving Score − Public Transport Score` | Higher values indicate areas where driving significantly outperforms public transport — structurally car-dependent |
| **Active Travel Gap** | `Mean(Walking, Cycling) − Driving` | Negative values indicate driving-dominant areas with weak active travel infrastructure |
| **Need–Connectivity Mismatch** | `Disability Rate × (1 − Healthcare PT Score / 100)` | Identifies areas with high healthcare need but poor public transport access to health services |
| **Deprivation–Connectivity Gradient** | `Mean PT Score at IMD Decile 10 − Mean PT Score at IMD Decile 1` | Quantifies the accessibility gap between the least and most deprived communities |

### 4. Inequality Gradient Analysis

For each region and nationally: calculate mean public transport connectivity by IMD decile, test for gradient linearity, and compute the Decile 10 minus Decile 1 gap. This reveals whether transport inequality tracks deprivation systematically or varies by regional context.

### 5. LAD Policy Ranking

Aggregate LSOA-level metrics to LAD using population-weighted means. Rank Local Authorities by:
- Mean public transport connectivity
- Proportion of LSOAs in the national bottom 20%
- Car Dependency Index
- Need–Connectivity Mismatch score

### 6. Sensitivity and Limitations

- The DfT metric's exclusion of travel cost means affordability barriers are not captured
- Pre-COVID travel behaviour data may not reflect current patterns
- IMD 2019 data is based on 2015/16 indicators — deprivation patterns may have shifted
- Timetable adherence assumptions mean areas with unreliable services appear better connected than they are
- Wales analysis is limited by IMD incompatibility; Welsh Index of Multiple Deprivation (WIMD) is flagged separately

---

## Outputs

### Datasets

| File | Description |
|------|-------------|
| `master_lsoa_dataset.csv` | LSOA-level master dataset — connectivity, deprivation, disability, car ownership, rurality |
| `master_oa_dataset.csv` | OA-level dataset for hyper-local analysis and case studies |
| `lad_summary.csv` | LAD-level summary with policy-relevant rankings |
| `region_summary.csv` | Regional structural analysis |

### Visualisations & Dashboards

- National inequality dashboard — IMD vs connectivity scatter, region filters, LAD ranking table
- Car Dependency heatmap — LSOA-level map with top 50 most car-dependent councils
- Healthcare Access Mismatch map — top 10% worst areas overlaid with disability prevalence
- Urban–rural connectivity comparison charts
- Regional inequality gradient profiles

Interactive dashboards will be published via [OpenDataInsights.org](https://opendatainsights.org).

### Policy Brief

A standalone 10-page policy brief structured as:
1. Problem statement
2. Data and method
3. Key national findings
4. Regional variation
5. LAD-level rankings
6. Policy implications and recommendations

---

## Intended Audiences

**Primary:** Local Authorities, Combined Authorities, Department for Transport, NHS Integrated Care Boards, Office for Health Improvement and Disparities (OHID), Active Travel England

**Secondary:** Transport NGOs (Sustrans, Transport for All, Campaign for Better Transport), disability organisations (Disability Rights UK, Wheels for Wellbeing), think tanks (IPPR, Resolution Foundation, Joseph Rowntree Foundation), Parliamentary Transport Committee

---

## Project Status

> 🚧 **Under active development**

- [ ] Data acquisition and harmonisation
- [ ] Master LSOA dataset construction
- [ ] Derived indices and national inequality analysis
- [ ] LAD and Regional aggregation
- [ ] Dashboard development
- [ ] Policy brief drafting
- [ ] Publication and dissemination

---

## Reproducibility

All analysis code, data processing steps, and methodology documentation will be published in this repository. Raw data sources are publicly available from the links above. The project is designed to be fully reproducible by any analyst with access to R or Python and the listed open datasets.

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

[Open Data Insights](https://opendatainsights.org) is a UK-focused open-access research initiative that transforms public datasets into actionable, policy-relevant analysis. We bridge the gap between open government data and the communities, councils, and organisations that need it most.

> *Open data should lead to open decisions.*
