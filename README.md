# FUTURE_ML_02
This repository will contain code related to an attempt to predict SP500 stock prices using LSTM 
# SP500 Stock Price Prediction using LSTM

## Project Overview

This project aims to predict the future prices of the SP500 stock index using a Long Short-Term Memory (LSTM) neural network. The goal is to provide insights into potential market trends and assist in investment decisions. We utilize historical closing prices and calculated logarithmic returns as features.

## Model Description

The model employed is a Sequential LSTM neural network built with Keras and TensorFlow. It uses a look-back period of 60 days to predict the next day's closing price. The model architecture consists of:

* Two LSTM layers with 50 units each.
* Dropout layers (20%) to prevent overfitting.
* Batch normalization to improve training stability.
* A dense output layer with a single neuron for predicting the closing price.

The model is trained using the Adam optimizer with a learning rate of 0.0001 and Mean Squared Error (MSE) loss. Early stopping is implemented to prevent overfitting and restore the best model weights based on validation loss.

**Features:**

* `Close`: Daily closing price of the SP500 index.
* `log_returns`: Logarithmic returns calculated from the closing prices.

**Libraries:**

* `tensorflow` and `keras`: For building and training the LSTM model.
* `pandas`: For data manipulation.
* `numpy`: For numerical operations.
* `yfinance`: For downloading historical stock data.
* `matplotlib`: For plotting results.
* `sklearn`: For data preprocessing (MinMaxScaler) and model evaluation (mean_squared_error).

**Preprocessing:**

* Data is downloaded from Yahoo Finance.
* Logarithmic returns are calculated and added as a feature.
* Data is split into training (80%) and testing (20%) sets.
* Separate `MinMaxScaler` scalers are used for the `Close` price and the combined `Close` and `log_returns` features.
* The data is transformed into a time-series format with a look-back period of 60 days.

**Training:**

* The model is trained for a maximum of 50 epochs with a batch size of 32.
* Early stopping is used to monitor validation loss and prevent overfitting.
