# Forecasting Forest Fires: The Role of Fire Weather Indices
An R Markdown project for predicting forest fire occurrences in the Canadian Cordillera and Hudson Bay regions using the Canadian Fire Weather Index system (FFMC, DMC, DC, ISI, BUI, FWI) plus meteorological variables. Multiple machine-learning models are built and compared, with performance evaluated via confusion matrices, ROC curves, and AUC.

<div align="right" style="font-size:16px; color:black; font-family:Segoe UI, sans-serif;">
Developed by Haya Mazyad, Joudy Allam, and Nour Saad
    
As part of the *Data Mining* course, December 2024
</div>

---
## Overview

Forest fires are a significant threat to ecosystems and human life. Accurate prediction of fire occurrence based on fire weather indices and climate conditions can support early warning systems. This project involves data preprocessing, exploratory analysis, and comparative modeling using various supervised learning techniques.

## Dataset

The dataset includes measurements from two distinct geographical areas:
- Cordillera
- Hudson Bay
Each record includes:
- Meteorological Variables: Temperature, Relative Humidity (RH), Wind Speed, Rainfall
- Fire Weather Indices: FFMC, DMC, DC, ISI, BUI, FWI
- Target Variable: Classes (Fire or Not Fire)
  
The raw dataset is provided in `data/forest_fires_dataset.csv`.

## Preprocessing

Key preprocessing steps:
- Merged two location-based datasets into one unified table
- Created new variables: `Location`, `ClassesN` (numeric version of Classes), and `day_group`
- Converted categorical variables to factors
- Winsorized outliers to reduce skewness (applied 5th–95th percentile capping)
- Removed low-variance columns such as `year`

## Exploratory Data Analysis (EDA)

The dataset was explored through:
- Distribution plots (histograms, boxplots)
- Class imbalance analysis
- Correlation analysis between features
- Location-specific trends in feature values

## Modeling & Evaluation

Built and evaluated:
- Logistic Regression  
- Linear Discriminant Analysis (LDA)  
- Quadratic Discriminant Analysis (QDA)  
- k-Nearest Neighbors (KNN)  
- Decision Trees (pruned & unpruned)  
- Bagging  
- Random Forest  
- Gradient Boosting Machines (GBM)  
- Support Vector Machines (SVM)  

All models were trained on normalized datasets, using a 70-30 train-test split.
**Metrics:** Confusion matrix, ROC curve, AUC.

## Tools and Packages

All analyses were performed in R. The main packages used include:

- `dplyr`, `tidyr`, `ggplot2`
- `caret` for preprocessing and model training
- `rpart`, `randomForest`, `gbm`, `class`, `e1071`, `MASS`, `pROC`

## Report

The complete project report, including methodology, visualizations, and model evaluation, is provided in `docs/report.html`.
