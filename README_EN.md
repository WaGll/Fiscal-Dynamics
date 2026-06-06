# Fiscal Dynamics

[中文文档](./README_.md)

## Overview

Fiscal-Dynamics is a data mining and econometric analysis project focusing on China's provincial tax revenue data.

This project explores industrial tax structure, consumption expenditure patterns, and disposable income relationships using statistical modeling and machine learning methods for regional tax classification.

## Analysis Pipeline

1. Data loading and initial exploration
2. Data integration and descriptive statistics
3. Data cleaning (missing values, log transformation, normality tests)
4. Pearson correlation analysis
5. Multiple linear regression (VIF, heteroscedasticity, autocorrelation diagnostics)
6. K-Means clustering (elbow method + regional classification)
7. Geospatial visualization (GeoPandas China map)

## Quick Start

```bash
# 1. Install dependencies
pip install -r requirements.txt

# 2. Place raw data files in data/ directory
#    - Industrial tax table (.xlsx)
#    - Household consumption expenditure table (.xlsx)
#    - Disposable income table (.xlsx)
#    - (Optional) GIS shapefiles in data/gis/

# 3. Launch Jupyter and run the analysis
jupyter notebook notebooks/fiscal-dynamics-analysis.ipynb
```

## Data Requirements

| File | Key Fields |
|------|------------|
| Industrial tax | TaxAmount, PrimaryInduTaxAmount, SecondInduTaxAmount, TertiaryInduTaxAmount |
| Consumption expenditure | ConsumExpense, CE_FoodTobaccoliquor, CE_Clothing, CE_Resident, CE_DailyUse, CE_TrafficCommunicate, CE_EducateCulture, CE_HealthCare |
| Disposable income | PCDI, PCDI_WageIncome, PCDI_BusinessIncome, PCDI_PropertyIncome, PCDI_TransferIncome |

All tables must include `Sgnyea` (year) and `AreaName` (region name) columns for joining.

## Project Structure

```text
fiscal-dynamics/
├── data/            — Raw data (Excel, shapefiles)  [git-ignored]
├── notebooks/       — Jupyter analysis notebook
├── src/             — Utility entry point
├── figures/         — Output charts  [git-ignored]
├── doc/             — Reference paper
├── CLAUDE.md        — Claude Code guide
├── README_.md        — Project README (Chinese)
├── README_EN.md     — Project README (English)
├── LICENSE          — MIT License
├── requirements.txt — Python dependencies
└── .gitignore
```

## Tech Stack

- Python · Pandas · NumPy · SciPy
- Statsmodels (regression, diagnostics)
- Scikit-learn (clustering)
- GeoPandas (spatial visualization)
- Matplotlib · Seaborn (plotting)

## Research Topics

- Tax Revenue Analysis
- Econometrics
- Regional Economic Development
- Clustering Analysis
- Spatial Data Visualization

## License

This project is licensed under the MIT License.
