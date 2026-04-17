# PCA vs Autoencoders: Dimensionality Reduction and Model Comparison

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1E83uY_sSUJSzxyxiAT8l2pBq-jHppzvr)

This repository contains the project for the second assignment of the **Machine Learning** course (A.Y. 2025/2026). The study explores and compares **Principal Component Analysis (PCA)** and **Autoencoders (AE)** as dimensionality reduction techniques applied to different machine learning tasks.

## 📌 Project Overview
The core objective is to evaluate how linear (PCA) and non-linear (Autoencoders) compression affects the performance of downstream models. We analyze three main tasks:

1.  **Clustering**: Using **K-Means**.
2.  **Regression**: Using a **Feed-forward Neural Network (FNN)**.
3.  **Classification**: Using a **Convolutional Neural Network (CNN)**.

For each task, models are trained and compared on:
* The **original** feature space.
* A **PCA-reduced** representation.
* An **Autoencoder-reduced** representation (maintaining the same latent dimensionality).

---

## 📊 Datasets
* **Regression**: [Air Quality Dataset](https://archive.ics.uci.edu/ml/datasets/Air+Quality) (UCI) – Tabular data for predicting pollutant concentrations.
* **Classification**: [RealWaste Dataset](https://www.kaggle.com/datasets/techsavyv/realwaste) – Image-based dataset for waste material classification.
* **Clustering**: Evaluated on the latent spaces derived from the datasets above.

---

## 🛠 Methodology
* **Dimensionality Reduction**: Comparison between linear PCA and Undercomplete Autoencoders.
* **Hyperparameter Tuning**: Performed via Grid Search/Cross-Validation on the training set to ensure the best configuration for each model.
* **Evaluation Metrics**: 
    * *Clustering*: Silhouette Score.
    * *Regression*: Root Mean Square Error (RMSE).
    * *Classification*: Accuracy and F1-Score.

---

## 🚀 Key Results
* **Clustering**: Autoencoders proved superior in creating a cluster-friendly geometry, achieving a higher test silhouette score (**0.558**) compared to PCA and the original space (~0.533).
* **Regression**: Aggressive compression significantly impacted performance. Reducing features to $d=6$ led to a substantial increase in RMSE, showing that critical predictive information was lost.
* **Classification**: Both PCA and AE reconstruction led to a decrease in CNN accuracy, suggesting that fine-grained discriminative cues are easily lost during the compression process.

---

## 📁 Repository Structure
* `Second_assignment_notebook.ipynb`: The full Google Colab notebook with data preprocessing, model training, and visualizations.
* `ML_Second_Assignment_Report.pdf`: The detailed technical report explaining the theoretical background and analyzing the results.

---

## 👨‍💻 Author
**Fabio Iacus** Machine Learning Project - January 2026
