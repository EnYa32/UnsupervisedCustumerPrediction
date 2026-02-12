---
title: UnsupervisedCustumerPrediction
emoji: 🧩
colorFrom: indigo
colorTo: blue
sdk: docker
app_port: 8501
tags:
- streamlit
pinned: false
short_description: Streamlit app that predicts cluster labels from uploaded CSV
license: mit
---

# 🧩 Clustering Predictor (KMeans / GMM)

This Space predicts cluster labels for uploaded tabular data using a saved preprocessing pipeline:
- **StandardScaler**
- **PCA (95% explained variance)**
- A clustering model (**KMeans** or **Gaussian Mixture Model**)

## ✅ What this app does
- Upload a CSV file
- The app checks required feature columns
- Applies **scaler + PCA**
- Outputs **Predicted** cluster label for each row
- Lets you download the predictions as a CSV

## 📦 Required files (must be in the repo root)
Place these files next to `app.py`:

- `feature_names.pkl`
- `scaler.pkl`
- `pca.pkl`
- `kmeans_model_k9.pkl` *(optional, if you want KMeans)*
- `gmm_model_k9.pkl` *(optional, if you want GMM)*

## 🧾 Input format
Your CSV must include all feature columns stored in `feature_names.pkl`.

Optional:
- You may include an `id` or `Id` column.  
  If present, it will be included in the output as `Id`.

## ▶️ Run locally
```bash
pip install -r requirements.txt
streamlit run app.py
📝 Notes
This is an unsupervised project, so cluster quality is evaluated on Kaggle using the leaderboard score.

Visual separation in 2D does not always reflect the Kaggle metric.