# Real-Time News Sentiment Analytics Dashboard

A real-time news analytics system that collects live news headlines, performs sentiment analysis, and visualizes insights through an interactive dashboard.

This project demonstrates **real-time data ingestion, NLP-based sentiment classification, scalable data storage, and interactive data visualization**, making it suitable for **Data Analytics, Data Engineering, and NLP portfolios**.

---

# Problem Statement

Monitoring public sentiment across news sources is challenging because thousands of headlines are published every hour. Manually analyzing these headlines is inefficient and time-consuming.

This project builds a **real-time sentiment analytics system** that automatically collects news headlines, analyzes sentiment using Natural Language Processing (NLP), and visualizes trends through an interactive dashboard.

The system helps analysts quickly understand **public opinion trends across global news sources.**

---

# Project Overview

The system performs the following tasks:

1. Fetches **live news headlines** from NewsAPI
2. Uses **GNews as a fallback** if NewsAPI fails
3. Performs **sentiment classification using TextBlob**
4. Stores results in **Parquet format (PySpark-compatible)**
5. Displays insights through a **Streamlit interactive dashboard**

---

# Key Features

* Real-time news headline collection
* NLP-based sentiment classification
* Interactive analytics dashboard
* Sentiment distribution visualization
* Sentiment trend analysis over time
* Big data compatible storage using **Parquet**

---

# Data Pipeline Architecture

NewsAPI / GNews
↓
Headline Collection
↓
Sentiment Analysis (TextBlob NLP)
↓
Parquet Storage (PySpark Compatible)
↓
Interactive Dashboard (Streamlit + Plotly)

---

# Dashboard Features

## 1. Latest Headlines Table

Displays real-time news headlines with:

* Published date
* News source
* Headline text
* Sentiment label
* Sentiment probability score

## 2. Sentiment Distribution

A bar chart showing the number of:

* Positive headlines
* Negative headlines

## 3. Sentiment Trend Over Time

A line chart tracking the **trend of positive sentiment over time**.

This helps identify **changes in public sentiment related to news events**.

---

# Sentiment Classification Logic

Sentiment is determined using **TextBlob polarity scores**.

Polarity > 0 → Positive
Polarity ≤ 0 → Negative

Example implementation:

```python
df['sentiment'] = df['title'].apply(
    lambda t: "Positive" if TextBlob(t).sentiment.polarity > 0 else "Negative"
)
```

TextBlob analyzes the emotional tone of each headline and assigns a sentiment label.

---

# Data Storage

All predictions are stored as **Parquet files**, enabling scalable big data processing.

Example storage format:

```
predictions_parquet/pred_<uuid>.parquet
```

Benefits:

* Efficient columnar storage
* Compatible with **PySpark and big data pipelines**
* Enables historical analysis of sentiment trends

---

# Project Structure

```
real-time-news-sentiment
│
├── real_time_news_sentiment_classification_and_dashboard_using_pyspark.py
├── requirements.txt
├── predictions_parquet/
└── README.md
```

---

# Technologies Used

Python
Streamlit
TextBlob (NLP)
PySpark-compatible storage (Parquet)
Plotly (Visualization)
Pandas (Data Processing)
NewsAPI
GNews

---

# Requirements

```
streamlit
pandas
plotly
textblob
gnews
pyarrow
pyspark
```

Install dependencies:

```
pip install -r requirements.txt
```

---

# Setup Instructions

## 1. Clone the Repository

```
git clone https://github.com/your-username/real-time-news-sentiment.git
cd real-time-news-sentiment
```

---

## 2. Install Dependencies

```
pip install -r requirements.txt
```

---

## 3. Add NewsAPI Key

Inside the script, replace:

```
NEWSAPI_KEY = "YOUR_API_KEY"
```

You can obtain a free API key from:

https://newsapi.org/

---

# Run the Application

Start the Streamlit dashboard:

```
streamlit run real_time_news_sentiment_classification_and_dashboard_using_pyspark.py
```

Open in browser:

```
http://localhost:8501
```

---

# Example Output

| publishedAt | source | headline                | sentiment | prob_pos |
| ----------- | ------ | ----------------------- | --------- | -------- |
| 2026-03-02  | CNN    | Market hits record high | Positive  | 0.65     |

---

# Skills Demonstrated

Real-time data ingestion
Natural Language Processing (NLP)
Sentiment analysis
Interactive dashboard development
Data visualization
Big data compatible storage
Data pipeline design

---

# Future Improvements

* Replace TextBlob with **BERT / HuggingFace model**
* Implement **PySpark Structured Streaming**
* Add **Kafka streaming ingestion**
* Add **WordCloud visualization**
* Add **Neutral sentiment class**
* Deploy dashboard on **AWS / GCP / Azure**
* Add **Docker container support**
* Integrate **PostgreSQL or MongoDB storage**

---

# Use Cases

Media sentiment monitoring
Financial market sentiment analysis
Political sentiment tracking
Real-time news analytics
NLP portfolio project
Big Data academic project

---

# Author

Rashad
Data Analyst | Python | Power BI | SQL | PySpark

GitHub: https://github.com/RASHAD750
