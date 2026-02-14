# Transport Connectivity & Inequality


## Overview

This project develops a multi-level analytical framework to measure structural transport inequality across England and Wales.

Using open government datasets, we quantify how accessibility to employment, healthcare, education, retail, and leisure varies across Output Area (OA), Lower Super Output Area (LSOA), Local Authority District (LAD), and Region.

The goal is to identify communities facing the greatest mobility barriers and to assess how deprivation, rurality, and car access shape inequality in transport connectivity.

---

## Core Impact Question

> **Which communities face the largest structural barriers to mobility, healthcare access, employment opportunities, and essential services?**

---

## Research Questions

1. How does transport connectivity vary across OA → LSOA → LAD → Region?
2. Where are the largest accessibility gaps between deprived and affluent communities?
3. How do urban–rural classifications influence connectivity outcomes?
4. Does car ownership reduce or mask deeper structural inequality?
5. Which Local Authorities exhibit the greatest deprivation-adjusted transport deficits?

---

## Data Sources

All datasets are open-access:

| Source | Detail | Level | Link |
|--------|--------|-------|------|
| **Department for Transport (DfT)** | Connectivity Metrics (2025) | LSOA | [Transport connectivity metric](https://www.gov.uk/government/publications/transport-connectivity-metric/transport-connectivity-metric) |
| **IMD 2019** | Index of Multiple Deprivation | LSOA | [IMD 2019](https://www.gov.uk/government/statistics/english-indices-of-deprivation-2019) |
| **Census 2021** | Car Ownership, Disability, Population Structure | OA | [Census 2021](https://www.ons.gov.uk/census) |
| **ONS Rural–Urban Classification** | Settlement type indicators | LSOA / LAD | [Rural–Urban Classification](https://www.ons.gov.uk/methodology/geography/geographicalproducts/ruralurbanclassifications) |
| **ONS Population Estimates & Density** | Mid-year estimates | LAD | [Population Estimates](https://www.ons.gov.uk/peoplepopulationandcommunity/populationandmigration/populationestimates) |
| **ONS Geographic Lookup Tables** | OA → LSOA → LAD → Region | All levels | [ONS Geoportal](https://geoportal.statistics.gov.uk/) |

---

## Methodology

### 1. Geographic Harmonisation

Postcode → OA → LSOA → LAD → Region using ONS lookup tables.

### 2. Multi-Level Data Integration

Merge connectivity, deprivation, demographic, and rurality datasets across all geographic levels.

### 3. Derived Indices

| Index | Formula |
|-------|---------|
| **Car Dependency Index** | `Driving Accessibility − Public Transport Accessibility` |
| **Active Travel Gap** | `Mean(Walking, Cycling) − Driving` |
| **Deprivation-Adjusted Connectivity Score** | `Connectivity weighted by IMD decile` |
| **Need–Connectivity Mismatch** | `Disability prevalence × (1 − Healthcare Accessibility Score)` |

### 4. Inequality Gradient Analysis

Connectivity range between IMD Decile 1 (most deprived) and Decile 10 (least deprived) across LADs and Regions.

---

## Outputs

**Datasets**

| File | Description |
|------|-------------|
| `master_oa_dataset.csv` | Output Area level master dataset |
| `master_lsoa_dataset.csv` | LSOA level master dataset |
| `lad_summary.csv` | Local Authority District summary |
| `region_summary.csv` | Regional summary |

**Visualisations**

- IMD vs Connectivity gradients
- Urban–rural access comparison charts
- Car Dependency heatmaps
- Accessibility inequality maps
- LAD rankings

Interactive dashboards will be published via [OpenDataInsights.org](https://opendatainsights.org).

---

## Policy Relevance

**Intended Audiences** — Local Authorities, Transport Authorities, NHS Integrated Care Boards, Public Health Teams, Urban Planners, and Civil Society Organisations.

**Findings can inform:**

- Transport investment prioritisation
- Active travel strategy
- Rural mobility policy
- Health access planning
- Levelling Up and inequality strategies

---

## Project Status

> 🚧 **Under active development**

- [ ] Data harmonisation in progress
- [ ] Master LSOA dataset construction underway
- [ ] First inequality dashboard scheduled for release following validation

---

## About Open Data Insights

[Open Data Insights](https://opendatainsights.org) is a UK-focused open-access research initiative transforming public datasets into actionable, policy-relevant insights.

> *We believe open data should lead to open decisions.*
