# AGDS II 
Fabrice Mettler

## Project overview
This repository contains coursework for Applied Geodata Science II (University of Bern).
The project applies machine learning methods to environmental and spatial data, focusing on:
Digital soil mapping using Random Forests
Model evaluation and generalisability
Random, spatial, and environmental cross-validation
Open and reproducible data science workflows

## Repository structure
This project follows the GECO R project template, mirroring an R package structure without being a package.

```R
.
├─ R/            # R functions used across analyses
├─ analysis/     # Analysis scripts (no R Markdown)
├─ data-raw/     # Raw data and preprocessing scripts
├─ data/         # Analysis-ready data
├─ src/           # Non-R scripts (if required)
├─ vignettes/     # R Markdown reports (limited use)

```

## Exercises implemented
#### Digital soil mapping
Binary classification of waterlogged soils at 100 cm depth (waterlog.100)
Random Forest models using all predictors and reduced predictor sets
Model evaluation on test data using classification metrics
Hyperparameter optimisation with 5-fold cross-validation
Probabilistic predictions and ROC analysis
Discussion of decision thresholds under different risk scenarios

#### Spatial upscaling and cross-validation
Prediction of leaf nitrogen concentration (leafN)
Random Forest regression with environmental and species predictors
Comparison of:
Random cross-validation
Spatial cross-validation (geographical clusters)
Environmental cross-validation (climate space clusters)
Evaluation using RMSE and R²


## Reproducibility
The project uses {renv} to ensure reproducibility.

```
renv::init()
renv::snapshot()
renv::restore()
```

###src/
Not used. All workflows were implemented in R; no external (C, Python, Bash) code was required.

###data-raw/
Contains raw soil and environmental datasets and scripts used for preprocessing. These data are not analysis-ready and are transformed into cleaned datasets stored in data/.

###data/
Contains analysis-ready RDS files (e.g. df_full.rds) used directly for modelling. These datasets are outputs of preprocessing steps and are small enough to be tracked in Git.
All data was obtained by https://geco-bern.github.io/agds2_course/

###analysis/
Contains R scripts used for functions.

###vignettes/
Used for reporting (R Markdown) in the context of this course exercise. Code development and modelling logic reside in analysis/ and R/, in line with reproducible workflow principles.

