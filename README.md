📈 Stock Price Prediction using Recurrent Neural Networks (RNN & LSTM)
This repository contains a Jupyter Notebook (Final_Training_new.ipynb) that demonstrates building and comparing Recurrent Neural Networks (RNN) and Long Short-Term Memory (LSTM) models for stock price prediction. The project focuses on predicting future stock prices for major tech companies (AAPL, GOOGL, MSFT) using historical daily data.

🎯 Project Overview
The goal of this project is to explore the effectiveness of RNN and LSTM neural networks in forecasting stock prices. Stock price prediction is a challenging time-series problem due to its non-linear and non-stationary nature. This notebook covers the entire machine learning pipeline, from data acquisition and preprocessing to model training, evaluation, and visualization of predictions.

📊 Dataset
The project utilizes historical stock data for Apple (AAPL), Google (GOOGL), and Microsoft (MSFT). The data is provided as three separate CSV files: AAPL.csv, GOOGL.csv, and MSFT.csv sourced from Yahoo Finance. These individual datasets are then combined and processed within the Final_Training_new.ipynb notebook. Each dataset contains daily stock prices (Open, High, Low, Close) and trading volumes over a significant period.

Expected format for each CSV (e.g., AAPL.csv):

Date,Open,High,Low,Close,Adj Close,Volume
2010-01-04,7.622500,7.660714,7.585000,7.643214,6.440331,493729600
...

✨ Key Features
Data Pipeline: Reading, combining, cleaning, and scaling historical stock data.

Time-Series Sequencing: Preparing data for RNN/LSTM input.

Model Development: Implementation of Simple RNN and LSTM neural networks.

Performance Evaluation: Quantitative (RMSE, MAE) and qualitative assessment of predictions.

Comparative Analysis: Benchmarking RNN vs. LSTM performance across different stock tickers.

Interactive Visualizations: Plotting actual vs. predicted prices for clear insights.

🧠 Model Architectures
Both RNN and LSTM models are built using Keras (part of TensorFlow), designed to learn sequential dependencies in stock price data.

Simple RNN: A basic recurrent neural network layer followed by dense layers.

LSTM: Utilizes LSTM layers, known for better capturing long-term dependencies, making them often more suitable for time-series forecasting.

📈 Results and Analysis
The notebook provides a detailed quantitative and qualitative analysis of the models' performance, highlighting their strengths and weaknesses in stock price prediction.

Quantitative Assessment (RMSE & MAE):

AAPL & GOOGL: Simple RNN slightly outperforms LSTM, suggesting its sufficiency for short-term dependencies in these tickers.

AAPL: RNN (RMSE: 5.47) vs. LSTM (RMSE: 5.62)

GOOGL: RNN (RMSE: 3.75) vs. LSTM (RMSE: 4.57)

MSFT: LSTM holds a slight edge (RMSE: 8.08 vs. 8.18), indicating its gating mechanisms may benefit higher volatility.

Qualitative Assessment:

Lag & Smoothness: Both models show mild lag during abrupt price reversals. Predictions are smoother, reducing over-reactivity but potentially under-capturing sharp spikes.

Over/Under-shooting: Occasional over-shoots suggest potential for further tuning or regularization.

🛠️ Prerequisites
Ensure you have the following installed to run the notebook:

Python 3.x

Jupyter Notebook or JupyterLab

Required Python libraries:

pandas

yfinance (for initial data acquisition, if not using provided CSVs)

numpy

matplotlib

scikit-learn

keras (or tensorflow which includes Keras)

joblib

You can install these using pip:

pip install pandas yfinance numpy matplotlib scikit-learn tensorflow joblib

🚀 How to Run Locally
1. Clone the Repository
git clone https://github.com/Poojabumesh/LSTM-vs-RNN.git
cd LSTM-vs-RNN

(Note: Replace Poojabumesh and LSTM-vs-RNN with your actual GitHub username and repository name if different.)

2. Place the Datasets
Ensure the AAPL.csv, GOOGL.csv, and MSFT.csv files are placed in the same directory as the Final_Training_new.ipynb notebook.

3. Open the Jupyter Notebook
jupyter notebook Final_Training_new.ipynb

This will open the notebook in your web browser.

4. Run All Cells
Execute all cells in the notebook sequentially to reproduce the analysis, model training, and visualizations.

📂 File Structure
.
├── Final_Training_new.ipynb  # Main Jupyter Notebook with code and analysis
├── AAPL.csv                  # Historical stock data for Apple
├── GOOGL.csv                 # Historical stock data for Google
├── MSFT.csv                  # Historical stock data for Microsoft
└── README.md                 # This file

👋 Contributing
Feel free to open issues or submit pull requests if you have suggestions for improvements, bug fixes, or new features.

📄 License
This project is open-sourced under the MIT License.

📧 Contact
For any questions or collaborations, please reach out to poojabumesh@gmail.com or connect on LinkedIn.
