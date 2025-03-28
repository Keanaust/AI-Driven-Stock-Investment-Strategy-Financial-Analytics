# AI-Driven Stock Investment Strategy – DARES Team 

## Overview

This project showcases a machine learning (ML)-driven investment strategy developed by **DARES**, the in-house Data Analytics and Research team at a financial investment firm. Facing pressure to compete with existing AI-driven products, we designed a predictive system to identify portfolios expected to outperform the market.

> Our mission: **Predict future 3-month stock winners based on historical data using ML models**, benchmark against passive strategies, and explore GPT-based stock picking as a novel alternative.

---

## Project Objective

- **Goal**: Forecast Top 30 and Bottom 30 performing stocks over a 3-month future window.
- **Target**: Build an investment product using ML predictions backed by backtesting evidence.
- **Scope**: Excludes Financials, Real Estate, and Utilities.
- **Bonus**: Compare ML predictions against ChatGPT's portfolio selections using LLM prompting.

---

## Methodology

### Step 1: Data Preparation and EDA
- Data sourced from CRSP/Compustat-style financials (2015–2023).
- Merged datasets containing valuation ratios, profitability, liquidity metrics, sector indicators, and past returns.
- Target variable: **Forward 3-month returns**.
- Addressed cross-sectional + time-series nature using realistic rolling windows.
- Created Winner/Loser labels using Top 30 and Bottom 30 ranking methods.
- Data normalized using `StandardScaler`.

### Step 2: Machine Learning Modeling
- Model used: **XGBoost Regressor**
- Justification: Robust to noise, excellent with tabular data, strong performance and interpretability.
- Transformed target using log-return scaling for stability.
- Trained model on 3-year moving windows; predictions made for each subsequent quarter.
- Prevented lookahead bias and simulated real-world investment constraints.

---

## Model Performance

### Feature Importance Highlights
- **Consistent Signals**: Price Index, 3-Month and 12-Month Past Returns showed moderate predictive power.
- **Transient Spikes**: Pre-Tax Return, Asset Turnover, and Cash/Total Liabilities gained prominence in 2021–2022.
- **Low Impact Features**: Sector labels and accrual-based metrics had consistently low importance.

### Backtesting Results
- **Top 30 Predicted vs. Actual**:
  - Our model captured meaningful subsets of true winners.
  - Predicted Top 30 stocks generally performed above average, though not consistently beating the index.

- **Bottom 30 Filtering**:
  - Stronger success at identifying poor performers.
  - Avoiding bottom-tier stocks helped reduce downside risk.

---

## Real-World Portfolio Simulation (Q1 2024)

- **Portfolio Construction Date**: December 31, 2023.
- **Outcome**: ML-predicted portfolio **underperformed** the market in Q1 2024.
- **Insight**: Reinforced the importance of **adapting models to market regimes** and external macro conditions.

---

## GPT vs ML Strategy

We prompted ChatGPT with:
> “You are a financial AI advisor as of Dec 31, 2023. Select 30 stocks likely to perform well in Q1 2024 based on available data.”

### GPT Results:
- Portfolio composed of strong **tech** (MSFT, AAPL, GOOGL), **retail** (AMZN, NKE), and **auto/AI** (TSLA, META).
- GPT's portfolio had **stable, benchmark-like performance** – outperforming the ML strategy in Q1 2024.

### Final Verdict:
- **GPT**: Stable, intuitive, surprisingly competitive.
- **ML**: Higher upside but more volatile and sensitive to market shifts.
- **Conclusion**: GPT provides strategic value and complements ML-based strategies.

---

## Key Insights

- **No One-Size-Fits-All**: ML signals vary based on market regime.
- **ML Works Best When Tuned Dynamically**: Static models struggle to adapt in changing environments.
- **GPT Shows Potential**: LLMs can act as complementary tools in strategy development.
- **Product Not Ready Yet**: But we’ve laid a strong foundation.

  ---

## Output & Results

- **Check the Final_Model Script for detailed results!**


