Stock Price Prediction using Recurrent Neural Networks (RNN & LSTM)
This repository contains a Jupyter Notebook (Final_Training_new.ipynb) that demonstrates building and comparing Recurrent Neural Networks (RNN) and Long Short-Term Memory (LSTM) models for stock price prediction. The project focuses on predicting future stock prices for major tech companies (AAPL, GOOGL, MSFT) using historical daily data.

Table of Contents
Project Overview

Dataset

Key Features

Model Architectures

Results and Analysis

Prerequisites

How to Run

File Structure

Contributing

License

Contact

Project Overview
The goal of this project is to explore the effectiveness of RNN and LSTM neural networks in forecasting stock prices. Stock price prediction is a challenging time-series problem due to its non-linear and non-stationary nature. This notebook covers the entire machine learning pipeline, from data acquisition and preprocessing to model training, evaluation, and visualization of predictions.

Dataset
The project utilizes historical stock data for Apple (AAPL), Google (GOOGL), and Microsoft (MSFT). The data is provided as three separate CSV files: AAPL.csv, GOOGL.csv, and MSFT.csv sourced from Yahoo Finance. These individual datasets are then combined and processed within the Final_Training_new.ipynb notebook. Each dataset contains daily stock prices (Open, High, Low, Close) and trading volumes over a significant period.

Expected format for each CSV (e.g., AAPL.csv):

Date,Open,High,Low,Close,Adj Close,Volume
2010-01-04,7.622500,7.660714,7.585000,7.643214,6.440331,493729600
...

Key Features
Data Loading & Preprocessing:

Reading historical stock data from individual CSV files (AAPL.csv, GOOGL.csv, MSFT.csv).

Combining multiple stock datasets into a unified DataFrame.

Handling multi-level headers and renaming columns for clarity.

Converting data types (e.g., Date to datetime, numerical columns to float/int).

Min-Max Scaling of features for neural network input.

Creating sequences for time-series forecasting.

Model Development:

Implementation of a Simple RNN model.

Implementation of an LSTM (Long Short-Term Memory) model.

Training both models on historical stock data.

Evaluation & Visualization:

Evaluating model performance using metrics like Root Mean Squared Error (RMSE) and Mean Absolute Error (MAE).

Visualizing actual vs. predicted stock prices for qualitative assessment.

Comparative Analysis:

Comparing the performance of RNN and LSTM models across different stock tickers (AAPL, GOOGL, MSFT).

Qualitative assessment of prediction lag, smoothness, and over/under-shooting.

Model Architectures
Both RNN and LSTM models are built using Keras (part of TensorFlow). The models are designed to learn sequential dependencies in the stock price data.

Simple RNN: A basic recurrent neural network layer followed by dense layers.

LSTM: Utilizes LSTM layers, which are better at capturing long-term dependencies compared to simple RNNs, making them often more suitable for time-series data.

Results and Analysis
The notebook provides a detailed quantitative and qualitative analysis of the models' performance.

Quantitative Assessment (RMSE & MAE):

AAPL & GOOGL: The Simple RNN slightly outperforms the LSTM on AAPL (5.47 vs. 5.62 RMSE) and more noticeably on GOOGL (3.75 vs. 4.57 RMSE). This suggests that for these tickers, a simpler recurrent architecture might suffice for short-term dependencies. MAE reductions of ~0.06 (AAPL) and ~0.73 (GOOGL) indicate tighter average errors.

MSFT: The LSTM holds a very slight edge on MSFT (RMSE: 8.08 vs. 8.18), though MAE is nearly identical. This hints that the additional gating mechanisms in LSTM may help with the higher volatility seen in MSFT’s price series.

Qualitative Assessment:

Lag and Smoothness: Both models exhibit a mild lag when the price direction reverses abruptly. Predictions are generally smoother than the ground truth, which reduces over-reactivity but can under-capture sharp spikes.

Over/Under-shooting: Occasional over-shoots (e.g., RNN overshooting in MSFT around index 85) suggest room for regularization or sequence-length tuning.

Prerequisites
Before running the notebook, ensure you have the following installed:

Python 3.x

Jupyter Notebook or JupyterLab

Required Python libraries:

pandas

yfinance (though the data is loaded from CSV, this might be used for initial data acquisition)

numpy

matplotlib

scikit-learn

keras (or tensorflow which includes Keras)

joblib

You can install these using pip:

pip install pandas yfinance numpy matplotlib scikit-learn tensorflow joblib

How to Run
Clone the repository:

git clone https://github.com/Poojabumesh/LSTM-vs-RNN.git
cd LSTM-vs-RNN

(Note: Replace Poojabumesh and LSTM-vs-RNN with your actual GitHub username and repository name if different.)

Place the datasets:
Ensure the AAPL.csv, GOOGL.csv, and MSFT.csv files are in the same directory as the Final_Training_new.ipynb notebook.

Open the Jupyter Notebook:

jupyter notebook Final_Training_new.ipynb

This will open the notebook in your web browser.

Run all cells:
Execute all cells in the notebook sequentially to reproduce the analysis, model training, and visualizations.

File Structure
.
├── Final_Training_new.ipynb  # Main Jupyter Notebook with code and analysis
├── AAPL.csv                  # Historical stock data for Apple
├── GOOGL.csv                 # Historical stock data for Google
├── MSFT.csv                  # Historical stock data for Microsoft
└── README.md                 # This file

Contributing
Feel free to open issues or submit pull requests if you have suggestions for improvements, bug fixes, or new features.

Contact
For any questions or collaborations, please reach out to poojabumesh@gmail.com / https://www.linkedin.com/in/pooja-baraluumesh.
