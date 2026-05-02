# Air Quality Analysis — PM10 & PM2.5 with Machine Learning

**Predicting and classifying particulate matter concentrations using environmental monitoring data from Colombia.**

---

## Problem

Particulate matter (PM10 and PM2.5) is one of the main air quality indicators regulated by environmental authorities. Monitoring these pollutants generates large volumes of data that, when analyzed manually, are slow to interpret and hard to scale.

This project applies Machine Learning techniques to:
1. **Predict** PM2.5 concentrations from operational variables (regression)
2. **Classify** air quality alert levels based on WHO 2021 guidelines (binary and multi-class)

---

## Dataset

- Source: Environmental monitoring records from industrial field campaigns (CONHINTEC S.A.S)
- File: `dateWr.xlsx`
- Key variables: `PM_10`, `PM_25`, `Temp_C`, `Presion_mmHg`, `LATITUD_N`, `LONGITUD_O`, `STATION`, `DATE`
- Temporal split: 80% training / 20% test (chronological order — no data leakage)

---

## Models

### Regression (predicting PM2.5 values)

| Model | Purpose |
|-------|---------|
| Linear Regression | Baseline |
| Random Forest Regressor | Non-linear relationships |
| XGBoost Regressor | Best performance |

Metrics: MAE, RMSE, R²

### Classification (alert levels)

| Type | Threshold | Models used |
|------|-----------|-------------|
| Binary | WHO 24h limit: 15 µg/m³ | Logistic Regression, Random Forest |
| Multi-class | ≤15 / 15–25 / >25 µg/m³ | Random Forest |

---

## Key results

- XGBoost achieved the best regression performance across all metrics
- Feature importance analysis shows PM10 and temperature are the strongest predictors of PM2.5
- The chronological split (instead of random) ensures results reflect real-world deployment conditions

---

## Tech stack

- Python 3
- pandas, numpy
- scikit-learn (Pipeline, ColumnTransformer, imputers, scalers)
- XGBoost
- matplotlib, seaborn

---

## Project structure

```
├── pm_10_and_pm2_5.py       # Main analysis: EDA, regression, classification, feature importance
├── untitled21.py            # Supplementary analysis
├── untitled22.py            # Supplementary analysis
├── dateWr.xlsx              # Environmental monitoring dataset
├── correlacion.png          # Correlation matrix
└── descarga (1-7).png       # Output visualizations
```

---

## How to run

```bash
pip install pandas numpy scikit-learn xgboost matplotlib seaborn openpyxl
python pm_10_and_pm2_5.py
```

Or open directly in [Google Colab](https://colab.research.google.com/).

---

## Author

**Wilmer Ricardo Urda**
Environmental Engineer | Data Analyst | Python Developer
[LinkedIn](https://www.linkedin.com/in/wilmer-ricardo-urda-267624b2) · [GitHub](https://github.com/Wilnecot)

> This project combines 10+ years of hands-on environmental monitoring experience with applied Machine Learning — bridging domain expertise and data science.
