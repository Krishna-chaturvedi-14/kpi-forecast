# kpi-forecast
# 📈 KPI Time Series Forecasting

This project demonstrates time series forecasting of a Key Performance Indicator (KPI) using a Gradient Boosting Regressor model. The data used contains KPI values over time for different network tower nodes. The notebook includes all steps from data preprocessing to future forecasting.

## 🔍 Overview

- **Dataset**: Time-stamped KPI values for network tower clusters  
- **Goal**: Forecast KPI values for the next 10 days  
- **Best Model**: Gradient Boosting Regressor (after testing multiple models)

## 🛠️ Workflow

1. **Data Preprocessing**  
   - Parsing dates  
   - Sorting chronologically by server, location, and cluster  
   - Creating time-based features like day of the week and week of the year  

2. **Feature Engineering**  
   - Lag features: KPI values of the past 3 days  
   - Rolling statistics: 3-day rolling mean and standard deviation  

3. **Model Training**  
   - Trained Gradient Boosting Regressor on 80% of the time-sorted data  
   - Evaluated using MAE, RMSE, and R² metrics

4. **Forecasting**  
   - Predicting the next 10 days for a specific node (Hyderabad / INTEL / cluster ID `10000000000599`)  
   - Recursive prediction using last known KPI values

5. **Visualization**  
   - Plot showing historical data and predicted values for the next 10 days

## 📊 Model Performance

- Model: **Gradient Boosting Regressor**
- Evaluation:
  - Mean Absolute Error (MAE)
  - Root Mean Squared Error (RMSE)
  - R-squared (R²)

## 📁 Files

- `kpi.ipynb`: Jupyter notebook with complete working code and plots  
- `unique_cluster_kpi_timeseries.csv`: The cleaned dataset used in this notebook

## 🚀 Future Improvements

- Hyperparameter tuning for further optimization  
- Incorporating external factors like holidays, outages, etc.  
- Extending to multi-node forecasting

## 📌 Requirements

Install dependencies using:

```bash
pip install pandas numpy matplotlib scikit-learn
