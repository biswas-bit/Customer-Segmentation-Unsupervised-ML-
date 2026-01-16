#Customer Segmentation Analysis Report
---
## 1.Project Overview
The goal of this analysis was to segment customers based on their Annual Income and Spending Score using an unsupervised machine learning approach. By identifying distinct groups, we can tailor marketing strategies and improve customer retention.

## 2.Methodology
* **Algorithm**: K-Means Clustering.
* **Optimal Clusters ($k$)**: Determined to be 8 using the Elbow Method (minimizing Within-Cluster Sum of Squares).
* **Feature Scaling**: Data was normalized before clustering to ensure income and spending scores were weighted equally.
* **Profiling**: Clusters were labeled by comparing each group's mean feature values against the global average of the dataset.
