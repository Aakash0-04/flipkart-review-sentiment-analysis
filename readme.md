# Flipkart Review Sentiment Analysis

An end-to-end NLP and Machine Learning project that analyzes customer reviews of **Samsung Galaxy S24** and **iPhone 15** collected from Flipkart. The project includes data collection, preprocessing, exploratory data analysis (EDA), sentiment classification using **TF-IDF + Logistic Regression**, business insight generation, and a **FastAPI-based inference service** for real-time sentiment prediction.

---

## Project Overview

### Objectives

* Analyze customer sentiment from e-commerce product reviews.
* Identify key customer pain points and product strengths.
* Build a sentiment classification model for review prediction.
* Expose the trained model through a FastAPI inference service.

### Tech Stack

* Python
* Pandas
* NumPy
* Scikit-learn
* NLTK
* Matplotlib
* FastAPI
* Docker

---

## Project Structure

```bash
flipkart-review-sentiment-analysis/
│
├── App/
│   └── main.py
│
├── Data/
│   ├── Raw/
│   └── Processed/
│       ├── flipkart_cleaned.csv
│       └── EDA_Charts/
│
├── Notebooks/
│   ├── EDA.ipynb
│   ├── Preprocessing.ipynb
│   └── Model_Training.ipynb
│
├── Src/
│   └── sentiment_model.pkl
│
├── Report/
│   └── Insight_Report.pdf
│
├── Dockerfile
├── requirements.txt
└── README.md
```

## Dataset

* Reviews collected from Flipkart using a browser extension.
* Products analyzed:

  * Samsung Galaxy S24
  * Apple iPhone 15
* Dataset cleaned and processed for sentiment analysis.
* Class imbalance addressed using balancing techniques.

### Sentiment Labels

| Rating | Sentiment          |
| ------ | ------------------ |
| 4–5    | Positive           |
| 1–2    | Negative           |
| 3      | Neutral (EDA only) |

---

## Exploratory Data Analysis & Business Insights

Key findings from customer reviews:

### Positive Themes

* Camera quality received consistent praise.
* Display quality was frequently highlighted.
* Overall user satisfaction was strongly positive.

### Negative Themes

* Battery drain issues appeared in both devices.
* Heating concerns were reported by multiple users.
* Performance lag was occasionally reported during heavy usage.

### Additional Observations

* Negative reviews tend to be longer and more detailed.
* Verified buyers often provide more informative feedback.

---

## Model Development

### Feature Extraction

* TF-IDF Vectorization

### Classification Algorithm

* Logistic Regression

### Performance

| Metric   | Score |
| -------- | ----- |
| Accuracy | ~84%  |

The model achieved balanced performance across both positive and negative sentiment classes.

---

## FastAPI Inference Service

The trained model is served using FastAPI for real-time sentiment prediction.

### Run Locally

```bash
pip install -r requirements.txt

uvicorn App.main:app --reload
```

### Endpoints

API:

```text
http://127.0.0.1:8000
```

Swagger UI:

```text
http://127.0.0.1:8000/docs
```

### Sample Request

```json
{
  "review_text": "The phone heats up too quickly and the battery drains very fast."
}
```

### Sample Response

```json
{
  "predicted_sentiment": "negative"
}
```

---

## Results

Include screenshots from:

* Sentiment Distribution
* Rating Distribution
* Confusion Matrix
* FastAPI Swagger UI

Example:

```markdown
![Confusion Matrix](Data/Processed/EDA_Charts/confusion_matrix_balanced.png)
```

---

## Limitations

* Dataset limited to two smartphone products.
* Negative reviews were partially curated manually.
* Aspect-level sentiment analysis is not implemented.
* API currently runs locally.
* Docker configuration has not been production tested.

---

## Future Improvements

* Deploy FastAPI service on Render or Railway.
* Implement BERT-based sentiment classification.
* Perform aspect-based sentiment analysis.
* Build a Streamlit dashboard for model interaction.

---

## Author

Aakash Jaiswal

GitHub: Aakash0-04
