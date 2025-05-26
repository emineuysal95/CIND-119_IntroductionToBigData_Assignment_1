# CIND119_IntroductionToBigData_Assignment_1
# Heart Disease Clustering Analysis

This project presents a clustering analysis of a heart disease dataset using SAS procedures, particularly focusing on `FASTCLUS`, which performs K-means clustering. The objective is to segment patients into meaningful groups based on medical attributes and identify patterns that may relate to heart disease risk.

📁 Dataset Summary

The dataset consists of **303 observations** and includes the following key variables:

- `age`: Age of the patient
- `sex`: Biological sex (1 = male, 0 = female)
- `cp`: Chest pain type (categorical)
- `trestbps`: Resting blood pressure
- `chol`: Serum cholesterol
- `fbs`: Fasting blood sugar
- `restecg`: Resting electrocardiographic results
- `thalach`: Maximum heart rate achieved
- `exang`: Exercise-induced angina
- `oldpeak`: ST depression
- `slope`: Slope of the peak exercise ST segment
- `ca`: Number of major vessels colored by fluoroscopy
- `thal`: Thalassemia indicator
- `target`: Presence of heart disease (1 = present, 0 = absent)

⚙️ Analysis Steps

1. Data Standardization
All variables were standardized using Z-score transformation. This ensures each variable contributes equally to the distance calculations during clustering.

2. K-means Clustering (FASTCLUS)
Clustering was performed for different values of `K` (number of clusters) from **K=2** to **K=5**. Evaluation metrics include:

- **Pseudo F Statistic**: Measures separation between clusters (higher is better).
- **R-Square**: Indicates how much of the total variance is explained by the clustering.
- **Cubic Clustering Criterion (CCC)**: Helps determine the optimal number of clusters.

3. Evaluation Summary

| K value | R-Square | Pseudo F | Comment |
|---------|----------|----------|---------|
| 2       | 0.072    | 23.46    | Low separation, not very informative |
| 3       | 0.198    | 37.16    | Good balance between separation and interpretability ✅ |
| 4       | 0.223    | 28.68    | Higher R² but more complexity |
| 5       | 0.261    | 26.33    | Highest R², but cluster sizes are unbalanced |

Based on these results, **K=3** is recommended as the most practical model.

🔍 Key Findings

- The clustering identified patient subgroups with distinct patterns in `thalach`, `oldpeak`, and `target`.
- Certain clusters showed higher heart disease presence (target = 1), suggesting potential risk profiles.
- Standardized cluster means allow for interpretation of variable importance in each group.

📌 Notes

- The data was analyzed using **SAS** (FASTCLUS Procedure).
- The variables are **correlated**, so metrics like CCC should be interpreted with caution (as noted by SAS warnings).

🧠 Future Improvements

- Incorporate dimensionality reduction (e.g., PCA) to address multicollinearity.
- Use cluster labels to predict risk or compare with actual heart disease diagnoses.
- Visualize clusters with 2D/3D plots for better intuition.

---

Author: Emine Uysal   
Assignment_1: Clustering Analysis  
Date: October 2024
