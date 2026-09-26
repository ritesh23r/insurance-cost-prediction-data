# Insurance Cost Prediction — From Raw Data to Model-Ready Data

## Project Overview

This project focuses on preparing a medical insurance dataset for machine learning.

The goal was to take the raw insurance data, perform exploratory data analysis, clean and transform the data, engineer useful features, and prepare a final dataset ready for a prediction model.

**Raw Data → EDA → Data Cleaning → Feature Engineering → Statistical Feature Selection → Model-Ready Data**

---

## Dataset

The dataset contains 1,338 records and 7 original features.

| Feature | Description |
|---|---|
| age | Age of the individual |
| sex | Gender |
| bmi | Body Mass Index |
| children | Number of children/dependents |
| smoker | Smoking status |
| region | Residential region |
| charges | Medical insurance charges |

---

## Exploratory Data Analysis

The following analyses were performed:

- Dataset shape and structure
- Data types
- Descriptive statistics
- Missing-value analysis
- Duplicate-value analysis
- Distribution of numerical features
- Categorical feature distributions
- Boxplots for numerical variables
- Correlation analysis

---

## Data Cleaning & Preprocessing

The following preprocessing steps were performed:

- Checked for missing values
- Removed duplicate records
- Converted categorical variables into numerical representations
- Renamed encoded variables for better readability
- Applied one-hot encoding to the `region` column

Examples:

- `sex` → `is_female`
- `smoker` → `is_smoker`

---

## Feature Engineering

A BMI category feature was created using standard BMI ranges:

| BMI Range | Category |
|---|---|
| Below 18.5 | Underweight |
| 18.5 – 24.9 | Normal |
| 25 – 29.9 | Overweight |
| 30+ | Obese |

Numerical features were standardized using `StandardScaler`.

Features scaled:

- age
- bmi
- children

---

## Statistical Feature Selection

A Chi-square test was used to investigate the relationship between categorical features and insurance charge groups.

Insurance charges were divided into four groups using quartiles.

### Process

Insurance Charges  
↓  
Quartile Groups  
↓  
Contingency Table  
↓  
Chi-square Test  
↓  
p-value  
↓  
Feature Selection

Significance level:

`α = 0.05`

---

## Final Dataset

After preprocessing and feature engineering, the dataset was transformed into a numerical format suitable for machine learning.

Selected features include:

- age
- is_female
- bmi
- children
- is_smoker
- region_southeast
- charges
- bmi_category_Obese

---

## Project Workflow

```text
Raw Dataset
     ↓
Exploratory Data Analysis
     ↓
Data Cleaning
     ↓
Categorical Encoding
     ↓
Feature Engineering
     ↓
Feature Scaling
     ↓
Correlation Analysis
     ↓
Chi-square Feature Selection
     ↓
Model-Ready Dataset
