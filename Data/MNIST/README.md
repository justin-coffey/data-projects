# Biased MNIST Dataset - Dimensionality Reduction

This README explains the contents of the CSV files in the `Data` directory, which contain dimensionality reduction results from the Biased MNIST dataset. These files are ready for visualization and analysis.

## Dataset Overview

The Biased MNIST dataset contains modified MNIST handwritten digits with controlled biases. Each image contains:
- A digit (0-9)
- Various auxiliary features (color, position, background texture)

Three bias levels were analyzed:
- `full_0.1`: Low correlation between digits and auxiliary features
- `full_0.5`: Medium correlation 
- `full_0.99`: High correlation

The higher the bias level, the stronger the correlation between digit classes and auxiliary features.

## Data Files

The `Data` directory contains CSV files with preprocessed dimensionality reduction results:

### combined_pca.csv

Principal Component Analysis (PCA) results across all bias levels.

| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| PC1, PC2, PC3, ... | float | Principal component coordinates (up to PC50) |
| label       | integer  | Digit class (0-9) |
| bias_level  | string   | Bias level (full_0.1, full_0.5, full_0.99) |

### combined_pacmap.csv

PACMAP (Pairwise Controlled Manifold Approximation) results across all bias levels.

| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| PACMAP1     | float     | First PACMAP embedding dimension |
| PACMAP2     | float     | Second PACMAP embedding dimension |
| PACMAP3     | float     | Third PACMAP embedding dimension |
| label       | integer   | Digit class (0-9) |
| bias_level  | string    | Bias level (full_0.1, full_0.5, full_0.99) |

### combined_umap.csv

UMAP (Uniform Manifold Approximation and Projection) results across all bias levels.

| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| UMAP1       | float     | First UMAP embedding dimension |
| UMAP2       | float     | Second UMAP embedding dimension |
| UMAP3       | float     | Third UMAP embedding dimension |
| label       | integer   | Digit class (0-9) |
| bias_level  | string    | Bias level (full_0.1, full_0.5, full_0.99) |

### dataset_summary.csv

Summary statistics about the analyzed datasets.

| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| bias_level  | string    | Bias level |
| num_samples | integer   | Number of samples |
| image_shape | string    | Shape of the original images |
| num_classes | integer   | Number of unique classes (10) |
| data_type   | string    | Data type of the images |
| digit       | integer   | Digit class (0-9) - in distribution rows only |
| count       | integer   | Count of samples for each digit |
| percentage  | float     | Percentage of samples for each digit |

When visualizing this data, consider:

1. **Comparing bias levels**: Use color or separate plots to see how bias affects clustering
2. **Digit separation**: Color by digit class to see separation quality
3. **Comparing techniques**: Create equivalent plots across PCA/PACMAP/UMAP to compare effectiveness
4. **2D vs 3D**: Try both 2D (faster, clearer) and 3D (more information) visualizations
5. **Individual vs combined**: Look at individual bias levels first, then combined views

The `bias_level` column is crucial for understanding how the different bias levels compare in the reduced dimensional space.
