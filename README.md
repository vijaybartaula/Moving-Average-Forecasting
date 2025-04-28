# NEPSE Trend Forecasting Using Moving Averages

## Overview
This project analyzes Nepal Stock Exchange (NEPSE) trends using three different moving average methods: Simple Moving Average (SMA), Weighted Moving Average (WMA), and Exponential Moving Average (EMA). The analysis demonstrates the application of these techniques in forecasting stock values and evaluates their prediction performance.

## Background
Moving averages are essential tools for smoothing out price data and identifying trends in financial markets. This analysis explores the practical application of different moving average techniques and compares their effectiveness in predicting NEPSE index values.

## Methods

### Simple Moving Average (SMA)
The SMA calculates the arithmetic mean of a selected range of prices over a specific period:
```
SMA(t) = (a + b + c + d) / 4
```
Where a, b, c, and d represent the values from the most recent 4 months.

### Weighted Moving Average (WMA)
The WMA assigns more weight to recent data points:
```
WMA(t) = (a×1 + b×2 + c×4 + d×8) / (1 + 2 + 4 + 8)
```
This makes WMA more responsive to recent price movements while still considering historical data.

### Exponential Moving Average (EMA)
The EMA applies exponentially decreasing weights to older data points:
```
EMA(t) = b + 0.5(a - b)
```
Where:
- a is the actual value
- b is the previous forecast
- 0.5 is the smoothing factor (α)

## Results

### Prediction Performance
The analysis calculated forecasted values for each month using the three moving average methods with the following Mean Squared Error (MSE) results:

| Method | MSE      | Performance Ranking |
|--------|----------|---------------------|
| WMA    | 7,058.35 | Best (lowest error) |
| SMA    | 13,816.89| Medium error        |
| EMA    | 61,972.44| Highest error       |

### Key Findings
- The WMA provided the most accurate forecasts for this particular dataset
- All three moving averages effectively smoothed major spikes in the data
- The three forecast methods converged toward similar values in later months
- Each method demonstrated different responsiveness to price movements

## Visualization Insights
The visualization offered several insights:
1. All three moving averages effectively reduced data noise
2. The WMA followed the actual index more closely in middle periods
3. The three forecast lines converged in later months (Chaitra through Jestha) 
4. The final predicted value for Jestha month was nearly identical across all three methods

## Usage
The Excel spreadsheet implements these moving average methods and provides visualizations of the results. The spreadsheet calculates:
- Forecasted values using each method
- Error measurements
- Mean Squared Error (MSE) for performance comparison

## Dependencies
- Microsoft Excel or compatible spreadsheet software

## Future Work
Potential areas for future exploration include:
- Testing different periods for the moving averages
- Exploring alternative smoothing factors for EMA
- Combining multiple methods for hybrid forecasting
- Incorporating additional technical indicators

## Resources
For access to the complete project files, visit:
[Moving-Average-Forecasting on GitHub](https://github.com/vijaybartaula/Moving-Average-Forecasting/blob/main/NEPSE_SWE_MA.xlsx)

## Acknowledgements
- Er. Manil Vaidya (Machine Learning)
- Nepal College of Information Technology, Department of Computer Engineering

---
*This project was completed as part of coursework at Nepal College of Information Technology, affiliated with Pokhara University.*
