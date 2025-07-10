# Stock Price Prediction using RNN & LSTM

Leverage historical stock data from Apple (AAPL), Google (GOOGL), and Microsoft (MSFT) to build and compare Recurrent Neural Network (RNN) and Long Short-Term Memory (LSTM) models for next-day price forecasting.

⸻

Table of Contents
	•	Project Overview
	•	Dataset
	•	Key Features
	•	Data Loading & Preprocessing
	•	Model Development
	•	Evaluation & Visualization
	•	Comparative Analysis
	•	Model Architectures
	•	Results and Analysis
	•	Quantitative Assessment
	•	Qualitative Assessment
	•	Prerequisites
	•	How to Run
	•	File Structure
	•	Contributing
	•	License
	•	Contact

⸻

Project Overview

Time-series forecasting of stock prices is a challenging problem due to non-linearity and market noise. This notebook walks through the full pipeline—data acquisition, cleaning, feature scaling, RNN/LSTM model training, evaluation, and visualization—to predict the next-day closing price of major tech stocks.

Dataset

Three CSV files sourced from Yahoo Finance:
	•	AAPL.csv — Apple daily OHLC and volume
	•	GOOGL.csv — Google daily OHLC and volume
	•	MSFT.csv — Microsoft daily OHLC and volume

Each file follows this schema:

Column	Description
Date	YYYY-MM-DD
Open	Opening price
High	Daily high
Low	Daily low
Close	Closing price
Adj Close	Adjusted closing price
Volume	Shares traded

Key Features

Data Loading & Preprocessing
	•	Read and merge multiple CSVs into one DataFrame
	•	Handle multi-level headers and rename for clarity
	•	Convert Date to datetime and numeric columns to float/int
	•	Apply Min–Max scaling to features
	•	Generate sliding-window sequences for time-series input

Model Development
	•	Simple RNN: Single recurrent layer + dense output
	•	LSTM: One or more LSTM layers for long-term dependency capture
	•	Implemented in Keras (TensorFlow backend)
	•	Trained on historical windows to predict next-day close

Evaluation & Visualization
	•	Metrics: Root Mean Squared Error (RMSE), Mean Absolute Error (MAE)
	•	Plot actual vs. predicted prices for visual inspection

Comparative Analysis
	•	Benchmark RNN vs. LSTM on AAPL, GOOGL, and MSFT
	•	Assess prediction lag, smoothness, and spike capture

Model Architectures
	1.	Simple RNN
	•	Input → RNN layer → Dense(output)
	2.	LSTM
	•	Input → LSTM layer(s) → Dense(output)

Both use Mean Squared Error loss, Adam optimizer, and early stopping on validation loss.

Results and Analysis

Quantitative Assessment

Ticker	Model	RMSE	MAE
AAPL	RNN	5.47	4.12
AAPL	LSTM	5.62	4.18
GOOGL	RNN	3.75	2.34
GOOGL	LSTM	4.57	3.07
MSFT	RNN	8.18	6.50
MSFT	LSTM	8.08	6.48

Qualitative Assessment
	•	Lag: Both models lag when price trends reverse abruptly.
	•	Smoothness: Predictions are generally smoother than ground truth, reducing over-reactivity to spikes.
	•	Spike handling: Occasional overshoot/undershoot suggests hyperparameter or sequence-length tuning.

Prerequisites
	•	Python 3.x
	•	Jupyter Notebook or JupyterLab

Required libraries:

pip install pandas yfinance numpy matplotlib scikit-learn tensorflow joblib

How to Run
	1.	Clone repository:





git clone https://github.com/Poojabumesh/LSTM-vs-RNN.git
cd LSTM-vs-RNN

2. **Place CSV files** next to `Final_Training_new.ipynb`:
   - `AAPL.csv`, `GOOGL.csv`, `MSFT.csv`
3. **Launch notebook**:
   ```bash
jupyter notebook Final_Training_new.ipynb

	4.	Execute cells sequentially to reproduce training, evaluation, and plots.

File Structure

LSTM-vs-RNN/
├── Final_Training_new.ipynb   # Jupyter Notebook with code & analysis
├── AAPL.csv                   # Apple historical data
├── GOOGL.csv                  # Google historical data
├── MSFT.csv                   # Microsoft historical data
└── README.md                  # This file

Contributing

Contributions, issues, and pull requests are welcome. Feel free to improve code, add features, or fix bugs.

License

This project is licensed under the MIT License. See LICENSE for details.

Contact
	•	Email: poojabumesh@gmail.com
	•	LinkedIn: https://www.linkedin.com/in/pooja-baraluumesh
