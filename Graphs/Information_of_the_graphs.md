# 1. Confusion Matrix – Random Forest

## Overview
The confusion matrix evaluates the performance of the Random Forest classifier by comparing actual class labels with predicted class labels.

| Actual Class | Predicted No Disease (0) | Predicted Disease (1) |
|-------------|-------------------------|----------------------|
| No Disease (0) | 100 | 0 |
| Disease (1) | 0 | 105 |

## Interpretation

- **True Negatives (TN) = 100**
  - 100 healthy patients were correctly classified as healthy.

- **False Positives (FP) = 0**
  - No healthy patient was incorrectly classified as having heart disease.

- **False Negatives (FN) = 0**
  - No patient with heart disease was incorrectly classified as healthy.

- **True Positives (TP) = 105**
  - 105 patients with heart disease were correctly identified.

## Performance Metrics

### Accuracy

$$
Accuracy = \frac{TP + TN}{TP + TN + FP + FN}
$$

$$
= \frac{105 + 100}{205}
= 1.0
$$

**Accuracy = 100%**

### Precision

$$
Precision = \frac{TP}{TP + FP}
$$

$$
= \frac{105}{105 + 0}
= 1.0
$$

**Precision = 100%**

### Recall

$$
Recall = \frac{TP}{TP + FN}
$$

$$
= \frac{105}{105 + 0}
= 1.0
$$

**Recall = 100%**

### F1-Score

$$
F1 = 2 \times \frac{Precision \times Recall}{Precision + Recall}
$$

$$
= 1.0
$$

**F1-Score = 100%**

## Conclusion

The Random Forest model achieved perfect classification on the test dataset, correctly identifying every healthy and diseased patient without any errors. This indicates excellent predictive performance, although such perfect accuracy may also suggest that the dataset is relatively easy to classify or that further validation on unseen data is necessary.

---

# 2. Decision Tree: Training vs Testing Accuracy by Max Depth

## Overview

This graph illustrates how the training and testing accuracy of the Decision Tree model change as the maximum depth of the tree increases.

## Observations

### Depth 1–2

- Training Accuracy ≈ 77%
- Testing Accuracy ≈ 72%

The model is too simple and unable to capture complex relationships in the data.

**Result:** Underfitting

### Depth 3–5

- Training Accuracy increases from 84% to 93%.
- Testing Accuracy increases from 85% to 87%.

The model begins learning meaningful decision boundaries and improves generalization.

### Depth 6–8

- Training Accuracy increases to nearly 100%.
- Testing Accuracy improves significantly to approximately 97%.

The model captures most patterns while still maintaining strong performance on unseen data.

### Depth 9–15

- Training Accuracy reaches 100%.
- Testing Accuracy stabilizes around 98.5%.

Performance no longer improves significantly after depth 9.

## Interpretation

The gap between training and testing accuracy remains very small, indicating minimal overfitting.

The optimal tree depth appears to be around:

$$
\text{Max Depth} = 9
$$

where testing accuracy reaches its highest stable value.

## Conclusion

Increasing tree depth improves predictive performance up to a certain point. Beyond depth 9, the model becomes more complex but provides negligible gains, making depth 9 the best trade-off between complexity and accuracy.

---

# 3. Decision Tree Visualization (Max Depth = 4)

## Overview

This figure shows the structure of a Decision Tree used for heart disease prediction with a maximum depth of 4.

Each node contains:

- Splitting condition
- Gini impurity
- Number of samples
- Class distribution
- Predicted class

## Root Node

### Split Condition

$$
cp \le 0.5
$$

This indicates that **Chest Pain Type (cp)** is the most important feature for the first split.

- Left branch → Mostly No Disease
- Right branch → Mostly Disease

## Important Splitting Features

The tree uses several medical attributes:

### cp (Chest Pain Type)

- Appears at the root node.
- Most influential feature for separating healthy and diseased patients.

### age

- Used multiple times.
- Older patients generally show higher disease risk.

### oldpeak

- Measures ST depression induced by exercise.
- Higher values often indicate cardiac abnormalities.

### thal

- Represents thalassemia test results.
- Frequently used to distinguish disease classes.

### chol

- Cholesterol level.
- Helps refine classifications.

### trestbps

- Resting blood pressure.
- Provides additional diagnostic information.

### sex

- Used in later decision branches.

### exang

- Exercise-induced angina.
- Helps separate high-risk patients.

## Color Interpretation

### Orange Nodes

Represent:

$$
\text{No Disease (0)}
$$

### Blue Nodes

Represent:

$$
\text{Disease (1)}
$$

Darker colors indicate greater purity and stronger confidence in the prediction.

## Example Decision Rule

A simplified path from the tree:

```
cp ≤ 0.5
→ thal ≤ 2.5
→ oldpeak ≤ 0.65
→ Predict No Disease
```

Another path:

```
cp > 0.5
→ age > 56.5
→ oldpeak > 3.55
→ Predict Disease
```

## Conclusion

The decision tree demonstrates how clinical features are sequentially used to classify patients. Chest pain type acts as the primary decision factor, while age, thalassemia results, cholesterol, blood pressure, and exercise-related indicators further refine the prediction.

---

# 4. Feature Importance – Random Forest

## Overview

This graph shows the relative importance of each feature in the Random Forest model.

Higher values indicate greater contribution to prediction accuracy.

## Feature Ranking

| Rank | Feature | Importance |
|--------|---------|-----------|
| 1 | cp | 0.142 |
| 2 | thalach | 0.117 |
| 3 | ca | 0.115 |
| 4 | oldpeak | 0.112 |
| 5 | thal | 0.096 |
| 6 | age | 0.091 |
| 7 | chol | 0.078 |
| 8 | exang | 0.074 |
| 9 | trestbps | 0.068 |
| 10 | slope | 0.049 |
| 11 | sex | 0.027 |
| 12 | restecg | 0.020 |
| 13 | fbs | 0.010 |

## Interpretation of Top Features

### cp (Chest Pain Type)

Most influential predictor.

Different chest pain patterns are strongly associated with heart disease diagnosis.

### thalach (Maximum Heart Rate Achieved)

Higher or abnormal heart rates provide valuable diagnostic information.

### ca (Number of Major Vessels)

Indicates the extent of coronary artery blockage and is highly predictive.

### oldpeak

Measures ST depression during exercise.

Higher values often suggest cardiovascular abnormalities.

### thal

Reflects blood flow and oxygen transport abnormalities linked to heart disease.

## Interpretation of Low-Importance Features

### fbs (Fasting Blood Sugar)

Contributes the least to prediction.

### restecg

Provides only limited additional information.

### sex

Has some influence but is less important than clinical measurements.

## Conclusion

The Random Forest model relies primarily on clinical indicators such as chest pain type, maximum heart rate, number of affected vessels, ST depression, and thalassemia results. These features contribute most to distinguishing between healthy and diseased patients, while fasting blood sugar and ECG measurements have relatively minor influence.
