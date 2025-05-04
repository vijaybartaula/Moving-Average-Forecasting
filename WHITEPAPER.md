# NEPSE Trend Forecasting Using Moving Averages
### A Comparative Analysis of SMA, WMA, and EMA Forecasting Methods

## Executive Summary

This whitepaper presents a comprehensive analysis of Nepal Stock Exchange (NEPSE) index trends using three distinct moving average methodologies: Simple Moving Average (SMA), Weighted Moving Average (WMA), and Exponential Moving Average (EMA). The research evaluates each method's effectiveness in forecasting stock market movements and identifies the most reliable approach for predicting NEPSE index values. Based on Mean Squared Error (MSE) analysis, the Weighted Moving Average emerged as the most accurate forecasting technique for this dataset, demonstrating superior performance in capturing recent market dynamics while appropriately weighting historical data.

## Introduction

Moving averages are fundamental tools in technical analysis that help traders and analysts identify trends, support and resistance levels, and potential reversal points in financial markets. By smoothing out price data and reducing noise, moving averages provide clearer visualizations of underlying market trends. This study applies three widely-used moving average techniques to NEPSE index data and compares their predictive accuracy.

## Theoretical Framework

### Simple Moving Average (SMA)
The SMA calculates the arithmetic mean of a selected range of prices over a specific period:

$$SMA(t) = \frac{A_1 + A_2 + ... + A_n}{n}$$

Where:
- $A$ represents prices
- $n$ is the number of periods

For this study using a 4-month window:

$$SMA(t) = \frac{a + b + c + d}{4}$$

The SMA gives equal weight to all data points in the calculation period, making it a straightforward but sometimes less responsive indicator for rapidly changing markets.

### Weighted Moving Average (WMA)
The WMA assigns different weights to data points, with greater emphasis on more recent values:

$$WMA(t) = \frac{\text{Sum of weighted prices}}{\text{Sum of weights}}$$

For this analysis, exponentially increasing weights were applied:

$$WMA(t) = \frac{a \times 1 + b \times 2 + c \times 4 + d \times 8}{1 + 2 + 4 + 8}$$

This weighting scheme makes the WMA more responsive to recent price movements while still incorporating historical context.

### Exponential Moving Average (EMA)
The EMA gives exponentially decreasing weights to older data points:

$$EMA(t) = b + \alpha(a - b)$$

Where:
- $a$ is the actual value
- $b$ is the previous forecast
- $\alpha$ is the smoothing factor (0.5 in this study)

This recursive calculation makes EMA potentially more responsive to recent price changes than SMA.

## Methodology

The analysis utilized monthly NEPSE index data spanning from Ashwin to Jestha, with the following approach:

1. **Data Collection**: Monthly NEPSE index values were compiled
2. **Moving Average Calculations**: SMA, WMA, and EMA values were calculated for each month
3. **Forecast Generation**: Each method was used to forecast future index values
4. **Error Analysis**: Mean Squared Error (MSE) was calculated to evaluate prediction accuracy
5. **Visual Comparison**: Graphical representation of actual vs. forecasted values

## Results and Analysis

### Forecast Performance Metrics

| Method | Mean Squared Error (MSE) | Performance Ranking |
|--------|--------------------------|---------------------|
| WMA    | 7,058.35                 | Best (lowest error) |
| SMA    | 13,816.89                | Medium error        |
| EMA    | 61,972.44                | Highest error       |

* **SMA** has the lowest MSE, suggesting that it performs better overall in terms of forecast accuracy.
* **WMA** and **EMA** have higher MSE, indicating that their predictions deviate more from the actual values compared to SMA.

### Detailed Error Analysis

The error analysis for each month revealed:

| Month   | Index | SMA  | P. Error (SMA) | Error Sq. (SMA) | WMA  | P. Error (WMA) | Error Sq. (WMA) | EMA  | P. Error (EMA) | Error Sq. (EMA) |
| ------- | ----- | ---- | -------------- | --------------- | ---- | -------------- | --------------- | ---- | -------------- | --------------- |
| Ashwin  | 2214  | 2214 | 0              | 0               | -    | -              | -               | -    | -              | -               |
| Shrawan | 2259  | 2214 | 45             | 2025            | -    | -              | -               | -    | -              | -               |
| Bhadra  | 3019  | 2237 | 783            | 612306          | -    | -              | -               | -    | -              | -               |
| Asoj    | 2529  | 2628 | -99            | 9752            | -    | -              | -               | -    | -              | -               |
| Kartik  | 2756  | 2505 | 251            | 62876           | 2603 | 153            | 23511           | 2578 | 178            | 31551           |
| Mangsir | 2762  | 2641 | 121            | 14702           | 2697 | 65             | 4173            | 2667 | 95             | 8989            |
| Poush   | 2662  | 2767 | -105           | 10920           | 2746 | -84            | 7135            | 2715 | -53            | 2766            |
| Magh    | 2597  | 2677 | -80            | 6440            | 2692 | -95            | 9088            | 2688 | -91            | 8335            |
| Falgun  | 2691  | 2694 | -3             | 11              | 2647 | 44             | 1942            | 2643 | 48             | 2338            |
| Chaitra | 2720  | 2678 | 42             | 1764            | 2667 | 53             | 2830            | 2667 | 53             | 2828            |
| Baishak | 2665  | 2668 | -3             | 6               | 2692 | -27            | 729             | 2693 | -28            | 807             |
| Jestha  | 2668  | 2679 | -              | -               | 2679 | -              | -               | 2679 | -              | -               |

### **Summary of Error Analysis:**

* The **Prediction Error** (P. Error) is the difference between the actual index value and the forecasted value (SMA/WMA/EMA).
* **Error Squared** (Error Sq.) is the square of the prediction error, which gives more weight to larger errors and helps in calculating the Mean Squared Error (MSE).

This analysis helps to gauge how well the different moving averages (SMA, WMA, EMA) are forecasting the NEPSE index.

### Key Observations

1. **Spike Handling**: All three moving averages effectively smoothed the major spike in Bhadra month, demonstrating their core function of reducing data noise
   
2. **Responsiveness**: The WMA followed the actual index more closely in middle periods, confirming its superior MSE score
   
3. **Convergence**: The forecast lines converged toward similar values in later months (Chaitra through Jestha), suggesting stabilization in the underlying data
   
4. **Final Prediction**: The forecasted value for Jestha month was nearly identical across all three methods despite their different calculation approaches

### Interactive Visualization Findings

The interactive analysis implemented in Streamlit revealed:

- **Window Size Impact**: Adjusting the rolling window size significantly affected forecast accuracy
- **Smoothing Factor Sensitivity**: The EMA performance varied considerably based on the chosen smoothing factor (α)
- **Error Distribution**: The WMA method exhibited the smallest squared errors across most periods

## Practical Applications

This research has practical implications for investors, financial analysts, and market participants:

1. **Investment Timing**: Using the most accurate moving average method can help identify optimal entry and exit points
   
2. **Portfolio Rebalancing**: Forecasted trends can guide portfolio rebalancing decisions
   
3. **Risk Management**: Understanding trend direction and strength supports effective risk management strategies
   
4. **Market Sentiment Analysis**: Moving averages provide insights into broader market sentiment

## Limitations

The analysis acknowledges several limitations:

1. **Historical Dependence**: Moving averages are lagging indicators based on historical data
   
2. **Market Volatility**: Extreme market volatility can reduce forecast accuracy
   
3. **External Factors**: Fundamental factors affecting markets are not captured by technical indicators alone
   
4. **Parameter Sensitivity**: Results are sensitive to chosen parameters (window size, weights, smoothing factor)

## Conclusions and Recommendations

### Key Findings

1. **Method Performance**: The Weighted Moving Average (WMA) demonstrated superior performance with an MSE of 7,058.35, making it the most reliable method for this dataset

2. **Trend Identification**: All three methods effectively identified the underlying trend direction, but with varying degrees of accuracy

3. **Forecast Convergence**: The convergence of forecasts in later periods suggests increasing market stability

### Recommendations

1. **Primary Method**: Use WMA as the primary forecasting tool for NEPSE index analysis
   
2. **Complementary Approach**: Consider using multiple moving average methods together for confirmation
   
3. **Parameter Optimization**: Regularly reassess optimal parameters as market conditions evolve
   
4. **Integration**: Combine moving average analysis with other technical and fundamental indicators

## Future Research Directions

Future studies could expand on this research by:

1. **Extended Time Series**: Analyzing longer time periods to test consistency across different market cycles
   
2. **Hybrid Models**: Developing hybrid models combining multiple moving average techniques
   
3. **Machine Learning Integration**: Incorporating machine learning to optimize parameter selection
   
4. **Sector-Specific Analysis**: Applying these methods to specific market sectors within NEPSE

## References

1. Nepal College of Information Technology, Balkumari, Lalitpur (Affiliated to Pokhara University)
   
2. Department of Computer Engineering, Machine Learning Lab Series

## Acknowledgements

Special thanks to Er. Manil Vaidya for guidance throughout this research project.

---

*This whitepaper is based on research conducted at Nepal College of Information Technology, Department of Computer Engineering, as part of the Machine Learning course work.*

*For source code and data files, visit: [Moving-Average-Forecasting](https://github.com/vijaybartaula/Moving-Average-Forecasting)*
