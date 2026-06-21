# 🏠 House Price Prediction

Predicting residential property prices from structural and amenity features using regression models, with a focus on identifying the key drivers of price.

![Python](https://img.shields.io/badge/Python-3.12-blue)
![scikit--learn](https://img.shields.io/badge/scikit--learn-ML-orange)
![pandas](https://img.shields.io/badge/pandas-Data%20Analysis-150458)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

## 📌 Overview

Real estate buyers and sellers often rely on guesswork or outdated comparisons to estimate fair property value. This project builds a regression pipeline that predicts house prices from property features — size, rooms, amenities — and identifies which of those features influence price the most. The full workflow covers data loading, cleaning, model training, evaluation, visualization, and a written summary of findings.

This was completed as a Week 1 internship project at **XYlofy**.

## 📊 Dataset

- **Source:** [Housing Prices Dataset](https://www.kaggle.com/datasets/yasserh/housing-prices-dataset) (Kaggle, by yasserh)
- **Size:** 545 properties × 13 features
- **Features:** area, bedrooms, bathrooms, stories, mainroad, guestroom, basement, hotwaterheating, airconditioning, parking, prefarea, furnishingstatus
- **Target:** price
- No missing values or duplicate rows were present in the raw data.

## 🗂️ Project Structure

```
HousePricePrediction_VarshithaMolabanti/
│
├── analysis.ipynb        # Full notebook — all 5 tasks (EDA → modeling → insights)
├── Housing.csv            # Raw dataset
├── summary.docx           # One-page written project summary
├── README.md               # Project documentation (this file)
└── charts/                 # Saved visualizations
    ├── chart1_price_distribution.png
    ├── chart2_correlation_heatmap.png
    └── chart3_actual_vs_predicted.png
```

## 🛠️ Methodology

1. **Data Loading & Exploration** — Inspected shape, data types, summary statistics, and checked for missing values.
2. **Data Cleaning** — Removed duplicates, encoded binary yes/no fields as 1/0, and one-hot encoded `furnishingstatus`.
3. **Model Building** — Trained and compared two regressors on an 80/20 train-test split:
   - Linear Regression
   - Random Forest Regressor
4. **Evaluation** — Assessed both models using MAE, RMSE, and R².
5. **Visualization** — Generated charts for price distribution, feature correlation, and actual vs. predicted prices.
6. **Insights & Summary** — Translated model outputs into business-relevant takeaways.

## 📈 Results

| Metric | Linear Regression | Random Forest |
|---|---|---|
| MAE | ₹970,043 | ₹1,014,947 |
| RMSE | ₹1,324,507 | ₹1,399,769 |
| R² Score | **0.653** | 0.612 |

Linear Regression slightly outperformed Random Forest — the price relationship is largely linear at this scale, and the dataset's small size (545 rows) limited the ensemble model's ability to generalize.

## 🔍 Key Insights

- **Area is the dominant price driver**, contributing ~47% of feature importance in the Random Forest model and correlating ~0.54 with price.
- **Bathrooms** (~0.52 correlation) and **air conditioning** (~0.45 correlation) were the next strongest predictors — bathroom count appears to act as a proxy for overall home quality, mattering more than bedroom count.
- **Stories and parking** had a moderate effect; **furnishing status and hot water heating** had the weakest measurable impact on price.
- The model explains ~65% of price variation despite excluding location — a feature that typically matters significantly in real estate but isn't present in this dataset.
- **Business takeaway:** listings should foreground square footage and bathroom count, and renovation budgets aimed at resale value should prioritize bathrooms or air conditioning over furnishing upgrades.

## ⚙️ Tech Stack

`Python` · `pandas` · `NumPy` · `scikit-learn` · `matplotlib` · `seaborn` · `Jupyter Notebook`

## ▶️ How to Run

```bash
git clone <your-repo-url>
cd HousePricePrediction_VarshithaMolabanti
pip install pandas numpy matplotlib seaborn scikit-learn
jupyter notebook analysis.ipynb
```

## 🚀 Future Improvements

- Incorporate location-based features (e.g., neighborhood, distance to city center) to improve R².
- Test regularized models (Ridge, Lasso) and gradient boosting (XGBoost) for comparison.
- Apply hyperparameter tuning (GridSearchCV) to the Random Forest model.
- Expand the dataset to reduce overfitting risk in tree-based models.

## 👤 Author

**Varshitha Molabanti**
Week 1 Internship Project — XYlofy
