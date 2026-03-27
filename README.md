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




# ResumeIQ — AI-Powered Resume Ranker

An ML-powered resume screening tool that ranks candidates against a job description using TF-IDF vectorization, keyword analysis, experience detection, and education signals.

---

## File Structure

```
resume_ranker/
├── backend/
│   ├── app.py              # Flask REST API
│   ├── ranker.py           # ML ranking engine
│   └── requirements.txt    # Python dependencies
├── frontend/
│   ├── index.html          # Main UI
│   └── static/
│       ├── css/style.css   # Styles
│       └── js/app.js       # Frontend logic
├── uploads/                # Temp storage (auto-created)
└── README.md
```

---

## ML Pipeline

| Signal               | Weight | Method                          |
|----------------------|--------|---------------------------------|
| TF-IDF Similarity    | 40 %   | Cosine similarity (1-3 ngrams)  |
| Keyword Coverage     | 30 %   | Domain skill taxonomy matching  |
| Experience Level     | 15 %   | Regex extraction + normalise    |
| Education Level      | 10 %   | Keyword detection + weighting   |
| Section Completeness |  5 %   | Standard resume section count   |

**Grade bands:** Excellent (≥80) · Good (≥65) · Average (≥50) · Below Average (≥35) · Poor (<35)

---

## Setup & Run

### 1. Backend (Python 3.9+)

```bash
cd resume_ranker/backend
pip install -r requirements.txt
python app.py
# → Running on http://localhost:5000
```

### 2. Frontend

Open `frontend/index.html` in your browser directly, or serve it:

```bash
cd resume_ranker/frontend
python -m http.server 8080
# → http://localhost:8080
```

### 3. Use

1. Paste the **job description** in the textarea
2. **Upload resumes** (PDF, DOCX, or TXT)
3. Click **Rank Resumes**
4. Click any candidate card to see the **full score breakdown**

---

## API Endpoint

```
POST /api/rank
Content-Type: multipart/form-data

Fields:
  job_description  (string, required)
  resumes          (files, one or more)

Response:
{
  "success": true,
  "results": [
    {
      "rank": 1,
      "name": "john_doe.pdf",
      "score": 78.4,
      "grade": "Good",
      "tfidf_score": 82.1,
      "keyword_score": 75.0,
      "experience_score": 80.0,
      "education_score": 85.0,
      "section_score": 62.5,
      "matched_skills": ["python", "machine learning", ...],
      "missing_skills": ["kubernetes", ...],
      "word_count": 643
    },
    ...
  ]
}
```

---

## Supported File Types

- **PDF** — via PyPDF2
- **DOCX** — via python-docx
- **TXT** — plain text fallback
