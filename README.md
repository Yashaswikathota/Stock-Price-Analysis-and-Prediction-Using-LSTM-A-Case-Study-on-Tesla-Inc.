# Tesla Stock Price Prediction with LSTM

This project builds and tunes a **Long Short-Term Memory (LSTM)** neural network to forecast **Tesla (TSLA)** stock closing prices using historical stock data and technical indicators.

---

##  Project Objective

To accurately predict future closing prices of Tesla stock by training an LSTM model on time-series data enhanced with technical indicators such as **SMA**, **EMA**, and **RSI**.

---

## Dataset

- **Source**: `Tesla.csv` (included or expected to be provided)
- **Features**:
  - Date, Open, High, Low, Close, Adj Close, Volume

---

## Preprocessing

- Parsed and set `Date` as datetime index.
- Cleaned `Volume` by removing commas and converting to numeric.
- Dropped all missing values.
- Scaled all relevant numerical features using **MinMaxScaler**.

---

## Technical Indicators Used

- **SMA_10**: 10-day Simple Moving Average  
- **EMA_10**: 10-day Exponential Moving Average  
- **RSI**: Relative Strength Index

---

## Model Summary: LSTM

- **Input**: Time series window of historical stock prices and indicators
- **Architecture**:
  - LSTM Layer with dropout
  - Dense output layer (1 neuron)
- **Loss Function**: Mean Squared Error
- **Optimizer**: Adam
- **Regularization**: EarlyStopping and ModelCheckpoint

---

## Evaluation Metrics

The model was evaluated on the test set using the following metrics:

| Metric | Value |
|--------|-------|
| **RMSE** (Root Mean Squared Error) | **12.48** |
| **MAE** (Mean Absolute Error)      | **9.55**  |

---

## Results

- The model was able to capture the overall trend of Tesla stock prices.
- Predictions closely matched actual prices in the test set.
- Visualization included actual vs predicted closing prices.

---

## Project Structure

 Tesla-Stock-Prediction/
├── Tesla stock tuned-Copy1.ipynb # Main notebook
├── Tesla.csv # Input data file
└── README.md # Project documentation



