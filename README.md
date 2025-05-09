# Rockem-Stockem CorrelationBots

A collection of Jupyter notebooks demonstrating two approaches for exploring feature correlations in stock return prediction: a UMAP-based dimensionality reduction pipeline and a traditional statistical analysis pipeline.

## Overview

This repository contains two complementary notebooks:

* **UMAP Approach** (`Copy_of_Rockem_Stockem_Correlationbots_UMAPApproach.ipynb`): Applies Uniform Manifold Approximation and Projection (UMAP) to reduce high-dimensional feature spaces into a lower-dimensional embedding. The notebook then investigates correlations between these UMAP features and target returns, helping identify latent structures and the most predictive embeddings.

* **Statistical Approach** (`Rockem_Stockem_Correlationbots_statisticsApproach.ipynb`): Uses classical statistical methods (e.g., Spearman, Pearson correlations; heatmaps; hypothesis testing) to quantify relationships between original features and returns. It generates correlation matrices, visualizations, and significance tests to highlight the strongest predictors.

## Prerequisites

Ensure you have the following installed:

* Python 3.8 or higher
* Jupyter Notebook or JupyterLab
* Required Python libraries:

  * pandas
  * numpy
  * matplotlib
  * seaborn
  * umap-learn
  * scikit-learn
  * scipy
  * plotly (optional for interactive plots)

You can install dependencies via:

```bash
pip install pandas numpy matplotlib seaborn umap-learn scikit-learn scipy plotly
```

## Repository Structure

```text
├── Copy_of_Rockem_Stockem_Correlationbots_UMAPApproach.ipynb
├── Rockem_Stockem_Correlationbots_statisticsApproach.ipynb
└── README.md
```

## Usage

1. **Clone the repository**:

   ```bash
   ```

git clone <your-repo-url>
cd <your-repo-folder>

````
2. **Launch Jupyter**:
   ```bash
jupyter notebook
````

or

```bash
jupyter lab
```

3. **Open and run** the desired notebook:

   * For UMAP-based analysis: `Copy_of_Rockem_Stockem_Correlationbots_UMAPApproach.ipynb`
   * For statistical analysis: `Rockem_Stockem_Correlationbots_statisticsApproach.ipynb`

## Notebook Descriptions

### UMAP Approach

1. **Data Loading & Preprocessing**: Reads raw feature matrix and target returns.
2. **Dimensionality Reduction**: Applies UMAP to project features into a lower-dimensional space.
3. **Correlation Analysis**: Computes correlation coefficients between UMAP embeddings and returns.
4. **Feature Interpretation**: Identifies top UMAP components most predictive of returns.
5. **Visualization**: Plots embeddings and correlation bars for quick insight.

### Statistical Approach

1. **Data Loading & Cleaning**: Loads the dataset and handles missing values.
2. **Correlation Computation**: Calculates Spearman and Pearson correlation matrices.
3. **Heatmaps**: Visualizes correlation strengths across all features.
4. **Significance Testing**: Performs p-value calculations to assess statistical significance.
5. **Export**: Saves correlation matrices to Excel for further review.

## Contributing

Contributions are welcome! Feel free to open issues or submit pull requests to improve analysis methods or add new features.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
