# PJM Electricity Load Forecasting

**Reduced MAPE from 3.17% to 1.85% (41% improvement)**

## Setup

1. Get a free EIA API key at [eia.gov/opendata](https://www.eia.gov/opendata/)
2. Replace `YOUR_EIA_API_KEY_HERE` in the notebook with your key
3. Install dependencies: `pip install -r requirements.txt`
4. Run the notebook top to bottom

## Results
| Model Version | MAPE |
|---|---|
| Baseline XGBoost | 3.17% |
| + Spike features | 2.67% |
| + Hyperparameter tuning | 2.63% |
| + Temperature lead features | 2.51% |
| + Expanded data (38,472 rows) | **1.85%** |

## Tools
Python · XGBoost · scikit-learn · pandas · EIA API · Open-Meteo API
