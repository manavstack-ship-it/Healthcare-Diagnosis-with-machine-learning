# 🩺 Patient Health Disease Prediction

A machine learning project that analyzes patient health and lifestyle data to explore patterns associated with disease presence and build classification models for disease prediction.

The project covers the complete data science workflow — from data cleaning and exploratory data analysis to preprocessing, statistical analysis, model training, and evaluation.

---

## 📌 Project Overview

The goal of this project is to analyze patient health records and determine whether available health and lifestyle features can effectively predict the presence of a disease.

The dataset contains information such as:

- Age
- Gender
- BMI
- Heart Rate
- Cholesterol Level
- Blood Pressure
- Diabetes Status
- Smoking Status
- Medications
- Disease Status

The project also investigates whether these features actually contain meaningful predictive information.

---

## 🎯 Objectives

- Clean and preprocess patient health data
- Handle unknown values and duplicate records
- Perform exploratory data analysis (EDA)
- Visualize distributions and relationships between features
- Analyze correlations between variables
- Compare health characteristics between disease classes
- Perform statistical hypothesis testing
- Prepare numerical and categorical features for machine learning
- Train classification models
- Evaluate model performance
- Analyze the limitations of the dataset

---

## 📊 Exploratory Data Analysis

The project includes visualizations and analysis such as:

- Feature distributions
- Histograms
- Box plots
- Count plots
- Disease class distribution
- Categorical feature analysis
- Correlation matrix
- Heatmap
- Numerical feature comparisons
- Feature relationships with disease status

These visualizations were used to understand the structure of the dataset and identify potential relationships between patient characteristics and disease status.

---

## 🧹 Data Preprocessing

The following preprocessing steps were performed:

1. Inspected dataset structure and data types
2. Identified unknown values
3. Removed records with unknown target values
4. Removed duplicate records
5. Separated features (`X`) and target (`y`)
6. Performed train-test split
7. Standardized numerical features using `StandardScaler`
8. Encoded categorical features using `OneHotEncoder`
9. Used `ColumnTransformer` to combine preprocessing steps

### Dataset after cleaning

- Disease = 0 → 2,424 records
- Disease = 1 → 2,386 records
- Total records → 4,810

The target classes are approximately balanced.

---

## 🔬 Statistical Analysis

Statistical tests were performed to investigate whether individual features were associated with disease status.

### Categorical Features

Chi-square tests were performed on:

- Gender
- Diabetes
- Smoking
- Medications

The obtained p-values were:

| Feature | p-value |
|---|---:|
| Gender | 0.4151 |
| Diabetic | 0.5715 |
| Smoker | 0.9163 |
| Medications | 0.6836 |

All p-values are greater than 0.05, indicating that these features did not show statistically significant associations with the target in this dataset.

Numerical features were also compared between the two disease classes.

---

## 🤖 Machine Learning Models

Two classification algorithms were implemented:

### 1. Logistic Regression

Logistic Regression was used as a baseline classification model.

**Accuracy: ~46.8%**

### 2. Random Forest

Random Forest was used to capture potential nonlinear relationships between features.

**Accuracy: ~50.3%**

### Model Comparison

| Model | Accuracy |
|---|---:|
| Logistic Regression | 46.8% |
| Random Forest | 50.3% |
| Random Baseline | ~50% |

---

## 📈 Results & Findings

The models achieved performance close to the random baseline.

Further analysis showed that:

- Numerical feature means were almost identical between disease classes.
- Categorical features had nearly identical distributions across both classes.
- Correlations between individual numerical features and disease status were extremely weak.
- Statistical tests did not show significant associations for the categorical features.

### Key Insight

The results suggest that the available features contain **very limited predictive information** for the `Has_Disease` target.

This project therefore demonstrates an important machine learning concept:

> **Good model performance depends heavily on the quality and predictive power of the available features.**

Increasing model complexity cannot compensate for a lack of meaningful information in the dataset.

---

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- SciPy
- Jupyter Notebook

---

## 📂 Project Structure

```text
Patient-Health-Disease-Prediction/
│
├── Patient_Health_Records_ML.csv
├── Patient_Health_Analysis.ipynb
├── README.md
│
└── visualizations/
    ├── distribution_plots/
    ├── correlation_heatmap/
    ├── boxplots/
    └── categorical_analysis/
