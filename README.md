# 🔍 AIML Internship – Task 2: Exploratory Data Analysis (UNSW‑NB15)

## 🎯 Objective  
Perform an in‑depth exploratory data analysis on the cleaned UNSW‑NB15 dataset to:

- Understand the data distribution and class balance  
- Identify key features that separate normal and attack traffic  
- Detect correlations and patterns among features  
- Visualise anomalies and prepare insights for modelling  

The final output is a comprehensive analysis report and a set of visualisations that inform feature engineering and model selection for intrusion detection.

---

## 🛠️ Tools & Environment  
- **Python 3.12**  
- **Jupyter Notebook** (VS Code)  
- **Libraries**:  
  - `pandas`, `numpy` – data manipulation  
  - `matplotlib`, `seaborn` – static visualisations  
  - `plotly` – interactive plots (optional)  
  - `scipy.stats` – skewness, kurtosis  

---

## 📂 Dataset  
The cleaned dataset from **Task 1** is used:

- `UNSW_NB15_training_cleaned.csv` – 82,332 rows, 185 columns (after one‑hot encoding)  
- `UNSW_NB15_testing_cleaned.csv` – 175,341 rows (used only for future modelling)

All features are preprocessed: missing values imputed, categorical variables encoded, outliers capped, and numerical features standardised.

---

## 📊 Key EDA Steps & Visualisations  

### 1. Summary Statistics & Skewness  
- Computed mean, standard deviation, quartiles, skewness, and kurtosis for 12 numeric features.  
- Most numeric features (e.g., `sbytes`, `dbytes`, `rate`, `sload`) are **highly right‑skewed**.  
- Log transformation or further scaling may be needed for linear models.

### 2. Class Distribution (Binary)  
![Class Distribution](Output_Graphs/output%20of%20cell%205.png)  
- **Normal**: ~37,000 (44.9%)  
- **Attack**: ~45,332 (55.1%)  
- The dataset is **slightly imbalanced** but not extreme – no heavy resampling required, though class‑weighted learning can help.

### 3. Attack Category Distribution  
![Attack Categories](Output_Graphs/output%20of%20cell%206.png)  
- `Generic` and `Exploits` dominate the attack classes.  
- `Worms`, `Shellcode`, and `Backdoor` are rare – **multiclass imbalance** may cause poor detection for these types.  
- Class‑wise evaluation (precision, recall, F1) is essential.

### 4. Histograms of Key Numeric Features  
![Histograms](Output_Graphs/output%20of%20cell%207.png)  
- All features show heavy right skew and long tails.  
- `sttl` and `dttl` have discrete peaks (common TTL values: 64, 128, 255).  
- Outliers are present – capping (already done) helps stabilise models.

### 5. Boxplots After Winsorising  
![Boxplots After Capping](Output_Graphs/output%20of%20cell%208.png)  
- Outliers are capped but some extreme values remain (e.g., `rate`).  
- Winsorising preserved all rows while reducing the influence of extreme noise.

### 6. Correlation Matrix  
![Correlation Matrix](Output_Graphs/output%20of%20cell%209.png)  
- **Strong positive correlations**:  
  - `rate` ↔ `sload` (0.93) – higher packet rate → higher load.  
  - `sinpkt` ↔ `sjit` (0.87) – larger intervals → higher jitter.  
- **Strong negative correlations**:  
  - `sttl` ↔ `dload` (-0.82) – TTL inversely related to destination load.  
- **Correlation with label**:  
  - `sttl` (0.50), `rate` (0.45), `sload` (0.41) are the most informative single features.  
  - No feature is perfectly predictive → **non‑linear models** (Random Forest, XGBoost, neural nets) are recommended.

### 7. Pairplot (Normal vs Attack)  
![Pairplot](Output_Graphs/output%20of%20cell%2010.png)  
- Attack samples exhibit more spread in `rate` and distinct TTL clusters.  
- `sbytes` vs `dbytes` show heavy overlap – byte counts alone are insufficient.  
- Partial separation between classes suggests that tree‑based models can learn decision boundaries.

### 8. Scatter Plots for Anomaly Detection  
![Scatter Plots](Output_Graphs/output%20of%20cell%2011.png)  
- **sload vs dload (log scale)**: Attack samples populate high‑load regions – useful for detecting DoS, scanning, and flood attacks.  
- **sttl vs dttl**: Distinct clusters reflect OS and tool‑specific TTL patterns – strong discriminative power.

> 📌 *For a detailed interpretation of each graph, refer to [`Information of the graphs.md`](Output_Graphs/Information%20of%20the%20graphs.md).*

---

## 🧠 Key Insights & Modelling Implications  

| Finding | Implication |
|---------|--------------|
| Slight class imbalance (55% attack) | No severe resampling needed; use class weights. |
| Attack categories imbalanced | Monitor per‑class metrics, especially for rare types. |
| Features are right‑skewed | Consider log transforms or use tree‑based models. |
| Outliers are capped (Winsorised) | Model stability improved, all rows retained. |
| Weak linear correlation with label | Non‑linear models (RF, XGBoost, MLP) will outperform linear classifiers. |
| TTL and rate features are most informative | Prioritise `sttl`, `rate`, `sload`, `dload` in feature selection. |
| Visual separation in scatter plots | Attack detection is feasible with proper feature engineering. |

---

## 📁 Files In The Repository  

| File | Description |
|------|-------------|
| `EDA_of_UNSWNB15_cleaned_data.ipynb` | Full Jupyter notebook with all EDA steps and visualisations. |
| `EDA_of_UNSWNB15_cleaned_data.pdf` | Exported PDF – viewable directly on GitHub. |
| `UNSW_NB15_cleaned.zip` | Cleaned training and test CSVs from Task 1. |
| `Output_Graphs/` | Directory containing all generated plots (`.png`). |
| `Output_Graphs/Information of the graphs.md` | Detailed textual interpretation of each visualisation. |
| `README.md` | This documentation. |
| `requirements.txt` | Required Python packages. |

> **Note**: The `.ipynb` may not render fully on GitHub; please download or use the PDF.

---

## ✅ Conclusion  

The EDA reveals that the UNSW‑NB15 dataset is well‑prepared for classification, with clear separability between normal and attack traffic in several feature subspaces (`sttl`, `rate`, `sload`). However, the relationships are non‑linear, and the data is skewed. These insights guide the next steps:

- **Next Step (Task 3)**: Build and evaluate machine learning models.  
- Recommended algorithms: Random Forest, XGBoost, LightGBM, or a small neural network.  
- Evaluation focus: Precision, recall, F1‑score, and per‑class performance (especially for rare attacks).  

The cleaned data and EDA findings provide a solid foundation for developing a robust intrusion detection system.

---

## 📚 References  

- [UNSW‑NB15 Dataset](https://research.unsw.edu.au/projects/unsw-nb15-dataset)  
- [Pandas & Seaborn Documentation](https://pandas.pydata.org/)  
- [Scikit‑learn Preprocessing](https://scikit-learn.org/stable/modules/preprocessing.html)  
- [IQR Outlier Detection](https://en.wikipedia.org/wiki/Interquartile_range)
