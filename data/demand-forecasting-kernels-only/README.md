# Retail Sales Forecasting Using ARIMA & Prophet

## Overview

This project builds predictive time series models to forecast future retail sales based on historical daily sales data. Two approaches—ARIMA (AutoRegressive Integrated Moving Average) and Prophet—are developed, compared, and evaluated against baseline models.

The analysis supports critical business decisions in inventory planning, demand management, and revenue optimization.

## Project Structure

```
├── Forecasting.ipynb              # Main analysis notebook
├── requirements.txt               # Python dependencies
├── README.md                      # This file
├── train.csv                      # Historical sales data (training set)
├── test.csv                       # Test period data
└── sample_submission.csv          # Sample submission format
```

## Setup & Installation

### Prerequisites
- Python 3.7+
- pip or conda

### Installation

1. **Clone or download the project**

2. **Create a virtual environment (recommended):**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

## Usage

1. **Launch Jupyter:**
   ```bash
   jupyter notebook Forecasting.ipynb
   ```

2. **Run cells sequentially** from top to bottom. Key sections:
   - **Exploratory Data Analysis (EDA):** Understand sales patterns, seasonality, and trends
   - **Stationarity Testing:** Verify time series properties
   - **Baseline Models:** Establish performance baselines (naive, moving average, seasonal naive)
   - **ARIMA Model:** Build and evaluate AutoRegressive Integrated Moving Average model
   - **Prophet Model:** Build and evaluate Facebook's Prophet forecasting model
   - **Model Comparison:** Compare performance and select best model
   - **Conclusions:** Business applications and next steps

## Key Features

✅ **Comprehensive EDA** with insights after each visualization  
✅ **Stationarity Testing** (rolling statistics + ADF test)  
✅ **ACF/PACF Analysis** for parameter selection  
✅ **Multiple Baseline Models** for performance context  
✅ **ARIMA & Prophet** implementation with detailed evaluation  
✅ **Business-focused Interpretation** of results  
✅ **90-day Sales Forecast** for operational planning  

## Data

- **train.csv:** Historical daily sales with columns: date, store, item, sales
- **test.csv:** Test period data (same structure)
- **sample_submission.csv:** Format for predictions

## Models

### 1. Baseline Models
- **Naive Forecast:** Last known value
- **Moving Average (30-day):** Rolling mean forecast
- **Seasonal Naive:** Same day last year

### 2. ARIMA(p,d,q)
Captures temporal autocorrelation and trend through differencing. Parameters selected via ACF/PACF analysis.

### 3. Prophet
Facebook's forecasting model that handles seasonality, trend, and external regressors well, with automatic changepoint detection.

## Key Results

Both advanced models significantly outperform baselines:
- ARIMA provides rapid, stable forecasts
- Prophet excels at capturing complex seasonal patterns
- Select best model based on test set RMSE/MAE

## Business Applications

1. **Inventory Management:** Optimize stock levels by store and item
2. **Demand Planning:** Align supply chain with predicted demand
3. **Revenue Optimization:** Time promotions to peak periods
4. **Staffing:** Schedule labor based on predicted volume

## Files Generated

- Forecast plots and comparisons (embedded in notebook)
- Performance metrics (MAE, RMSE)
- 90-day forecast for next period

## Recommendations for Deployment

1. Implement monthly retraining with new sales data
2. Add prediction intervals (confidence bounds)
3. Monitor forecast accuracy against actuals
4. Incorporate external variables (holidays, promotions)
5. Consider ensemble methods combining both models

## Requirements

See `requirements.txt` for exact versions. Key packages:
- **pandas:** Data manipulation
- **numpy:** Numerical computing
- **matplotlib/seaborn:** Visualization
- **statsmodels:** ARIMA, stationarity tests, ACF/PACF
- **scikit-learn:** Evaluation metrics
- **prophet:** Facebook's forecasting library

## Troubleshooting

**NumPy compatibility issues:**
- Ensure numpy 1.21+ is installed (required by Prophet)
- Use: `pip install numpy==1.21.6`

**Prophet import errors:**
- Install with: `pip install prophet` or `conda install -c conda-forge prophet`

## Author Notes

This analysis demonstrates a complete workflow from exploratory analysis through model selection and business interpretation. The modular structure allows for easy updates with new data and experimentation with additional models.

## License

Please refer to your organization's data governance policies for usage and sharing.
