# Statistical-Arbitrage-Trading
This project implements **Statistical Arbitrage Trading** strategies, focusing on **stationarity, cointegration, and pairs trading**. The main objective is to identify mean-reverting asset pairs and execute trades based on statistical relationships rather than fundamental valuations.

## Key Concepts
### 1. Stationarity and Cointegration
- **Stationarity:** A time series is stationary if its statistical properties (mean, variance, and autocovariance) do not change over time. The **Augmented Dickey-Fuller (ADF) test** is used to check stationarity.
- **Cointegration:** Two time series are cointegrated if they share a long-term relationship, meaning their spread remains stable over time. The **OLS regression residual test** is used to determine cointegration.

### 2. Pairs Trading Strategy
Pairs trading is a market-neutral strategy that involves:
1. Identifying asset pairs with strong cointegration.
2. Monitoring the spread (difference in prices of the two assets).
3. Taking **long** positions when the spread is low and **short** positions when the spread is high.
4. Closing positions when the spread reverts to the mean.

## Implementation Steps
1. **Data Collection:** Historical data for currency pairs is retrieved using `yfinance`.
2. **Statistical Tests:** The ADF test and OLS regression are used to identify cointegrated pairs.
3. **Trade Signal Generation:**
   - Calculate the **spread** between the selected pair.
   - Compute **Z-scores** to detect deviations from the mean.
   - Define trading signals:
     - **Long**: If Z-score is below a threshold.
     - **Short**: If Z-score is above a threshold.
     - **Exit**: If Z-score returns to the mean.
4. **Backtesting:** The trading strategy is backtested to evaluate its performance using metrics like **Sharpe ratio, drawdown, and risk measures (VaR, cVaR)**.

## Results & Performance
- The **backtesting results** show key financial metrics:
  - **Sharpe Ratio**: Measures risk-adjusted returns.
  - **Sortino Ratio**: Adjusts for downside risk.
  - **Drawdown**: Measures potential losses.
  - **VaR (Value at Risk)**: Estimates potential losses in a given time frame.
  - **cVaR (Conditional VaR)**: Measures expected loss beyond VaR.

## Requirements
- Python
- Pandas
- NumPy
- Matplotlib
- Statsmodels
- YFinance

## How to Run
1. Install dependencies:  
   ```bash
   pip install numpy pandas matplotlib statsmodels yfinance
   ```
2. Run the script:
   ```bash
   python statistical_arbitrage.py
   ```

## Future Enhancements
- Improve **entry/exit thresholds** using machine learning.
- Extend strategy to **equities and commodities**.
- Implement **real-time trading** with a broker API.

---
This project serves as a **template** for statistical arbitrage strategies and can be extended to various financial markets.

