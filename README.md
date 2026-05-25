# PJM Electricity Load Forecasting

**Reduced MAPE from 3.17% to 1.90% (40% improvement)** forecasting 
hourly electricity demand for the PJM Interconnection using XGBoost 
and 38,472 hours of grid + weather data.

## Results

| Model Version | MAPE |
|---|---|
| Baseline XGBoost | 3.17% |
| + Spike features (heat index, cold flags, momentum) | 2.67% |
| + Hyperparameter tuning | 2.63% |
| + Temperature lead features | 2.51% |
| + Expanded data (38,472 rows, 2022–2026) | **1.90%** |

## Visualizations

![Load Forecast vs Actual](images/Chart_1.png)

![Monthly Difference & Feature Important](images/Chart_2.png)

![Result Summary](images/Results.png)

## How to Run

1. Get a free EIA API key at [eia.gov/opendata](https://www.eia.gov/opendata/)
2. Open `Load_Forecasting_Model.ipynb` in Google Colab
3. In the **Configuration** cell, replace `YOUR_EIA_API_KEY_HERE` with your key
4. Click **Runtime → Run All**

## Data Sources

- **Demand:** [EIA Open Data API](https://www.eia.gov/opendata/) — PJM hourly electricity demand
- **Weather:** [Open-Meteo](https://open-meteo.com/) — Philadelphia, PA (PJM region centre)

## Key Findings

- `demand_lag_24h` dominates at ~0.43 importance — electricity demand is highly autocorrelated
- `is_cold_spike` ranked 4th — PJM's Mid-Atlantic region has high electric heating penetration
- Temperature lead features (+6h, +12h) simulate how grid operators use weather forecasts
- Data volume (7.7x increase) outperformed all feature engineering combined

## Tools

Python · XGBoost · scikit-learn · pandas · EIA API · Open-Meteo
