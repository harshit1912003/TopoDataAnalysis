# Topological Mode Analysis Tool (ToMATo) - MTL782 Self-Study Project

This repository contains the work for our self-study project for MTL782 under Prof. Niladri Chatterjee at IIT Delhi. The project involved an in-depth study and implementation of the Topological Mode Analysis Tool (ToMATo), a clustering method based on Topological Data Analysis (TDA).

We were also instructed by the professor to hold a class presentation to share our findings and results with classmates.

![img](.\curx.png)


## Motivation

Traditional clustering algorithms like K-Means often struggle with non-convex cluster shapes, while density-based methods like DBSCAN can have difficulty with varying densities or hierarchical structures. Mode-seeking methods like Mean Shift can be sensitive to noise and parameter choices.

ToMATo offers an alternative approach that leverages topological persistence. By analyzing the persistence of density peaks (local maxima of a density estimator), ToMATo aims to:

* Identify clusters based on the underlying density function's gradient flow.
* Provide a more robust way to handle noise and complex data structures by distinguishing significant topological features (long persistence) from noise (short persistence).
* Use persistence to explicitly link input parameters (like the merging threshold τ) to the resulting number of clusters, forming a hierarchical structure.

## Results Summary

We tested the ToMATo algorithm against standard methods like K-Means and DBSCAN on various datasets:

1.  **2D Synthetic Datasets:** ToMATo demonstrated superior performance on datasets with non-convex shapes (Circles, Moons) and varying densities (Anisotropic, Blobs with varying variances), where K-Means and DBSCAN often struggled.
2.  **Real-World Dataset (Palmer Penguins):** Using pairs of features (Culmen Length vs. Depth, Culmen Length vs. Flipper Length), ToMATo achieved good clustering results (Adjusted Rand Index - ARI of 0.79 and 0.87 respectively), outperforming baseline methods in capturing the species clusters based on these features. Performance varied depending on the feature pair chosen (e.g., lower ARI for Culmen Length vs. Body Mass).
3.  **High-Dimensional Dataset (MNIST Digits):** After dimensionality reduction (784D -> 32D using a neural network), ToMATo significantly outperformed K-Means (ARI 0.78 vs 0.52). It provided more balanced clustering across digit classes, although it showed specific weaknesses (e.g., for digit '8').

## Contributors

* Ananya Sharma (2023MAS7117)
* Harshit Joshi (2023MAS7141)
