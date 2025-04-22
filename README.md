# Hybrid ARIMAX-LSTM for DBO Price Forecasting

This project applies advanced time series modeling techniques to forecast the daily closing prices of the Invesco DB Oil Fund (DBO), an oil-backed ETF. It combines traditional statistical modeling (ARIMAX) with deep learning (LSTM) in a hybrid framework to capture both linear and nonlinear market dynamics.

## Project Overview

- **Objective:** Improve forecasting accuracy for DBO prices by leveraging a hybrid model that combines ARIMAX and LSTM.
- **Scope:** Evaluate standalone ARIMAX, standalone LSTM, and a hybrid ARIMAX-LSTM model using historical financial and economic data from 2010 to 2025.
- **Key Inputs:**
  - Historical DBO closing prices
  - Exogenous variables: WTI crude oil prices and USD index (DXY)
  - Technical indicators: Moving Averages, RSI, etc.

## Models Used

### 1. **ARIMAX**
- Captures linear temporal patterns with exogenous variables.
- Best-fit: ARIMAX(1,1,1)

### 2. **LSTM**
- Neural network for sequence modeling with 2 stacked LSTM layers and dense output layers.
- Trained with normalized technical indicators and sliding input windows.

### 3. **Hybrid ARIMAX-LSTM**
- Stage 1: ARIMAX forecasts linear structure.
- Stage 2: LSTM models ARIMAX residuals to capture nonlinear components.
- Final output = ARIMAX forecast + LSTM residual prediction.

## Results Summary

| Model   | MAE   | MAPE (%) | RMSE  |
|---------|-------|----------|--------|
| ARIMAX | 2.57  | 18.27    | 2.62  |
| LSTM   | 0.50  | 3.63     | 0.62  |
| Hybrid | **0.27** | **1.93** | **0.34** |

The hybrid model significantly outperformed standalone models, especially during periods of volatility.

## Visualization

- Figure: Model forecasts vs actual prices (May 2024–Apr 2025)
- Observations: Hybrid model tracks actual prices most closely.

## Files in this Repo

- `DBO Price Forecasting.ipynb`: Final Jupyter Notebook with complete workflow
- `Hybrid_ARIMAX-LSTM_Modeling_for_Oil_ETF_Price_Forecasting.pdf`: 2-page IEEE-format summary report

## Key Takeaways

- Hybrid models enhance financial forecasting by leveraging complementary strengths.
- LSTM captures nonlinearity, while ARIMAX handles temporal autocorrelation with exogenous factors.
- Future improvements could include sentiment analysis and transformer models.

## Author

Chenming Dai  
Department of Economics  
University of Michigan  
Email: cmdai@umich.edu

---

**Course:** STATS 507 – Data Science Analytics using Python
