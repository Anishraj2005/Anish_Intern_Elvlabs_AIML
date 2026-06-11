# 🤖 Elevate Labs AIML Internship Portfolio

<p align="center">
  <img src="https://img.shields.io/badge/Internship-Ongoing-brightgreen?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/AIML-Machine%20Learning-blue?style=for-the-badge&logo=python"/>
  <img src="https://img.shields.io/badge/Python-3.12-yellow?style=for-the-badge&logo=python"/>
</p>

---

## 📑 Table of Contents

- [👋 About This Internship](#-about-this-internship)
- [🏆 Internship Highlights](#-internship-highlights)
- [🔎 Detailed Task Summaries](#-detailed-task-summaries)
  - [Task 1: Data Cleaning & Preprocessing](#task-1-data-cleaning--preprocessing)
  - [Task 2: Exploratory Data Analysis (UNSW‑NB15)](#task-2-exploratory-data-analysis-unswnb15)
  - [Task 3: Linear Regression – House Price Prediction](#task-3-linear-regression--house-price-prediction)
  - [Task 4: Logistic Regression – Breast Cancer Classification](#task-4-logistic-regression--breast-cancer-classification)
  - [Task 5: Tree‑Based Models – Heart Disease Classification](#task-5-tree-based-models--heart-disease-classification)
  - [Task 6: K‑Nearest Neighbors – Iris Classification](#task-6-k-nearest-neighbors--iris-classification)
- [📁 Project Blueprint (Coming Soon)](#-project-blueprint-coming-soon)
- [🌟 Why Hire Me?](#-why-hire-me)
- [📈 Key Skills Demonstrated](#-key-skills-demonstrated)

---

## 👋 About This Internship

**Role:** AIML Intern  
**Organization:** Elevate Labs  
**Duration:** 45 days (May–June 2026)

Welcome! This repository documents my hands‑on journey as an AIML Intern at Elevate Labs. I have successfully completed **6 practical tasks** covering the complete machine learning pipeline – from data cleaning and exploratory analysis to regression, classification (logistic, tree‑based, KNN), and model evaluation. My final project is currently in the planning phase; a blueprint is provided below.

---

## 🏆 Internship Highlights

| # | Task Title                                                                 | Focus Area                          | Key Tools / Libraries                               | Badge                                                                                                                          |
| - | -------------------------------------------------------------------------- | ----------------------------------- | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| 1 | [Data Cleaning & Preprocessing](#task-1-data-cleaning--preprocessing)      | Data Wrangling, Outlier Handling    | Pandas, NumPy, Scikit‑learn                         | <img src="https://img.shields.io/badge/Data%20Cleaning-Pandas-blue?style=flat-square&logo=pandas" />                           |
| 2 | [EDA (UNSW‑NB15)](#task-2-exploratory-data-analysis-unsw-nb15)             | Statistical Analysis, Visualisation | Matplotlib, Seaborn, Plotly                         | <img src="https://img.shields.io/badge/EDA-Visualisation-orange?style=flat-square&logo=python" />                              |
| 3 | [Linear Regression](#task-3-linear-regression--house-price-prediction)     | Regression, Overfitting Diagnosis   | Scikit‑learn, Seaborn                               | <img src="https://img.shields.io/badge/Regression-Linear%20Regression-red?style=flat-square&logo=scikit-learn" />              |
| 4 | [Logistic Regression](#task-4-logistic-regression--breast-cancer-classification) | Binary Classification, Threshold Tuning | Scikit‑learn, ROC‑AUC                               | <img src="https://img.shields.io/badge/Classification-Logistic-green?style=flat-square&logo=scikit-learn" />                   |
| 5 | [Tree‑Based Models](#task-5-tree-based-models--heart-disease-classification) | Ensemble Learning, Feature Importance | Random Forest, XGBoost, GraphViz                   | <img src="https://img.shields.io/badge/Ensemble-Random%20Forest-purple?style=flat-square&logo=scikit-learn" />                 |
| 6 | [K‑Nearest Neighbors](#task-6-k-nearest-neighbors--iris-classification)    | Distance‑Based Classification, PCA  | Scikit‑learn, Matplotlib                            | <img src="https://img.shields.io/badge/KNN-Distance%20Based-yellow?style=flat-square&logo=scikit-learn" />                     |

---

## 🔎 Detailed Task Summaries

### Task 1: Data Cleaning & Preprocessing

[🔗 View Full Task](https://github.com/Anishraj2005/Anish_Intern_Elvlabs_AIML/tree/Task-1)

**Objective:** Clean and prepare the raw UNSW‑NB15 network intrusion dataset for machine learning.  
**Steps:** Median imputation (numerical), mode imputation (categorical), one‑hot encoding for `proto`/`service`, ordinal encoding for `state`, IQR‑based outlier capping (Winsorising), and `StandardScaler` normalisation.  
**Outcome:** Preserved all 82,332 training rows; increased feature count from 45 to 185 after encoding; produced `UNSW_NB15_training_cleaned.csv` and `UNSW_NB15_testing_cleaned.csv` with zero data leakage.  
**Key Learning:** Outlier capping retains attack patterns while limiting noise – essential for intrusion detection.

---

### Task 2: Exploratory Data Analysis (UNSW‑NB15)

[🔗 View Full Task](https://github.com/Anishraj2005/Anish_Intern_Elvlabs_AIML/tree/Task-2)

**Objective:** Perform in‑depth EDA on the cleaned UNSW‑NB15 data to guide modelling.  
**Findings:** Slight class imbalance (55% attack, 44% normal); `Generic` and `Exploits` dominate attack categories; strong right‑skew in numeric features; `sttl`, `rate`, `sload` most correlated with `label`.  
**Outcome:** Pairplots and scatter plots revealed clear separability between normal and attack traffic, especially using TTL and rate features.  
**Key Learning:** Linear models are insufficient – tree‑based or neural networks are recommended for intrusion detection.

---

### Task 3: Linear Regression – House Price Prediction

[🔗 View Full Task](https://github.com/Anishraj2005/Anish_Intern_Elvlabs_AIML/tree/Task-3)

**Objective:** Build simple and multiple linear regression models to predict house prices (`Housing.csv`).  
**Outcome:** Simple (area‑only) R² = 0.27; multiple (all features) R² = 0.65. Residual analysis showed heteroscedasticity and non‑normality. **Critical finding:** 5‑fold cross‑validation produced strongly negative R² (mean -9.91), revealing severe overfitting.  
**Key Learning:** Linear regression assumptions can be violated; cross‑validation is vital to detect overfitting before trusting a model.

---

### Task 4: Logistic Regression – Breast Cancer Classification

[🔗 View Full Task](https://github.com/Anishraj2005/Anish_Intern_Elvlabs_AIML/tree/Task-4)

**Objective:** Classify breast tumours as malignant or benign using the Wisconsin dataset.  
**Outcome:** Accuracy = 96.5%, ROC‑AUC = 0.996. Threshold tuning (optimal at 0.24) improved F1‑score. Visualised the sigmoid function and confusion matrix.  
**Key Learning:** Logistic regression works excellently on well‑separated medical data; threshold adjustment trades off precision vs. recall (critical for cancer detection).

---

### Task 5: Tree‑Based Models – Heart Disease Classification

[🔗 View Full Task](https://github.com/Anishraj2005/Anish_Intern_Elvlabs_AIML/tree/Task-5)

**Objective:** Predict heart disease using Decision Tree, Random Forest, Extra Trees, and Gradient Boosting.  
**Outcome:** Random Forest and Extra Trees achieved **100% test accuracy**; Gradient Boosting 97.6%. Feature importance highlighted `cp` (chest pain), `thalach` (heart rate), and `ca` (vessel count) as top predictors. Decision tree visualisation (depth 9) provided interpretable rules.  
**Key Learning:** Ensemble methods dramatically outperform single trees; feature importance offers clinical insights.

---

### Task 6: K‑Nearest Neighbors – Iris Classification

[🔗 View Full Task](https://github.com/Anishraj2005/Anish_Intern_Elvlabs_AIML/tree/Task-6)

**Objective:** Classify iris species using KNN with hyperparameter tuning and PCA visualisation.  
**Outcome:** Default k=5 gave 93.3% accuracy; GridSearchCV found best parameters (`k=17`, `weights='distance'`, `metric='euclidean'`) with CV accuracy 97.5% and test accuracy 96.7%. Decision boundaries visualised after PCA showed clear separation for Setosa and more complex boundaries for Versicolor/Virginica.  
**Key Learning:** Scaling is essential for distance‑based algorithms; larger k with distance weighting can improve generalisation.

---

## 📁 Project Blueprint (Coming Soon)

> **Note:** My final AIML project has not started yet. Below is the planned structure and intended features.

### 🧠 Project Title
### 🎯 Goal

### 🧱 Planned Structure  

### ✨ Intended Features  

*This section will be expanded once the project officially kicks off.*

---

## 🌟 Why Hire Me?

- **Complete ML Pipeline Experience:** From raw data cleaning to model tuning and evaluation – I’ve done it all.  
- **Deep Understanding of Model Limitations:** Detected overfitting (Task 3), used cross‑validation (Tasks 3,5,6), and tuned thresholds (Task 4).  
- **Cybersecurity‑Aware:** Chose UNSW‑NB15 for tasks 1‑2 because I’m passionate about applying AI to intrusion detection.  
- **Ensemble & Distance‑Based Proficiency:** Worked with Random Forest, XGBoost, KNN, and logistic regression.  
- **Professional Documentation:** Every task includes a detailed README, visualisations, and reproducibility files (CSV splits, PDF exports).

---

## 📈 Key Skills Demonstrated

- **Data Preprocessing:** Missing value imputation, one‑hot/ordinal encoding, outlier capping (IQR), standardisation.  
- **Exploratory Data Analysis:** Summary statistics, skewness/kurtosis, correlation matrices, pairplots, boxplots, scatter plots.  
- **Regression:** Simple/multiple linear regression, residual diagnostics, regularisation (Ridge/Lasso), cross‑validation.  
- **Classification:** Logistic regression (sigmoid, ROC‑AUC, threshold tuning), decision trees, random forest, extra trees, gradient boosting, KNN.  
- **Model Evaluation:** Accuracy, precision, recall, F1‑score, confusion matrix, learning curves, grid search, PCA visualisation.  
- **Tools & Environment:** Python 3.12, Jupyter Notebook, Pandas, NumPy, Scikit‑learn, Matplotlib, Seaborn, Plotly, GraphViz.

---

<p align="center">
  <em>Thank you for reviewing my AIML internship portfolio!</em>
</p>
