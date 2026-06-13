# AI Portfolio Analyzer — ML-Based Dynamic Equity Allocation

## Overview

AI Portfolio Analyzer is a finance and machine learning project that builds and backtests dynamic allocation strategies on Apple stock (AAPL).

The objective is not to claim that machine learning can systematically beat the market, but to build a complete and realistic finance/ML pipeline:

* financial data extraction
* feature engineering
* machine learning classification
* probability-based allocation rules
* out-of-sample backtesting
* benchmark comparison
* risk-adjusted performance analysis

The project compares machine learning-based strategies against passive benchmarks such as Apple Buy & Hold, SPY and QQQ.

---

## Project Objective

The main research question is:

> Can machine learning signals improve a dynamic allocation strategy on Apple stock compared to passive benchmarks?

The project tests whether historical market signals such as returns, momentum, moving averages and volatility can be transformed into investment decisions.

---

## Methodology

The workflow follows the structure below:

1. Download historical market data using Yahoo Finance
2. Clean and align financial time series
3. Compute daily returns
4. Create financial features:

   * Apple returns
   * Nasdaq returns
   * S&P 500 returns
   * Dow Jones returns
   * moving averages
   * momentum
   * volatility
   * trend signals
5. Create a target variable:

   * `1 = Buy`
   * `0 = Do not buy`
6. Split the dataset chronologically into training and testing sets
7. Train machine learning models
8. Convert prediction probabilities into allocation weights
9. Backtest the strategies
10. Compare results against passive benchmarks

---

## Models Tested

Two machine learning models were tested:

### 1. Logistic Regression

Used as the baseline model.

### 2. Random Forest Classifier

Used to test whether a non-linear model could improve performance compared to the baseline.

---

## Benchmarks

The ML strategies are compared against:

* Apple Buy & Hold
* SPY ETF
* QQQ ETF

These benchmarks are important because they show whether the machine learning strategy adds value compared to simple passive alternatives.

---

## Final Results

| Strategy                     | Final Return (%) | Annualized Volatility (%) | Sharpe Ratio | Max Drawdown (%) |
| ---------------------------- | ---------------: | ------------------------: | -----------: | ---------------: |
| Logistic Regression Strategy |           120.12 |                     24.80 |         0.97 |           -32.71 |
| Random Forest Strategy       |           115.98 |                     24.78 |         0.95 |           -37.94 |
| Apple Buy & Hold             |           140.38 |                     25.45 |         1.06 |           -33.36 |
| SPY                          |           102.09 |                     15.17 |         1.30 |           -18.76 |
| QQQ                          |           176.38 |                     19.98 |         1.49 |           -22.77 |

---

## Key Findings

The Logistic Regression strategy outperformed the Random Forest strategy among the tested machine learning models.

However, passive benchmarks such as QQQ and Apple Buy & Hold performed better over the test period. This highlights the difficulty of outperforming strong technology benchmarks using relatively simple machine learning models.

The project also shows that classification accuracy alone is not enough in finance. A model must be evaluated through financial metrics such as cumulative return, volatility, Sharpe ratio and maximum drawdown.

---

## Main Takeaways

* Logistic Regression was the best-performing ML model in this study.
* Random Forest did not improve the risk-adjusted performance.
* QQQ remained the strongest benchmark over the test period.
* A more complex model does not necessarily lead to better financial performance.
* Backtesting is essential to evaluate whether a prediction model has practical investment value.
* Benchmarking is necessary to measure the real added value of an active strategy.

---

## Tech Stack

* Python
* pandas
* numpy
* yfinance
* scikit-learn
* matplotlib
* Jupyter Notebook

---

## Repository Structure

```text
AI-Portfolio-Analyzer/
│
├── AI_Portfolio_Analyzer.ipynb
├── requirements.txt
└── README.md
```

---

## Disclaimer

This project is for educational and research purposes only.
It is not financial advice.
