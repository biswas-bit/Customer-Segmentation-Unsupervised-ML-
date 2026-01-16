# Customer Segmentation Analysis Report
---
## 1.Project Overview
The goal of this analysis was to segment customers based on their Annual Income and Spending Score using an unsupervised machine learning approach. By identifying distinct groups, we can tailor marketing strategies and improve customer retention.

## 2.Methodology
* **Algorithm**: K-Means Clustering.
* **Optimal Clusters ($k$)**: Determined to be 8 using the Elbow Method (minimizing Within-Cluster Sum of Squares).
* **Feature Scaling**: Data was normalized before clustering to ensure income and spending scores were weighted equally.
* **Profiling**: Clusters were labeled by comparing each group's mean feature values against the global average of the dataset.

## 3.Final Cluster Mapping
  ```python

  mapping_dict = {
    0: 'VIP Champions',
    1: 'Elite Champions',
    2: 'Budget-Conscious',
    3: 'Core Customers',
    4: 'Loyal Super-Fans',
    5: 'Aspirational Spenders',
    6: 'Loyal Enthusiasts',
    7: 'Brand Ambassadors'
 } 

  df['Cluster_Name'] = df['Cluster'].map(mapping_dict)
  ```

## 4.Segment Profiles & Strategic Insights

| Cluster | Persona               | Income Level | Spending Level | Strategic Action                                          |
| ------: | --------------------- | ------------ | -------------- | --------------------------------------------------------- |
|   0 & 1 | Champions             | 1.4×         | 1.6×           | Retention: High-end rewards and VIP early access          |
|       7 | Brand Ambassadors     | 1.4×         | 1.6×           | Advocacy: Encourage referrals and social media sharing    |
|       6 | Loyal Enthusiasts     | Average      | 1.2×           | Engagement: Daily deals and “Buy More, Save More” offers  |
|   4 & 5 | Aspirational Spenders | 0.7×         | 1.2×           | Value: Trend-driven marketing and entry-level luxury      |
|       2 | Budget-Conscious      | 0.8×         | 0.8×           | Price: Seasonal clearances and discount-focused campaigns |
|       3 | Core Customers        | Average      | Average        | Stability: Standard updates and consistent service        |

## 5.Mathematical Context
The clusters were defined by minimizing the distance between data points and their respective centroids. The Inertia (WCSS) formula used by the model is:$$\text{Inertia} = \sum_{i=1}^{n} (x_i - \mu_{C_i})^2$$
Where:$x_i$ is the data point.$\mu_{C_i}$ is the centroid of the cluster assigned to $x_i$.