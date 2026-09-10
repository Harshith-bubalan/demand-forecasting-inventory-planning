# Demand Forecasting & Inventory Planning

## Project Overview

This project develops a time-series demand forecasting model using historical product demand data. Multiple forecasting techniques are compared and evaluated to identify a suitable model for short-term demand planning.

The project also demonstrates how demand forecasts can support inventory planning through safety stock and reorder point calculations.

## Objective

- Analyze historical product demand
- Identify demand trends and patterns
- Build and compare forecasting models
- Evaluate forecast accuracy
- Generate future demand forecasts
- Demonstrate inventory planning using forecast and demand variability

## Dataset

The analysis uses the Historical Product Demand dataset.

The dataset contains:

- Product Code
- Warehouse
- Product Category
- Date
- Order Demand

The selected product for forecasting was **Product_1359**.

## Methodology

### 1. Data Cleaning

- Converted dates to datetime format
- Converted demand values to numeric format
- Removed records with missing date or demand values
- Sorted the dataset chronologically

### 2. Product Selection

Products were compared based on total historical demand. Product_1359 was selected for the forecasting analysis.

### 3. Time-Series Preparation

Individual demand transactions were aggregated into monthly demand.

The selected product contains 24 monthly observations from January 2012 to December 2013.

### 4. Forecasting Models

The following approaches were compared:

- 3-Month Moving Average
- Exponential Smoothing
- ARIMA(1,1,1)

### 5. Model Evaluation

Models were evaluated using:

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- Mean Absolute Percentage Error (MAPE)

## Results

| Model | MAE | RMSE | MAPE |
|---|---:|---:|---:|
| Moving Average | 261,543 | 280,596 | 14.23% |
| Exponential Smoothing | 267,168 | 281,392 | 14.53% |
| **ARIMA(1,1,1)** | **178,069** | **188,460** | **9.96%** |

ARIMA(1,1,1) achieved the lowest MAPE on the selected test period and was therefore used for the final forecast.

## Future Demand Forecast

The ARIMA model was trained using the available 2013 monthly demand data to generate a six-month forecast.

- Average monthly forecast: **1,911,122 units**
- Total six-month forecast: **11,466,731 units**
- Minimum monthly forecast: **1,786,555 units**
- Maximum monthly forecast: **2,035,690 units**

## Inventory Planning

An illustrative inventory scenario was developed using:

- Lead time: 1 month
- Service level: 95%

Based on these assumptions:

- Safety stock: **565,041 units**
- Reorder point: **2,178,541 units**

These values are illustrative and are not company-specific inventory policies.

## Business Recommendations

- Use demand forecasts as an input for short-term production and inventory planning.
- Update forecasts regularly as new demand data becomes available.
- Consider supplier lead time, production capacity, market conditions and demand changes when making inventory decisions.
- Use safety stock to protect against demand variability and reduce the risk of stockouts.

## Limitations

- The selected product has only 24 monthly observations.
- A major demand shift occurred between 2012 and 2013.
- The model uses historical demand only and does not include external factors such as price, promotions or market conditions.
- Inventory calculations are based on illustrative assumptions.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Statsmodels
- Scikit-learn
- Google Colab
- GitHub

## Project Structure

```text
demand-forecasting-inventory-planning/
│
├── demand_forecasting.ipynb
└── README.md
