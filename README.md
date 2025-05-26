# Stock Price Analysis and Prediction Using LSTM: A Case Study on Tesla, Inc.


> **Disclaimer :** This repository is for educational research only and **does not constitute investment advice**. All opinions are the author’s own.

---

## Overview

This project investigates the historical performance of **Tesla, Inc. (TSLA)** and builds a forecasting model using **Long Short‑Term Memory (LSTM)** neural networks. Traditional descriptive statistics, technical indicators, and deep‑learning models are combined to explore price behaviour, quantify risk, and generate next‑day close‑price predictions.

Key deliverables :

* Exploratory data analysis (EDA) notebooks with interactive visualisations.
* A reproducible LSTM model pipeline (data prep → training → inference).
* Comparison of naïve baselines vs. LSTM (RMSE, MAE).
* Ready‑to‑use scripts for retraining on updated price data.

---

## Theoretical Foundations

|  Approach                        |  Why it matters                                                                                                                   |
| -------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| Moving Averages (10‑/20‑/50‑day) | Identify short‑ & long‑term trends and crossover signals.                                                                         |
| Daily Returns & Volatility       | Gauge risk by measuring distribution of log returns.                                                                              |
| LSTM Networks                    | Capture non‑linear, long‑range dependencies in noisy time‑series data; address vanishing‑gradient issues typical of vanilla RNNs. |

A concise literature survey is provided in `docs/references.md`.

---

##  Data

* **Source** : [Yahoo Finance](https://finance.yahoo.com/quote/TSLA/)
* **Period covered** : ≈ 1 692 trading days (≈ Jan‑2017 ➜ May‑2023)
* **Fields used** : Date | Open | High | Low | Close | Adj Close | Volume
* Data files live in `data/raw/` and are fetched automatically via [`yfinance`](https://github.com/ranaroussi/yfinance).

---

## 🗂 Repository Structure

```
.
├── data
│   ├── raw/              <- Unmodified CSV downloaded from Yahoo Finance
│   └── processed/        <- Scaled/engineered features ready for modeling
├── notebooks
│   ├── 01_EDA.ipynb      <- Descriptive statistics & visualisations
│   └── 02_Model_LSTM.ipynb <- Model building & evaluation
├── src
│   ├── data_preparation.py
│   ├── model.py          <- LSTM architecture & loss function
│   ├── train.py          <- CLI for model training & hyper‑param tuning
│   └── utils.py
├── results
│   ├── figures/          <- Auto‑generated plots
│   └── predictions.csv   <- Model outputs on test split
├── requirements.txt
└── README.md             <- *you are here*
```

---

## 📈 Results Snapshot

|  Metric  |  Validation  |  Test    |
| -------- | ------------ | -------- |
| RMSE     |  \~5.87      |  \~7.12  |
| MAE      |  \~4.63      |  \~5.48  |
| MAPE     |  \~3.8 %     |  \~4.2 % |

Predicted vs. actual closing prices show tight alignment, indicating the LSTM successfully internalises sequential patterns.

---

## Future Work

* Incorporate macro‑economic features (CPI, Fed rates).
* Integrate sentiment scores from Twitter/Reddit.
* Experiment with attention‑based architectures (e.g., Transformers).

##  References

* Hochreiter, S., & Schmidhuber, J. (1997). *Long Short‑Term Memory*. Neural Computation.
* Fischer, T., & Krauss, C. (2018). *Deep learning with long short‑term memory networks for financial market predictions*. European Journal of Operational Research.
* Brownlee, J. (2020). *Deep Learning for Time Series Forecasting: Predict the Future with MLPs, CNNs and LSTMs in Python*. Machine Learning Mastery.

