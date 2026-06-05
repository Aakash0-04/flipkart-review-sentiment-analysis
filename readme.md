# Flipkart Review Sentiment 
![Python](https://img.shields.io/badge/Python-3.x-blue)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-orange)
![FastAPI](https://img.shields.io/badge/FastAPI-API-green)
![NLP](https://img.shields.io/badge/NLP-Sentiment%20Analysis-red)

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

---

## Project Structure

```bash
flipkart-review-sentiment-analysis/
│
├── App/
│   └── main.py
│   └── sentiment_model.pkl
│
├── Data/
│   ├── Raw/
│   └── Processed/
│       ├── flipkart_cleaned.csv
│   └── EDA_Charts/
│
├── Notebooks/
│   ├── EDA.ipynb
│   ├── Preprocessing.ipynb
│   └── Model_Training.ipynb
│
├── Src/
│ ├── Data/
│ ├── preprocess_flipkart.ipynb
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

<h2>EDA Results</h2>

<table>
<tr>
<td align="center">
<b>Sentiment Distribution</b><br>
<img src="Data/EDA_Charts/sentiment_distribution.png" width="350">
</td>

<td align="center">
<b>Rating Distribution</b><br>
<img src="Data/EDA_Charts/Rating_distribution.png" width="350">
</td>
</tr>
</table>

---
<table>
<tr>
<td align="center">
<b>Review Length vs Sentiment</b><br>
<img src="Data/EDA_Charts/review_length_vs_sentiment.png" width="350">
</td>

<td align="center">
<b>Verified Purchase Analysis</b><br>
<img src="Data/EDA_Charts/sentiment_by_verified_purchase.png" width="350">
</td>
</tr>
</table>

---

<table>
<tr>
<td align="center">
<b>Product-wise Sentiment</b><br>
<img src="Data/EDA_Charts/sentiment_by_product.png" width="350">
</td>

<td align="center">
<b>Helpful Votes Analysis</b><br>
<img src="Data/EDA_Charts/helpful_upvotes_by_sentiment.png" width="350">
</td>
</tr>
</table>

<table>
<tr>
<td align="center">
<b>Word Cloud</b><br>
<img src="Data/EDA_Charts/world_cloud.png" width="350">
</td>

<td align="center">
<b>Confusion Matrix</b><br>
<img src="Data/EDA_Charts/confusion_matrix_balanced.png" width="350">
</td>
</tr>
</table>
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
