# Exploratory Data Analysis (EDA) – Unsupervised ML

## Dataset Overview

* **Dataset**: Mall Customers (Kaggle)
* **Objective**: Understand customer characteristics and structure the data for unsupervised learning (clustering).
* **Type of Problem**: Unsupervised Machine Learning (No target variable)

---

## Dataset Structure

* **Rows**: ~200 customers

* **Columns**:

  * `CustomerID` (Identifier)
  * `Gender` (Categorical)
  * `Age` (Numerical)
  * `Annual Income (k$)` (Numerical)
  * `Spending Score (1–100)` (Numerical)

* `CustomerID` was identified as a non-informative identifier and excluded from modeling.

---

## Missing Value Analysis

* No missing values were observed across any features.
* No imputation or row/column removal was required.

---

## Feature Type Identification

* **Categorical Features**:

  * `Gender`
* **Numerical Features**:

  * `Age`
  * `Annual Income (k$)`
  * `Spending Score (1–100)`

---

## Univariate Analysis

### Numerical Features

* **Age**:

  * Reasonable spread across adult age groups
  * No extreme or invalid values

* **Annual Income (k$)**:

  * Moderate spread
  * Slight right skew but within acceptable range

* **Spending Score (1–100)**:

  * Broad distribution
  * Good variance, useful for customer segmentation

### Categorical Feature

* **Gender**:

  * Balanced distribution
  * No rare or noisy categories

---

## Bivariate / Multivariate Analysis

### Correlation Matrix (Numerical Features)

* `Age` vs `Spending Score`: Weak negative correlation (~ -0.33)
* `Annual Income` vs other features: Near-zero correlation

**Conclusion**:

* No strong linear relationships between features
* Low multicollinearity
* Features provide complementary information, which is suitable for clustering

---

## Outlier Analysis

* Boxplots showed no extreme or invalid outliers
* All observed values appear to be realistic customer behaviors
* Outliers (if any) were retained, as they may represent meaningful customer segments

---

## Scaling Decision

* Features are on different scales (Age vs Income vs Spending Score)
* **Standardization (StandardScaler)** was applied
* Scaling is critical for distance-based algorithms such as K-Means

---

## Dimensionality Consideration

* The dataset contains only **3 numerical features** after dropping identifiers
* This is considered **low-dimensional data**
* **PCA is not required** for dimensionality reduction
* PCA may optionally be used for **2D visualization**, not for modeling

---

## Key EDA Conclusions

* Dataset is clean and well-structured
* No missing values or severe data quality issues
* Features are weakly correlated and informative
* Suitable for clustering without aggressive preprocessing

---

## Next Steps

* Encode categorical variable (`Gender`) if required
* Apply clustering algorithms (K-Means, Hierarchical Clustering)
* Determine optimal number of clusters (Elbow Method, Silhouette Score)
* Interpret customer segments

---

**EDA Outcome**: The dataset is ready for unsupervised learning and customer segmentation modeling.
