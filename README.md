# Urban Area Classification via Satellite Imagery

## Overview

This project was developed as part of a Kaggle competition focused on **multi-class classification of urban areas** using multi-date satellite-derived data.

The objective is to classify geographical zones into six categories:

* Demolition
* Road
* Residential
* Commercial
* Industrial
* Mega Projects

The dataset consists of **~300k observations** with heterogeneous features including:

* Geometric data (polygons)
* Temporal construction status (multi-date)
* Spectral features (RGB statistics)
* Urban and neighborhood characteristics

---

## Key Features

### Advanced Feature Engineering

* Geometric features: area, perimeter, compactness, solidity, bounding box ratios
* Temporal features: project duration, status transitions, construction speed
* Spectral features: trends, slopes, variations across multiple timestamps
* Feature interactions across geometry, time, and spectral signals

Feature space:

* Initial: **45 features**
* Engineered: **135 features**
* Final after selection: **92 features**

---

## Modeling Approach

### Models Explored

* KNN (baseline)
* Neural Networks (limited performance)
* Gradient Boosting (final choice)

### Final Models

* LightGBM (baseline + tuning)
* XGBoost (final model)

---

## Handling Class Imbalance

* Class weighting (inverse frequency)
* Threshold tuning for rare classes
* Evaluation using **macro F1-score**

---

## Optimization Strategy

* Stratified cross-validation
* Hyperparameter tuning with Optuna
* Joint optimization of:

  * Model parameters
  * Decision thresholds for minority classes

---

## Results

| Model    | CV Macro-F1 | Kaggle Public | Kaggle Private |
| -------- | ----------- | ------------- | -------------- |
| LightGBM | 0.536       | 0.883         | -              |
| XGBoost  | 0.574       | 0.91          | **0.84**       |

Final score (**private leaderboard**): **0.84 macro-F1**

---

## Repository Structure

```
├── notebooks/        # Experiments and modeling
├── report/           # Full project report (French)
├── data/             # Dataset description (no raw data)
├── README.md
└── requirements.txt
```

---

## Data
See data/README.md for details about data and generated files.


## How to Run

1. Install dependencies:

```bash
pip install -r requirements.txt
```

2. Run notebooks in order:

* Feature engineering
* LightGBM baseline
* LightGBM tuning
* XGBoost final model

---

## Key Takeaways

* Feature engineering is critical for tabular satellite data
* Gradient boosting models outperform neural networks in this setting
* Proper handling of class imbalance significantly improves macro-F1
* Threshold tuning can boost performance on rare classes

---

## Author

Project developed as part of a Machine Learning academic project (2026).
