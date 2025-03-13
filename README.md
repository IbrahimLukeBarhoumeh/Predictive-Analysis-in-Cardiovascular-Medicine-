# Predictive Analysis in Cardiovascular Medicine

This repository contains a comprehensive project on predictive analytics for cardiovascular health, focusing on two core tasks:

1. **Regression** to predict the clinical severity of heart failure.
2. **Classification** to predict patient mortality (`DEATH_EVENT`).

## Table of Contents
- [Overview](#overview)
- [Dataset Description](#dataset-description)
- [Project Structure](#project-structure)
- [Methods and Analysis](#methods-and-analysis)
    - [1. Exploratory Data Analysis](#1-exploratory-data-analysis)
    - [2. Regression Analysis](#2-regression-analysis)
    - [3. Classification Analysis](#3-classification-analysis)
- [Key Results](#key-results)
- [Conclusion](#conclusion)
- [Contact](#contact)

---

## Overview
Heart failure is a critical medical condition with significant implications for patient outcomes. The primary objective of this project was to leverage machine learning and statistical analysis to predict:
1. **Severity** of heart failure for each patient.
2. **Mortality risk** (`DEATH_EVENT`) using various classification models.

The findings can help clinicians and stakeholders identify high-risk patients and tailor interventions accordingly.

---

## Dataset Description
- **Name:** Heart Failure Clinical Records with Severity  
- **Size:** 299 patient records  
- **Features:**  
  - Age, Sex, Anaemia, Creatinine Phosphokinase, Diabetes, Ejection Fraction, High Blood Pressure, Platelets, Serum Creatinine, Serum Sodium, Smoking, Time (days), and a `Severity` score.  
  - **Target (for classification):** `DEATH_EVENT`  
  - **Target (for regression):** `Severity`  

This dataset was first introduced in the publication:  
> D. Chicco, G. Jurman: *"Machine learning can predict survival of patients with heart failure from serum creatinine and ejection fraction alone"*. BMC Medical Informatics and Decision Making 20, 16 (2020).

---

## Project Structure


- **data/** contains the dataset.  
- **notebooks/** includes Jupyter Notebooks for Exploratory Data Analysis (EDA), Regression, and Classification.  
- **README.md** is this document, providing an overview of the project.

---

## Methods and Analysis

### 1. Exploratory Data Analysis
- **Statistical Summary:** Checked for missing values, data types, and summary statistics.  
- **Visualizations:** Histograms, boxplots, and correlation heatmaps to understand feature distributions and potential relationships.  
- **Pairplots:** Explored how features interact and their impact on mortality.

### 2. Regression Analysis
- **Models:** 
  1. **Linear Regression**  
  2. **Ridge Regression**  
  3. **Lasso Regression**  
  4. **Kernel Regression (Kernel Ridge)**: tested linear, polynomial, and RBF kernels

- **Evaluation Metrics:** 
  - **Mean Squared Error (MSE)**  
  - **R-squared (R2)**  

- **Key Findings:**  
  - Ridge Regression slightly outperformed Linear Regression in terms of MSE and R2.  
  - Lasso allowed for feature importance inspection by driving some coefficients to zero.  
  - Kernel methods required tuning to outperform simpler linear models.

### 3. Classification Analysis
- **Models:** 
  1. **Logistic Regression**  
  2. **Support Vector Machine (SVM)**  
  3. **Random Forest**  
  4. **Naïve Bayes (GaussianNB)**  

- **Evaluation Metrics:**
  - **Accuracy**  
  - **Precision**  
  - **Recall**  
  - Additionally, classification reports and confusion matrices were reviewed.

- **Model Comparison:**  
  - Logistic Regression and SVM performed strongly (≈ 80% accuracy).  
  - Random Forest and Naïve Bayes showed moderate performance, suggesting benefits from further hyperparameter tuning.

---

## Key Results
1. **Regression (Severity Prediction):**  
   - **Best MSE**: ~0.84 with Ridge Regression  
   - **R-squared**: ~0.73  
   - Lasso helped in identifying key predictors (e.g., serum creatinine, ejection fraction).

2. **Classification (Mortality Prediction):**  
   - **Logistic Regression** and **SVM** consistently reached around 80% accuracy.  
   - **Random Forest** and **Naïve Bayes** showed slightly lower accuracy (~70–75%), but improved with parameter tuning.  
   - Precision-recall trade-offs suggest potential to optimize recall if we want to minimize missed deaths.

---

## Conclusion
Overall, we successfully demonstrated how various machine learning techniques can be applied to predict both the severity and mortality of heart failure patients using a structured dataset. By performing thorough EDA, model selection, and hyperparameter tuning, we gained valuable insights into the **key predictors** of heart failure severity and the **best-performing classification algorithms** for patient mortality. While certain models like Logistic Regression showed strong performance, the choice of model ultimately depends on the clinical objectives, such as favoring higher recall to ensure fewer missed cases.

**Further enhancements** could include more extensive hyperparameter tuning, advanced feature engineering, or incorporating additional clinical variables.

---
