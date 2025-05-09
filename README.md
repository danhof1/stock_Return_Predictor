# Rockem-Stockem Correlationbots

This repository includes two Jupyter notebooks that explore different approaches to analyzing and modeling stock returns using Kaggle datasets: a UMAP-based dimensionality reduction approach and a traditional statistical approach.

## Notebooks

* **UMAPApproach.ipynb**: Applies UMAP for dimensionality reduction on numeric features before modeling.
* **statisticsApproach.ipynb**: Uses standard statistical methods for feature exploration and baseline modeling.

## Goals

* Compare the effectiveness of dimensionality reduction (UMAP) versus traditional statistical analysis in capturing predictive signals for stock returns.
* Evaluate model performance and feature correlations on the 2024 Kaggle dataset and assess generalization to the 2025 public dataset.

## Methods

### UMAP Approach

1. Download the Kaggle 2024 and 2025 datasets using `gdown`.
2. Load the data and separate numeric features from the `RETURN` target.
3. Scale features with `StandardScaler`.
4. Apply UMAP (`n_components=28`, `n_neighbors=15`, `min_dist=0.1`) to reduce feature dimensionality.
5. Train an XGBoost regressor on the 2024 training set (`80/20` split) and compute Information Coefficient (IC) on the test set.
6. Predict on the 2025 public dataset and compute IC.
7. Compute and save a Spearman correlation matrix of original features.

### Statistical Approach

1. Download the Kaggle 2024 and 2025 datasets (same as above).
2. Load data and isolate numeric features and the `RETURN` target.
3. Compute a Spearman correlation matrix and visualize it as a heatmap.
4. Train an XGBoost regressor with default hyperparameters or with `GridSearchCV` on the 2024 training set.
5. Evaluate model performance with Mean Squared Error (MSE) and R-squared on the 2025 dataset.
6. Compute IC for both 2024 test set and 2025 public dataset.

## Results

| Approach        | 2024 IC | 2025 IC  | 2025 MSE | 2025 R²  |
| --------------- | ------- | -------- | -------- | -------- |
| **UMAP**        | 0.20807 | -0.11982 | N/A      | N/A      |
| **Statistical** | 0.13093 | 0.15001  | 0.001029 | 0.021503 |

* The UMAP-based model shows moderate IC on the 2024 test set but fails to generalize to the 2025 data (negative IC).
* The standard statistical model yields lower 2024 IC but a positive generalization signal on 2025, with modest R².

## Potential Limitations

* **Dataset Size**: The dataset (\~1,000 samples) is small for high-dimensional modeling. Removing outliers can significantly impact results.
* **Model Complexity**: Hyperparameter tuning and model selection may be limited due to computational constraints.
* **Evaluation Metrics**: IC and R² provide only partial insight; additional metrics (e.g., MAE, Sharpe ratio) may offer further understanding.

## Conclusions & Next Steps

* Traditional statistical modeling provided more stable generalization compared to the UMAP approach in this project.
* Future work could include:

  * Hyperparameter optimization for both approaches.
  * Ensembling multiple models.
  * Incorporating time-series cross-validation.
  * Testing different dimensionality reduction techniques (PCA, t-SNE).
