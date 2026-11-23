# Time Series Forecasting and Burst Detection in Network Traffic

## Project Overview

This project focuses on analyzing and forecasting institutional network traffic using Statistical Time Series Analysis, Machine Learning, and Deep Learning techniques.

Using hourly CESNET network traffic data, the project analyzes historical traffic patterns, forecasts future network demand, detects unexpected traffic bursts, and generates insights to support network capacity planning.

## Project Objectives

- Analyze hourly network traffic patterns.
- Perform data preprocessing and missing-value handling.
- Identify trends, seasonality, and stationarity.
- Build and compare different forecasting models.
- Detect unexpected network traffic bursts.
- Generate forecasts for operational monitoring and capacity planning.

## Technologies & Libraries

- **Programming Language:** Python
- **Data Processing:** Pandas, NumPy
- **Visualization:** Matplotlib, Seaborn
- **Statistical Analysis:** Statsmodels, SciPy
- **Statistical Forecasting:** ARIMA, SARIMA, SARIMAX, Holt-Winters
- **Machine Learning:** XGBoost
- **Deep Learning:** LSTM, GRU, Sequence-to-Sequence
- **Additional Forecasting Models:** Prophet, AutoTS
- **Evaluation Metrics:** RMSE, MAE, MAPE

## Models Implemented

### 1. Statistical Models
- Autoregressive (AR)
- Moving Average (MA)
- ARMA
- ARIMA
- SARIMA
- SARIMAX
- Holt-Winters Exponential Smoothing

### 2. Machine Learning Models
- XGBoost
- Prophet
- AutoTS

### 3. Deep Learning Models
- Long Short-Term Memory (LSTM)
- Gated Recurrent Unit (GRU)
- Sequence-to-Sequence Forecasting

### 4. Ensemble Forecasting
- Combined forecasting using multiple models to improve prediction performance.

## Project Workflow

1. Data loading and preprocessing.
2. Missing-value handling and hourly frequency conversion.
3. Exploratory Data Analysis (EDA).
4. Trend and seasonality analysis.
5. Stationarity testing using ADF and KPSS.
6. ACF and PACF analysis.
7. Model development and parameter selection.
8. Hyperparameter tuning and model comparison.
9. Forecast evaluation using RMSE, MAE, and MAPE.
10. Out-of-sample burst detection.
11. Forecast dashboard and capacity planning insights.

## Forecasting Tasks

**Task A – 7-Day-Ahead Forecasting**

Predicts network traffic for the next 168 hours to support network capacity planning.

**Task B – 1-Hour-Ahead Forecasting**

Predicts the next hour's traffic using recently observed values to support operational monitoring and burst alerts.

The final 7-day period is kept separate for testing.

## Key Results

| Forecasting Task | Best Model | RMSE |
|---|---|---:|
| 7-Day-Ahead | XGBoost | 23.26 GB/h |
| 1-Hour-Ahead | Ensemble (Holt-Winters + XGBoost + LSTM) | 18.46 GB/h |

### Model Evaluation

The models were compared using:
- Root Mean Squared Error (RMSE)
- Mean Absolute Error (MAE)
- Mean Absolute Percentage Error (MAPE)

**Best model performance:**

- 7-Day-Ahead: RMSE 23.26, MAE 18.74, MAPE 28.2%.
- 1-Hour-Ahead: RMSE 18.46, MAE 14.26, MAPE 20.0%.

### Burst Detection Results

An out-of-sample XGBoost forecasting approach was used to identify unusual network traffic spikes.

- Total burst alerts: 119
- Alert precision: 76%
- Recall against IQR-defined burst hours: 58%

### Capacity Planning Insights

The forecasting dashboard provides:
- Next-week traffic forecasts.
- 90% forecast uncertainty band.
- Historical traffic patterns.
- Burst alert visualization.
- Estimated network capacity requirements.

## Key Learnings

- Understanding stationarity and seasonality in real-world time-series data.
- Applying statistical and machine learning forecasting techniques.
- Comparing classical forecasting models with deep learning approaches.
- Feature engineering using lag and rolling statistics.
- Evaluating models while avoiding data leakage.
- Using forecasting residuals for burst detection.
- Translating predictions into practical capacity planning insights.

## How to Run the Project

1. Clone this repository:

   `git clone YOUR_GITHUB_REPOSITORY_URL`

2. Install the required libraries:

   `pip install pandas numpy matplotlib seaborn statsmodels scipy scikit-learn xgboost prophet autots tsfresh`

3. Open `TS_Project.ipynb` using Google Colab or Jupyter Notebook.

4. Upload the required dataset:

   `cesnet_institution_hourly.csv`

5. Run the notebook cells sequentially.

## Future Scope

- Real-time network traffic forecasting.
- Improved burst detection techniques.
- Analysis across multiple institutions.
- Experimentation with advanced deep learning models.
- Automated network traffic monitoring and alert systems.

## Conclusion

This project demonstrates how Statistical Time Series Analysis, Machine Learning, and Deep Learning can be integrated to forecast network traffic, identify unusual traffic patterns, and support data-driven network capacity planning.

