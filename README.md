# PCA vs Autoencoders — Dimensionality Reduction and Model Comparison

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1E83uY_sSUJSzxyxiAT8l2pBq-jHppzvr)

This repository contains the project for the second assignment of the **Machine Learning** course. The project explores the impact of linear (PCA) and non-linear (Autoencoders) dimensionality reduction on different downstream machine learning tasks.

## 🎯 Goal
The objective is to analyze and compare the following approaches:
- **K-Means** for **clustering**.
- **Neural Networks** (including **CNNs**) for **regression** and **multi-class classification**.
- **Principal Component Analysis (PCA)** and **Autoencoders (AE)** for **dimensionality reduction**.

Performance is evaluated and compared across three data representations:
1. The **original** data (when computationally manageable).
2. The **PCA-reduced** data.
3. The **AE-reduced** data (using the same latent dimensionality `d` as PCA for a fair comparison).

---

## 📊 Datasets (UCI Repository)
All datasets are **downloaded automatically** at runtime (no Google Drive or manual upload required):

* **AirQuality (UCI id=360)**: Tabular data used for **Regression**.
* **Paddy Dataset (UCI id=1186)**: Tabular data used for **Clustering**.
* **RealWaste (UCI id=908)**: Image-based dataset used for **Multi-class Classification**.

---

## ⚙️ Pipeline
The project follows a structured high-level pipeline:
1. **Data Acquisition**: Automatic download and organization into local folders under `/content/data`.
2. **Preprocessing**: 
   - Handling missing or noisy data.
   - Feature standardization/normalization.
   - Splitting into **train**, **validation**, and **test** sets.
3. **Dimensionality Reduction**: Application of PCA and Undercomplete Autoencoders to a fixed latent dimension `d`.
4. **Model Training & Evaluation**:
   - **K-Means**: Evaluated via Silhouette Score.
   - **FNN (Regression)**: Evaluated via MAE, RMSE, and R².
   - **CNN (Classification)**: Evaluated via Accuracy, F1-Score, Confusion Matrix, and ROC/AUC.
5. **Analysis**: Generation of summary tables, learning curves, and training time comparisons.

---

## 🚀 Key Findings
- **Clustering**: The Autoencoder latent space improved the K-Means test silhouette (**0.558**) compared to PCA and the original space (~0.533), suggesting a more cluster-friendly geometry.
- **Regression**: Aggressive compression significantly degraded performance on the Air Quality dataset (RMSE increased from 0.314 to ~1.8), indicating loss of predictive information.
- **Classification**: Both PCA and AE reconstruction led to a decrease in CNN accuracy on the RealWaste dataset, likely due to the loss of fine-grained discriminative visual cues.

---

## 📝 Notes
- **Reproducibility**: A fixed random seed is used throughout the project.
- **Hardware**: The code automatically detects and uses a **GPU** if available, otherwise it defaults to CPU.

---

**Author**: Fabio Iacus  
**Date**: January 2026
