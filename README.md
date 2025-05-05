Syed Mohammed Ahmed | syedmohd2002@gmail.com

# Canadian Household Spending Analysis

This group project explores Canadian household spending behavior using unsupervised clustering and predictive modeling techniques. The goal was to identify meaningful household segments and forecast how much income households allocate to pensions and insurance. The project was completed as part of a machine learning course and involved multiple stages of preprocessing, modeling, and interpretation.

---

## Overview

- **Clustering Techniques:** K-Means, PCA, and UMAP were used to segment households based on demographic and behavioral features.
- **Predictive Modeling:** Elastic Net and XGBoost were employed to predict the proportion of household income spent on pensions and insurance.
- **Model Interpretation:** SHAP analysis was used to understand feature contributions to XGBoost’s predictions.

---

## Key Steps

### 1. Data Cleaning & Preparation
- Removed columns with no variance or direct leakage (e.g., pension & insurance variables during clustering).
- Handled invalid outliers based on domain logic (e.g., negative total expenditure).
- Imputed missing demographic values with medians.
- Removed extreme outliers using z-score thresholding.
- Merged datasets by geographic identifiers and standardized features.

### 2. Clustering and Dimensionality Reduction
- **K-Means:** Applied with silhouette and elbow methods to determine optimal cluster count (k=6).
- **PCA:** Reduced data dimensionality to visualize linear separability of clusters.
- **UMAP:** Used for nonlinear projection, yielding clearer visual separation and subclusters compared to PCA.

### 3. Regression Modeling
- **Elastic Net:** Used as a regularized linear baseline; produced low R² (~0.0) and high MSE.
- **XGBoost:** Nonlinear gradient-boosted model performed substantially better with R² ≈ 0.69–0.72.

### 4. Model Interpretation with SHAP
- Identified top features impacting spending predictions:
  - Household income bracket
  - Proportion of elderly maintainers
  - Single-person households
  - Rental-based utilities
- SHAP plots confirmed complex nonlinear relationships better captured by tree-based models.

---

## Tools and Libraries
- Python (pandas, NumPy, scikit-learn, XGBoost, SHAP, matplotlib, seaborn)
- Jupyter Notebook

---

## Files

- `canadian_spending_analysis.ipynb`  
  Jupyter notebook containing the full analysis, including data cleaning, clustering (K-Means, PCA, UMAP), regression modeling (Elastic Net, XGBoost), and SHAP interpretation.

- `canadian_spending_report.pdf`  
  PDF report summarizing the project methodology, key findings, visualizations (PCA, UMAP, regression diagnostics, SHAP plots), and model evaluation results.

---

## Acknowledgments

This was a group project completed as part of **DS 3000: Introduction to Machine Learning** at Western University. The analysis, modeling, and interpretations were developed collaboratively. This repository reflects my personal contributions and is shared for educational and portfolio purposes.
