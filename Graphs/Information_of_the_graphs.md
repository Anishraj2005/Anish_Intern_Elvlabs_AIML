# Logistic Regression Model Evaluation

These three graphs are commonly used to evaluate and explain a **Logistic Regression model**.

---

# 1. Confusion Matrix

## What it Shows

A confusion matrix compares the model's predicted classes against the actual classes.

| Actual / Predicted | Benign | Malignant |
|-------------------|--------|------------|
| Benign            | 71     | 1          |
| Malignant         | 3      | 39         |

## Interpretation

### True Negatives (TN) = 71
Benign tumors correctly classified as benign.

### False Positives (FP) = 1
Benign tumor incorrectly classified as malignant.

### False Negatives (FN) = 3
Malignant tumor incorrectly classified as benign.

### True Positives (TP) = 39
Malignant tumors correctly classified as malignant.

## Performance Metrics

### Accuracy

### Accuracy

$$
Accuracy = \frac{TP+TN}{TP+TN+FP+FN}
= \frac{39+71}{39+71+1+3}
= \frac{110}{114}
= 96.49\%
$$

### Precision

$$
Precision = \frac{TP}{TP+FP}
= \frac{39}{39+1}
= 97.5\%
$$

### Recall (Sensitivity)

$$
Recall = \frac{TP}{TP+FN}
= \frac{39}{39+3}
= 92.86\%
$$

## Conclusion

The confusion matrix shows that the model performs extremely well, correctly classifying **110 out of 114 samples**. Only **4 predictions are incorrect**, indicating strong classification capability.

---

# 2. ROC Curve

## What it Shows

The **Receiver Operating Characteristic (ROC) Curve** evaluates how well the model distinguishes between classes across different classification thresholds.

## Axes

### X-axis: False Positive Rate (FPR)

$$
FPR = \frac{FP}{FP + TN}
$$

### Y-axis: True Positive Rate (TPR)

$$
TPR = \frac{TP}{TP + FN}
$$

## Understanding the Graph

- The **dashed diagonal line** represents a random classifier.
- The **orange curve** represents Logistic Regression.
- Curves closer to the **top-left corner** indicate better performance.

## AUC Score

The graph shows:

$$
AUC = 0.996
$$

where **AUC** stands for **Area Under the Curve**.

## Meaning of AUC

| AUC Value | Interpretation |
|------------|---------------|
| 0.50 | Random guessing |
| 0.60–0.70 | Fair |
| 0.70–0.80 | Good |
| 0.80–0.90 | Very Good |
| 0.90–1.00 | Excellent |

## Conclusion

An **AUC of 0.996** indicates nearly perfect class separation. The model can distinguish benign and malignant tumors with extremely high reliability.

---

# 3. Sigmoid Function

## What it Shows

The sigmoid function is the mathematical foundation of Logistic Regression.

It converts any real-valued input into a probability between **0 and 1**.

## Formula

$$
\sigma(z)=\frac{1}{1+e^{-z}}
$$

where:

z = Linear combination (weighted sum) of input features.
σ(z) = Predicted probability obtained after applying the sigmoid function.

## Graph Interpretation

When:

$$
z \ll 0
$$

the probability approaches:

$$
0
$$

The model predicts **Benign**.

---

### Center Point

At:

$$
z = 0
$$

$$
\sigma(z) = 0.5
$$

The red dashed lines indicate the **decision boundary**.

If probability:

- ≥ 0.5 → Malignant
- < 0.5 → Benign

---

### Right Side

When:

$$
z \gg 0
$$

the probability approaches:

$$
1
$$

The model predicts **Malignant**.

## Why Sigmoid is Important

- Converts linear output into probabilities.
- Enables binary classification.
- Provides confidence scores for predictions.

## Conclusion

The sigmoid function transforms the model's linear calculations into probabilities, allowing Logistic Regression to classify tumors as benign or malignant using a threshold of **0.5**.

---

# Overall Interpretation of the Three Graphs

Together, these graphs demonstrate that the Logistic Regression model is highly effective.

- **Confusion Matrix:** 96.49% accuracy with only 4 misclassifications.
- **ROC Curve:** AUC = 0.996, indicating near-perfect discrimination between classes.
- **Sigmoid Function:** Explains how Logistic Regression converts feature values into classification probabilities.

---

# Final Summary for Report

> The Logistic Regression model achieved excellent performance in breast cancer classification. The confusion matrix shows high accuracy with minimal classification errors, while the ROC curve produced an AUC score of 0.996, indicating outstanding class separability. The sigmoid function illustrates how the model converts feature values into probabilities and classifies tumors using a decision threshold of 0.5. Overall, the results confirm that Logistic Regression is highly effective for distinguishing between benign and malignant tumors.
