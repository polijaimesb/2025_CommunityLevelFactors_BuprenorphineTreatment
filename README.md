# Community-Level Factors Influencing the Duration of Buprenorphine Treatment in Individuals with Opioid Use Disorder

This repository contains four R markdown scripts to process, clean, and analyze claims data of patients treated with buprenorphine for opioid use disorder (OUD), focusing on understanding treatment duration and its predictors using real-world data.

## Prerequisites
The following R packages are required to run the scripts:

```
library(dplyr)
library(data.table)
library(stringr)
library(tidyr)
library(ggplot2)
library(AdhereR)
library(plotly)
library(gridExtra)
library(table1)
library(nnet)
library(caret)
library(pROC)
library(cobalt)
library(twang)
library(stringi)
library(readxl)
library(tidycensus)

```

## Authorization
The data used in this project is restricted and not publicly accessible.

## How to Use It
The first markdown script (1.-Data_processing) constructs the buprenorphine treatment cohort. It links claims with demographic and enrollment information, applies age and medication filters, identifies the index date, and removes invalid entries.

The second markdown script (2.-Analytical_cohort_derivation) processes the cohort by defining treatment episodes, calculating adherence measures (e.g., PDC), and creating outcome and feature variables. It merges clinical, demographic, diagnostic, procedural, and contextual (SDOH) information to form a complete dataset for modeling.

The third markdown script (3.-MNLR_model_deveopment) prepares features, selects variables, trains multinomial logistic and virtual twin models, and performs model evaluation. It exports the fitted models and predicted outcomes for further use.

The fourth markdown script (4.-SVI_censusTo3ZIP) converts the Social Vulnerability Index (SVI) from census tract to 3-digit ZIP code level by doing a weighted average SVI calculation using crosswalk tables from U.S. Department of Housing and Urban Development (HUD). 
## Analysis
Treatment episodes are defined using a 14-day gap rule. Adherence is measured with PDC over 30- and 90-day windows. Outcomes include discontinuation (episode duration < 180 days) and categorical duration outcomes (short (0-3 months), medium (3-6 months), extended-medium (6-12 months), long (more than 12 months). Demographic, diagnostic, procedural, and contextual variables are used as predictors. Multinomial logistic regression identifies factors associated with treatment retention.

## Publication
Jaimes-Buitron PA, Zhang K, Gong Y, Guo Y, Bauer C, Vivas-Valencia C. Community-level factors influencing the duration of buprenorphine treatment in individuals with opioid use disorder: a cohort study using US longitudinal claims data. BMJ Public Health. 2025;3:e003767. https://doi.org/10.1136/bmjph-2025-003767
