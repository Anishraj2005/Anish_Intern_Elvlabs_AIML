# 📊 Information of the Graphs – House Price Prediction

These three images summarize the performance and interpretation of a **house price prediction model** using both **simple linear regression** and **multiple linear regression**.

---

## 1. Feature Importance (Multiple Linear Regression)

### What it shows

The horizontal bars represent the **regression coefficients** of each feature.

- **Positive coefficients** → increase house price.
- **Negative coefficients** → decrease house price.
- Larger absolute values indicate stronger influence.

### Most influential positive features

| Feature                     | Approx. Coefficient | Interpretation                                          |
| --------------------------- | ------------------- | ------------------------------------------------------- |
| Bathrooms                   | +1.10M              | Each additional bathroom strongly increases price.      |
| Air Conditioning            | +0.79M              | Houses with AC tend to be significantly more expensive. |
| Hot Water Heating           | +0.69M              | Adds value to the property.                             |
| Preferred Area (`prefarea`) | +0.63M              | Location has a major positive impact.                   |
| Stories                     | +0.41M              | Multi-story houses are generally more expensive.        |
| Basement                    | +0.39M              | Adds value.                                             |
| Main Road                   | +0.37M              | Better accessibility increases price.                   |
| Guest Room                  | +0.23M              | Positive contribution.                                  |
| Parking                     | +0.22M              | Additional parking increases value.                     |

### Negative features

| Feature        | Approx. Coefficient |
| -------------- | ------------------- |
| Unfurnished    | -0.41M              |
| Semi-furnished | -0.13M              |

These indicate that compared with the baseline furnishing category, less furnished houses tend to sell for lower prices.

### Interesting observation

- **Area** has almost zero visible coefficient.
- **Bedrooms** contribute only slightly (~0.08M).

This suggests that after accounting for other variables, factors like bathrooms, amenities, and location explain more variation in price than bedroom count alone.

---

## 2. Simple Linear Regression: Price vs Area

### What it shows

- Blue points = actual houses.
- Red line = fitted regression line.
- X-axis = Area (sq ft).
- Y-axis = House Price.

### Key insights

1. **Positive relationship**  
   Larger houses generally cost more. The regression line slopes upward.

2. **High variability**  
   Houses with similar area have very different prices.  
   Example: around 6000 sq ft, prices range roughly from 3M to 10M+.

3. **Area alone is insufficient**  
   The scatter is widely spread around the line.  
   Other variables (location, bathrooms, furnishing, parking, etc.) clearly influence price.

### Conclusion

Area is an important predictor, but using only area results in a relatively weak model because many houses deviate substantially from the regression line.

---

## 3. Residual Analysis

### Left Plot: Residuals vs Predicted Values

**Residual formula:**

\[
\text{Residual} = \text{Actual Price} - \text{Predicted Price}
\]

#### Interpretation

- Residuals are mostly scattered around zero.  
  This is generally good because it means predictions are not consistently too high or too low.
- However, there are some large positive residuals (> 5M), indicating a few houses were severely underpredicted.

#### Potential issue

The spread of residuals appears to increase somewhat for higher predicted prices.

This may indicate:
- Mild **heteroscedasticity** (non-constant variance).
- The model struggles more with expensive houses.

---

### Right Plot: Distribution of Residuals

**What we want:**
- Bell‑shaped distribution.
- Centered around zero.

**What we see:**
- Most residuals cluster near zero.
- Distribution is approximately normal.
- Slight right skew caused by a few very large positive residuals.

### Meaning

The model captures the overall trend reasonably well, but there are some expensive properties whose prices are not fully explained by the available features.
