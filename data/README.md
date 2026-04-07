# Data

The dataset is not included in this repository.

It comes from the following Kaggle competition:
https://www.kaggle.com/competitions/2-el-1730-machine-learning-project-2026/

---

## Dataset Overview

The data consists of precomputed features derived from satellite imagery, including:

* geometric properties (polygons, area, shape descriptors)
* temporal evolution (multi-date construction status)
* spectral features (RGB statistics over time)

It includes:

* **Training set (~296k samples)** with labels
* **Test set (~120k samples)** without labels

---

## How to Access the Data

1. Create a Kaggle account
2. Join the competition
3. Download the dataset manually or using the Kaggle API

---

## Expected Raw Data Structure

After download, place the files in this folder:

```id="jzv7db"
data/
├── train.geojson
├── test.geojson
└── sample_submission.csv
```

---

## Generated Data (Feature Engineering Outputs)

Running the feature engineering notebook (`01_feature_engineering.ipynb`) will generate:

```id="2qf5gr"
data/
├── train_features_cleaned.csv
├── test_features_cleaned.csv
├── train_target_corr.csv
```

These processed files are then used as inputs for the modeling notebooks.

---

## Pipeline Summary

```id="y9d8rd"
train.geojson / test.geojson
        ↓
feature engineering
        ↓
cleaned feature datasets (.csv)
        ↓
LightGBM / XGBoost models

```
Prediction results (CSV files containing test set predictions) are also saved in the `data/` folder.