# 🤖 Elevate Labs AIML Internship Portfolio

<p align="center">
  <img src="https://img.shields.io/badge/Internship-Completed-brightgreen?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/AIML-Machine%20Learning-royalblue?style=for-the-badge&logo=python"/>
  <img src="https://img.shields.io/badge/Python-3.12-blue?style=for-the-badge&logo=python"/>
</p>

![Scikit-Learn](https://img.shields.io/badge/scikit--learn-1.5-F7931E?style=for-the-badge&logo=scikit-learn)
![XGBoost](https://img.shields.io/badge/XGBoost-2.0.3-orange?style=for-the-badge)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-FF6F00?style=for-the-badge&logo=tensorflow)
![Streamlit](https://img.shields.io/badge/Streamlit-1.36.0-red?style=for-the-badge&logo=streamlit)
![MediaPipe](https://img.shields.io/badge/MediaPipe-0.10.x-0097A7?style=for-the-badge&logo=google)

---

## 📑 Table of Contents

- [👋 About This Internship](#-about-this-internship)
- [🏆 Internship Highlights](#-internship-highlights)
- [🔎 Detailed Task Summaries](#-detailed-task-summaries)
- [📁 Projects](#-projects)
- [🌟 Why Hire Me?](#-why-hire-me)
- [📈 Key Skills Demonstrated](#-key-skills-demonstrated)

---

## 👋 About This Internship

**Role:** AIML Intern  
**Organization:** Elevate Labs  
**Duration:** 45 days (May–June 2026)

Welcome! This repository documents my hands-on journey as an AIML Intern at Elevate Labs. I have successfully completed **6 practical tasks** covering the complete machine learning pipeline — from data cleaning and exploratory analysis to regression, classification (logistic, tree-based, KNN), and model evaluation — plus **2 capstone projects** applying these skills to real-world problems.

---

## 🏆 Internship Highlights

| # | Task Title | Focus Area | Key Tools / Libraries |
|---|------------|------------|----------------------|
| 1 | Data Cleaning & Preprocessing | Data Wrangling, Outlier Handling | Pandas, NumPy, Scikit-learn |
| 2 | EDA (UNSW-NB15) | Statistical Analysis, Visualisation | Matplotlib, Seaborn, Plotly |
| 3 | Linear Regression | Regression, Overfitting Diagnosis | Scikit-learn, Seaborn |
| 4 | Logistic Regression | Binary Classification, Threshold Tuning | Scikit-learn, ROC-AUC |
| 5 | Tree-Based Models | Ensemble Learning, Feature Importance | Random Forest, XGBoost, GraphViz |
| 6 | K-Nearest Neighbors | Distance-Based Classification, PCA | Scikit-learn, Matplotlib |
| **7** | **Credit Card Fraud Detection** | **Anomaly Detection & Supervised Learning** | **Python, XGBoost, Streamlit, SHAP** |
| **8** | **Real-Time ASL Recognition** | **Computer Vision & Gesture Classification** | **Python, MediaPipe, OpenCV, TensorFlow** |

---

## 🔎 Detailed Task Summaries

### Task 1: Data Cleaning & Preprocessing
🔗 [View Full Task](https://github.com/Anishraj2005/Anish_Intern_Elvlabs_AIML/tree/main/Task-1-Data-Cleaning)

**Objective:** Clean and prepare the raw UNSW-NB15 network intrusion dataset for machine learning.

**Steps:** Median imputation (numerical), mode imputation (categorical), one-hot encoding for `proto`/`service`, ordinal encoding for `state`, IQR-based outlier capping (Winsorising), and `StandardScaler` normalisation.

**Outcome:** Preserved all 82,332 training rows; increased feature count from 45 to 185 after encoding; produced `UNSW_NB15_training_cleaned.csv` and `UNSW_NB15_testing_cleaned.csv` with zero data leakage.

**Key Learning:** Outlier capping retains attack patterns while limiting noise – essential for intrusion detection.

---

### Task 2: Exploratory Data Analysis (UNSW-NB15)
🔗 [View Full Task](https://github.com/Anishraj2005/Anish_Intern_Elvlabs_AIML/tree/main/Task-2-EDA)

**Objective:** Perform in-depth EDA on the cleaned UNSW-NB15 data to guide modelling.

**Findings:** Slight class imbalance (55% attack, 44% normal); `Generic` and `Exploits` dominate attack categories; strong right-skew in numeric features; `sttl`, `rate`, `sload` most correlated with `label`.

**Outcome:** Pairplots and scatter plots revealed clear separability between normal and attack traffic, especially using TTL and rate features.

**Key Learning:** Linear models are insufficient – tree-based or neural networks are recommended for intrusion detection.

---

### Task 3: Linear Regression – House Price Prediction
🔗 [View Full Task](https://github.com/Anishraj2005/Anish_Intern_Elvlabs_AIML/tree/main/Task-3-Linear-Regression)

**Objective:** Build simple and multiple linear regression models to predict house prices (`Housing.csv`).

**Outcome:** Simple (area-only) R² = 0.27; multiple (all features) R² = 0.65. Residual analysis showed heteroscedasticity and non-normality. **Critical finding:** 5-fold cross-validation produced strongly negative R² (mean -9.91), revealing severe overfitting.

**Key Learning:** Linear regression assumptions can be violated; cross-validation is vital to detect overfitting before trusting a model.

---

### Task 4: Logistic Regression – Breast Cancer Classification
🔗 [View Full Task](https://github.com/Anishraj2005/Anish_Intern_Elvlabs_AIML/tree/main/Task-4-Logistic-Regression)

**Objective:** Classify breast tumours as malignant or benign using the Wisconsin dataset.

**Outcome:** Accuracy = 96.5%, ROC-AUC = 0.996. Threshold tuning (optimal at 0.24) improved F1-score. Visualised the sigmoid function and confusion matrix.

**Key Learning:** Logistic regression works excellently on well-separated medical data; threshold adjustment trades off precision vs. recall (critical for cancer detection).

---

### Task 5: Tree-Based Models – Heart Disease Classification
🔗 [View Full Task](https://github.com/Anishraj2005/Anish_Intern_Elvlabs_AIML/tree/main/Task-5-Tree-Based-Models)

**Objective:** Predict heart disease using Decision Tree, Random Forest, Extra Trees, and Gradient Boosting.

**Outcome:** Random Forest and Extra Trees achieved **100% test accuracy**; Gradient Boosting 97.6%. Feature importance highlighted `cp` (chest pain), `thalach` (heart rate), and `ca` (vessel count) as top predictors. Decision tree visualisation (depth 9) provided interpretable rules.

**Key Learning:** Ensemble methods dramatically outperform single trees; feature importance offers clinical insights.

---

### Task 6: K-Nearest Neighbors – Iris Classification
🔗 [View Full Task](https://github.com/Anishraj2005/Anish_Intern_Elvlabs_AIML/tree/main/Task-6-KNN)

**Objective:** Classify iris species using KNN with hyperparameter tuning and PCA visualisation.

**Outcome:** Default k=5 gave 93.3% accuracy; GridSearchCV found best parameters (`k=17`, `weights='distance'`, `metric='euclidean'`) with CV accuracy 97.5% and test accuracy 96.7%. Decision boundaries visualised after PCA showed clear separation for Setosa and more complex boundaries for Versicolor/Virginica.

**Key Learning:** Scaling is essential for distance-based algorithms; larger k with distance weighting can improve generalisation.

---

## 📁 Projects

### Project 1: Credit Card Fraud Detection
🔗 [View Branch](https://github.com/Anishraj2005/Anish_Intern_Elvlabs_AIML/tree/Project-1-Credit-Card-Fraud-Detection)

**Objective:** Identify fraudulent transactions using anomaly detection and supervised learning.

**Tools:** Python, Scikit-Learn, XGBoost, Pandas, Streamlit, SHAP

**Key Highlights:**
- Compared 3 models: Isolation Forest, LOF, and calibrated XGBoost
- Achieved **86.2% F1-Score** and **97.7% ROC-AUC** on highly imbalanced data (578:1)
- Built interactive Streamlit dashboard with dynamic threshold control and SHAP explainability
- Generated synthetic test data for instant validation

**Deliverables:** Jupyter notebook, Streamlit UI, confusion matrices, ROC/PR curves

---

### Project 2: Real-Time ASL Alphabet Recognition
🔗 [View Branch](https://github.com/Anishraj2005/Anish_Intern_Elvlabs_AIML/tree/Project-2-Real-Time-Sign-Language-Recognition)

**Objective:** Convert hand gestures (A-Z) to text in real-time from webcam feed.

**Tools:** Python, OpenCV, MediaPipe, TensorFlow, scikit-learn, pyttsx3

**Key Highlights:**
- Extracted 21 hand landmarks per frame using MediaPipe Tasks API
- Trained 1D-CNN (TensorFlow) and MLP (scikit-learn) on normalized landmark features
- Achieved **99.8% test accuracy** with only 3 misclassifications across 26 classes
- Built debounce logic (LetterStabilizer + SentenceBuilder) for natural fingerspelling
- Optional text-to-speech output and camera-free demo video generation

**Deliverables:** Model code, webcam script, demo video, project report

---

## 🌟 Why Hire Me?

- **Complete ML Pipeline Experience:** From raw data cleaning to model tuning and evaluation – I've done it all.
- **Deep Understanding of Model Limitations:** Detected overfitting (Task 3), used cross-validation (Tasks 3, 5, 6), and tuned thresholds (Task 4).
- **Cybersecurity-Aware:** Chose UNSW-NB15 for tasks 1-2 because I'm passionate about applying AI to intrusion detection.
- **Ensemble & Distance-Based Proficiency:** Worked with Random Forest, XGBoost, KNN, and logistic regression.
- **Real-World Project Deployment:** Built production-ready Streamlit dashboards and real-time inference pipelines.
- **Professional Documentation:** Every task and project includes detailed READMEs, visualisations, and reproducibility files.

---

## 📈 Key Skills Demonstrated

- **Data Preprocessing:** Missing value imputation, one-hot/ordinal encoding, outlier capping (IQR), standardisation.
- **Exploratory Data Analysis:** Summary statistics, skewness/kurtosis, correlation matrices, pairplots, boxplots, scatter plots.
- **Regression:** Simple/multiple linear regression, residual diagnostics, regularisation (Ridge/Lasso), cross-validation.
- **Classification:** Logistic regression (sigmoid, ROC-AUC, threshold tuning), decision trees, random forest, extra trees, gradient boosting, KNN.
- **Anomaly Detection:** Isolation Forest, Local Outlier Factor for fraud detection.
- **Deep Learning:** 1D-CNN architecture design, landmark-based gesture recognition.
- **Computer Vision:** MediaPipe hand tracking, OpenCV real-time video processing.
- **Model Evaluation:** Accuracy, precision, recall, F1-score, confusion matrix, learning curves, grid search, PCA visualisation.
- **Deployment:** Streamlit dashboards, real-time webcam inference, model serialization (joblib).
- **Tools & Environment:** Python 3.12, Jupyter Notebook, Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn, Plotly, GraphViz, TensorFlow, XGBoost, SHAP, Streamlit.

---

*Thank you for reviewing my AIML internship portfolio!*

*⭐ If you found this portfolio helpful, please give it a star!*
