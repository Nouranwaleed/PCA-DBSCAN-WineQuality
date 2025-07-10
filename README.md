# PCA & Clustering on Wine Quality Dataset

This project demonstrates the application of **Principal Component Analysis (PCA)** from scratch, followed by **DBSCAN clustering** before and after dimensionality reduction. The dataset used is the **Wine Quality Dataset**.


## Dataset

* Source: [`winequality-red.csv`](https://archive.ics.uci.edu/ml/datasets/wine+quality)
* Records: `1,599` wine samples
* Features: `12` columns (11 numeric + 1 quality score)

## Objectives

* Apply **PCA manually** (using power iteration + deflation) to reduce feature dimensions.
* Analyze **reconstruction error** across multiple values of `k` (number of components).
* Cluster data using **DBSCAN**, and compare performance before and after PCA.
* Visualize outliers, clusters, and variance explained.

## Data Preprocessing

* Handled outliers using the **IQR method**.
* Final shape after cleaning: **(1179, 12)**.
* Standardized features before applying PCA.


## PCA Implementation (From Scratch)

* Used **power iteration** to compute top eigenvalues and eigenvectors.
* Observed that:

  * Reconstruction error **decreases** with increasing `k`.
  * At `k = 3`, significant variance is already captured.
  * At `k = 12`, reconstruction is **almost perfect**.

### Reconstruction Error:

<img width="862" height="585" alt="image" src="https://github.com/user-attachments/assets/fda61ea5-c197-46d8-97dd-0aaea35c2a2b" />


## Clustering: DBSCAN

### Before PCA:

* DBSCAN struggled due to high dimensionality.
* **65+ clusters** with **many noise points (108)**.
* Clusters were poorly defined.

### After PCA (2D projection):

* Clusters became **more distinct**.
* Noise points reduced to **zero**.
* **Only 8 clear clusters** detected.

<img width="1894" height="969" alt="image" src="https://github.com/user-attachments/assets/c30bb128-d360-4acc-a48a-05bd085c2b22" />

## Key Takeaways

* **Dimensionality reduction significantly improved clustering performance.**
* **PCA** helps highlight latent structure in noisy, high-dimensional data.
* **DBSCAN + PCA** is a powerful combo for unsupervised learning tasks.


## Technologies Used

* Python, NumPy, Pandas
* Matplotlib, Seaborn
* Manual implementation of **PCA** and **DBSCAN**
