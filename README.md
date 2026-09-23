# GHG Emissions Predictive Analysis

An interactive data analysis and machine learning project that explores historical national
greenhouse gas (GHG) emissions (1990–2018) and forecasts future emissions using a Random
Forest Regressor.

## Dataset

[International Greenhouse Gas Emissions](https://www.kaggle.com/datasets/unitednations/international-greenhouse-gas-emissions)
— published by the United Nations on Kaggle. Contains total GHG emissions (MtCO₂e) by
country/region for the years 1990–2018.

> Download `ghg-emissions.csv` from the link above and place it in the project's root folder
> before running the notebook (or update the `DATA_PATH` variable in the notebook).

## Project Description

This project walks through a complete data science workflow:

1. **Data cleaning** — standardizing country names, coercing year columns to numeric,
   handling missing values.
2. **Exploratory Data Analysis (EDA)** — top-emitter bar charts (static + interactive Plotly),
   and an interactive per-country trend explorer built with `ipywidgets`.
3. **Time-series decomposition** — trend, seasonality, and autocorrelation (ACF/PACF) analysis
   for individual countries using `statsmodels`.
4. **Feature engineering** — lag (previous year) and 3-year rolling-mean features built per
   country.
5. **Predictive modeling** — a `RandomForestRegressor` trained on a time-respecting 80/20
   train/test split (no future data leaks into training).
6. **Model evaluation** — global and per-country RMSE / R², actual-vs-predicted plots, and
   feature importance.

## Technologies Used

- **Python 3**
- **pandas / numpy** — data loading, cleaning, and manipulation
- **matplotlib / seaborn / plotly** — static and interactive visualization
- **scikit-learn** — `RandomForestRegressor`, train/test splitting, evaluation metrics
- **statsmodels** — seasonal decomposition, ACF/PACF
- **ipywidgets** — interactive dropdowns/sliders inside the notebook

## Setup / Run Instructions

1. Clone or download this project folder.
2. Download `ghg-emissions.csv` from the [Kaggle dataset page 1](https://www.kaggle.com/datasets/unitednations/international-greenhouse-gas-emissions) or [Kaggle dataset page 2](https://www.kaggle.com/datasets/saurabhshahane/green-house-gas-historical-emission-data)
   and place it in the same folder as the notebook.
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Launch Jupyter and open the notebook:
   ```bash
   jupyter notebook YourName_GHG_Emissions_Predictive_Analysis.ipynb
   ```
5. Run all cells in order (**Kernel → Restart & Run All**). The interactive widgets (dropdowns,
   sliders) require `ipywidgets`; if it isn't installed, the notebook automatically falls back
   to static charts so the rest of the analysis still runs.

## Key Information

- **Model:** Random Forest Regressor (`n_estimators=200`)
- **Features:** year, 1-year lag of emissions, 3-year rolling mean of emissions
- **Train/test split:** time-aware, 80% earliest years / 20% most recent years, per country
- **Evaluation metrics:** RMSE, MAE, R² (reported globally and for selected target countries)

## Project Files

| File | Description |
|---|---|
| `Rohan S -- GHG_Emissions_Predictive_Analysis.ipynb` | Complete project code |
| `requirements.txt` | Python dependencies |
| `Rohan S -- GHG Emissions Predictive Analysis.docx` | Full project documentation/report |
| `README.md` | This file |
