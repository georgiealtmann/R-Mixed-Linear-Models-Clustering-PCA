# Mixed Linear Models, Clustering & PCA in R

Statistical analysis of longitudinal childhood health data using mixed-effects models, model-based clustering, and principal component analysis.

## Overview

This project investigates barriers to healthy childhood living across a multi-site longitudinal study of **12,338 children** observed over up to 7 annual visits. It addresses two research questions:

1. **How do barriers to childhood living change over time?** — Answered using linear mixed models with random intercepts and slopes.
2. **Do biomarkers identify subgroups responding differently to standard care?** — Answered using Gaussian mixture model clustering on blood biomarkers, PCA for visualisation, and cluster-by-time interaction models.

## Methods

| Technique | Purpose | R Package |
|---|---|---|
| Linear Mixed Models | Model individual trajectories over time | `lme4` |
| Multiple Imputation (MICE) | Handle site-level missing biomarker data | `mice` |
| Model-Based Clustering | Identify biomarker-defined subgroups | `mclust` |
| PCA | Visualise high-dimensional biomarker space | base R `prcomp` |

## Key Findings

- Barriers decline significantly over time, with a **non-linear (quadratic) trajectory** — steeper early on, flattening at later visits.
- Substantial **between-child heterogeneity** in both starting level and rate of change (71.7% of variance is between-children).
- Two biomarker-defined clusters were identified. One cluster showed both **lower initial barriers and faster improvement**, suggesting potential for biomarker-guided personalisation of care.

## Project Structure

```
├── 7524_ABHDS.Rmd      # Full R Markdown analysis
├── 7524_ABHDS.html      # Knitted HTML report
└── README.md
```

## Requirements

```r
install.packages(c("tidyverse", "lme4", "mice", "mclust", "pheatmap"))
```

## How to Run

1. Clone this repository
2. Open `7524_ABHDS.Rmd` in RStudio
3. Update the data file paths in the `load-data` chunk to point to your local copies of `DATA.rds` and `BLOODS.rds`
4. Knit to HTML

## Visualisations

The report includes:
- Individual + mean trajectory plots
- QQ diagnostic plots for model residuals
- PCA scatter plot coloured by cluster membership
- Predicted trajectories by biomarker cluster
- Subject-specific fitted trajectories (BLUPs)
