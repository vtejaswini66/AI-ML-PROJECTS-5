# AI-ML-PROJECTS-5
#  Stock Price Prediction using LSTM

##  Project Overview

This project aims to predict the future stock prices using historical data and a Deep Learning model (LSTM – Long Short-Term Memory). The model learns patterns from past stock prices and forecasts the next day's closing price.

---

##  Objective

* Analyze historical stock price data
* Build a predictive model using LSTM
* Predict the next day's stock closing price
* Evaluate model performance using metrics

---

##  Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-learn
* TensorFlow / Keras
* Google Colab / Jupyter Notebook

---

##  Dataset

The dataset contains stock market data with the following columns:

* Date
* Open
* High
* Low
* Close
* Adjusted Close
* Volume

The model mainly uses the **Close price** for prediction.

---

##  Project Workflow

1. Data Loading
2. Data Preprocessing (Normalization)
3. Sequence Creation for Time Series
4. Model Building (LSTM)
5. Model Training
6. Prediction
7. Model Evaluation
8. Visualization

---

##  Model Used

**LSTM (Long Short-Term Memory)** – A type of Recurrent Neural Network (RNN) suitable for time-series forecasting.

---

##  Results

*  Next Day Predicted Price
*  Actual vs Predicted Graph
*  Model Evaluation Metrics

### Metrics Used:

* R² Score
* RMSE (Root Mean Squared Error)

---

##  Output Example

Next Day Predicted Price: 231.45
R2 Score: 0.91
RMSE: 2.35

---

##  Repository Structure

Stock-Price-Prediction
│
├── stock_sample_dataset.csv
├── stock_prediction.ipynb
├── prediction_graph.png
└── README.md

---

##  How to Run the Project

1. Clone the repository
2. Open the notebook in Google Colab or Jupyter Notebook
3. Upload the dataset
4. Run all cells

---

## Future Improvements

* Use real-time stock data (API integration)
* Improve model accuracy with deeper LSTM layers
* Deploy as a web application (Streamlit)
* Add multiple stock predictions

---

##  Conclusion

This project demonstrates how deep learning models like LSTM can be used for time-series forecasting. It provides insights into stock trends and helps understand predictive modeling in finance.


