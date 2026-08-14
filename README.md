# 📈 Stock Market Analysis and Prediction using PyTorch

This project aims to analyze the historical stock data of tech giants (Apple, Amazon, Google, Microsoft) and predict future prices using Deep Learning models (**LSTM and GRU**) via **PyTorch**.

## 🚀 Project Overview & Features

* **Exploratory Data Analysis (EDA):** Extracted historical data using the `yfinance` library. Conducted daily returns, moving averages, and correlation analysis between different tech stocks.
* **Data Preprocessing:** Scaled the 'Close' prices into a [0, 1] range using `MinMaxScaler`. Restructured the time-series data using a sliding window approach (60 days) to predict the next day's closing price.
* **PyTorch Integration:** Converted NumPy arrays into PyTorch Tensors and utilized `DataLoader` to feed the data into the models in batches (batch size of 16) for optimized training.
* **Deep Learning Models:** Built two distinct architectures using PyTorch's `nn.Module`:
  * 2-Layer **LSTM** Model
  * 2-Layer **GRU** Model (with a Dropout of 0.2)
* **Evaluation:** Trained the models using Mean Squared Error (MSE) loss and the Adam optimizer. Evaluated the final performance using the Root Mean Squared Error (RMSE) metric.

## 📊 Model Comparison (LSTM vs. GRU)

The project concludes with a performance and training time comparison between the two models:
* The GRU model trained faster than the LSTM due to having fewer parameters.
* Both models' test predictions were inverse-transformed and plotted against the actual historical closing prices to visually evaluate their accuracy.

## 🛠️ Technologies Used
* **Language:** Python 3
* **Data Gathering & Processing:** yfinance, Pandas, NumPy, Scikit-Learn
* **Visualization:** Matplotlib, Seaborn
* **Deep Learning Framework:** PyTorch
