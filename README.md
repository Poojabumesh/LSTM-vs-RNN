# 📈 Stock Price Prediction using Recurrent Neural Networks (RNN & LSTM)
This repository contains a Jupyter Notebook **('Final_Training_new.ipynb')** that demonstrates building and comparing **Recurrent Neural Networks (RNN)** and **Long Short-Term Memory (LSTM)** models for stock-price prediction.  
The project focuses on predicting future prices for major tech companies **AAPL, GOOGL, MSFT** using historical daily data.

## 🎯 Project Overview
The goal is to explore the effectiveness of RNN and LSTM architectures in forecasting stock prices—an inherently **non-linear** and **non-stationary** time-series problem.  
The notebook walks through the complete ML pipeline:

* Data acquisition & preprocessing  
* Model training (RNN & LSTM)  
* Evaluation (quantitative & qualitative)  
* Visualisation of predictions  
--
## 📊 Dataset
The project utilizes historical stock data for Apple (AAPL), Google (GOOGL), and Microsoft (MSFT). The data is provided as three separate CSV files: AAPL.csv, GOOGL.csv, and MSFT.csv sourced from Yahoo Finance. These individual datasets are then combined and processed within the Final_Training_new.ipynb notebook. Each dataset contains daily stock prices (Open, High, Low, Close) and trading volumes over a significant period.

### Expected format for each CSV (e.g., AAPL.csv):
```csv
Date,Open,High,Low,Close,Adj Close,Volume
2010-01-04,7.622500,7.660714,7.585000,7.643214,6.440331,493729600
...
```
--
## ✨ Key Features
- **Data Pipeline** – reading, combining, cleaning, and scaling historical stock data  
- **Time-Series Sequencing** – preparing sliding-window sequences for RNN/LSTM input  
- **Model Development** – implementation of **Simple RNN** and **LSTM** neural networks  
- **Performance Evaluation** – quantitative (**RMSE**, **MAE**) and qualitative assessment of predictions  
- **Comparative Analysis** – benchmarking **RNN vs LSTM** across different stock tickers  
- **Interactive Visualizations** – plotting actual vs predicted prices for clear insight
--
## 🧠 Model Architectures
Both models are implemented in **Keras /TensorFlow** to learn sequential dependencies in stock-price data.

| Architecture | Layer Stack | Strength |
|--------------|-------------|----------|
| **Simple RNN** | `SimpleRNN → Dense` | Lightweight; captures short-term patterns |
| **LSTM** | `LSTM → Dense` | Gated cells retain long-term context; often better for volatile series |

## 📈 Results and Analysis
The notebook provides a detailed quantitative and qualitative analysis of the models' performance, highlighting their strengths and weaknesses in stock price prediction.

### Quantitative Assessment (RMSE & MAE)
- **AAPL & GOOGL**: Simple RNN slightly outperforms LSTM, suggesting its sufficiency for short-term dependencies.  
  - **AAPL**: RNN (RMSE: 5.47) vs. LSTM (RMSE: 5.62)  
  - **GOOGL**: RNN (RMSE: 3.75) vs. LSTM (RMSE: 4.57)  
- **MSFT**: LSTM holds a slight edge (RMSE: 8.08 vs. 8.18), indicating its gating mechanisms may benefit higher volatility.

### Qualitative Assessment
- **Lag & Smoothness** – Both models show mild lag during abrupt price reversals. Predictions are smoother, reducing over-reactivity but potentially under-capturing sharp spikes.  
- **Over/Under-shooting** – Occasional over-shoots suggest potential for further tuning or regularization.

---

## 🛠️ Prerequisites

Ensure you have the following installed to run the notebook:

- Python 3.x  
- Jupyter Notebook or JupyterLab  

Required Python libraries:

```bash
pip install pandas yfinance numpy matplotlib scikit-learn tensorflow joblib
```
## 🚀 How to Run Locally
### 1. Clone the Repository
```bash
git clone https://github.com/Poojabumesh/LSTM-vs-RNN.git
cd LSTM-vs-RNN
```
(Note: Replace Poojabumesh and LSTM-vs-RNN with your actual GitHub username and repository name if different.)

### 2. Place the Datasets
Ensure the AAPL.csv, GOOGL.csv, and MSFT.csv files are placed in the same directory as the Final_Training_new.ipynb notebook.

### 3. Open the Jupyter Notebook
```bash
jupyter notebook Final_Training_new.ipynb
```
This will open the notebook in your web browser.

### 4. Run All Cells
Execute all cells in the notebook sequentially to reproduce the analysis, model training, and visualizations.

## 📂 File Structure
```
.
├── Final_Training_new.ipynb  # Main Jupyter Notebook with code and analysis
├── AAPL.csv                  # Historical stock data for Apple
├── GOOGL.csv                 # Historical stock data for Google
├── MSFT.csv                  # Historical stock data for Microsoft
└── README.md                 # This file
```
## 👋 Contributing
Feel free to open issues or submit pull requests if you have suggestions for improvements, bug fixes, or new features.

## 📧 Contact
For any questions or collaborations, please reach out to poojabumesh@gmail.com or connect on LinkedIn.
