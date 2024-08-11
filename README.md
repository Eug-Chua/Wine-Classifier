# Wine Classification Using Unsupervised Learning

## Overview

This project aims to classify different types of wine based on their chemical attributes using unsupervised learning techniques. The dataset, sourced from the UC Irvine Machine Learning Repository, includes chemical analysis results of wines grown in the same region in Italy but derived from three different cultivars. The goal is to explore clustering algorithms to determine the natural groupings of these wines based on their features.

## Dataset

The dataset consists of 178 samples with 13 features and one target column representing the wine class. The target variable has three classes:

- **Class 1**: 59 samples (33.1%)
- **Class 2**: 71 samples (39.9%)
- **Class 3**: 48 samples (27.0%)

### Features

1. Alcohol
2. Malic acid
3. Ash
4. Alcalinity of ash  
5. Magnesium
6. Total phenols
7. Flavanoids
8. Nonflavanoid phenols
9. Proanthocyanins
10. Color intensity
11. Hue
12. OD280/OD315 of diluted wines
13. Proline

### Key Observations

- The dataset contains no missing values or duplicates.
- Features are numeric and show varying degrees of correlation.
- The features with relatively stronger correlations (in absolute terms) are:
  - Alcalinity of ash
  - Total phenols
  - Flavanoids
  - Hue
  - OD280/OD315 of diluted wines
  - Proline

## Clustering Algorithms

### K-Means Clustering

The K-Means algorithm was employed to visualize how classes are grouped. Although the dataset contains 3 classes, we tested K-Means with 2, 3, and 4 clusters to compare the results.

#### Results

- The clearest cluster delineation was observed when `K=3`.
- The Elbow Method was used to determine the optimal number of clusters, and a clear 'kink' was observed at 3 clusters, indicating that `K=3` is the optimal choice.

### Hierarchical Clustering

To further validate the findings, hierarchical clustering was used with Agglomerative Clustering. This method provides a good visualization of the number of clusters through a dendrogram.

#### Methodology

- **Linkage Criteria**: `ward`, which minimizes the sum of squared differences within all clusters.
- **Linkage Matrix `Z`**:
  - Indices of merged clusters: `Z[i, 0]` and `Z[i, 1]`
  - Distance between merged clusters: `Z[i, 2]`
  - Number of points in the new cluster: `Z[i, 3]`

#### Results

- The dendrogram confirmed the presence of 3 distinct clusters, aligning with the 3 target classes.
- The silhouette score further validated that 3 clusters provide the best separation, confirming the results from the K-Means algorithm.

## Conclusion

The project successfully used unsupervised learning techniques to classify wines into three distinct groups based on their chemical attributes. Both K-Means and hierarchical clustering confirmed that the optimal number of clusters is 3, which aligns with the known classes in the dataset.

## References

- [Wine Dataset - UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/109/wine)
