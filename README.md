#  Real-Time News Sentiment Classification and Dashboard (PySpark + Streamlit)

A real-time news analytics dashboard that fetches live headlines, performs sentiment analysis, and visualizes insights using **Streamlit**, **TextBlob**, and **PySpark-compatible storage (Parquet format)**.

This project demonstrates real-time data ingestion, NLP-based sentiment classification, and interactive dashboard visualization — ideal for Data Engineering + NLP portfolio projects.

---

##  Project Overview

This system:

- Fetches live news headlines using **NewsAPI**
- Falls back to **GNews** if NewsAPI fails
- Performs **sentiment classification** using TextBlob
- Stores predictions in **Parquet format**
- Displays:
  - Latest headlines
  - Sentiment distribution (Bar Chart)
  - Positive sentiment trend over time (Line Chart)

---

##  Architecture

### Workflow

1. **News Fetching**
   - NewsAPI (Primary)
   - GNews (Fallback)

2. **Sentiment Analysis**
   - TextBlob polarity score
   - Positive / Negative classification

3. **Storage**
   - Predictions stored as `.parquet` files
   - Enables PySpark scalability

4. **Visualization**
   - Interactive dashboard using Streamlit
   - Charts via Plotly

---

##  Project Structure

```
📦 real-time-news-sentiment
 ┣  real_time_news_sentiment_classification_and_dashboard_using_pyspark.py
 ┣  requirements.txt
 ┣  predictions_parquet/
 ┗  README.md
```

---

##  Requirements

```
streamlit
pandas
plotly
textblob
gnews
pyarrow
pyspark
```

---

##  Technologies Used

- Python
- Streamlit
- TextBlob (NLP)
- PySpark (Parquet Storage)
- Plotly
- NewsAPI
- GNews

---

##  Setup Instructions

### 1️. Clone Repository

```bash
git clone https://github.com/your-username/real-time-news-sentiment.git
cd real-time-news-sentiment
```

### 2️. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3️. Add NewsAPI Key

Inside the script, replace:

```python
NEWSAPI_KEY = "YOUR_API_KEY"
```

Get your API key from:

https://newsapi.org/

---

##  Run the Application

```bash
streamlit run real_time_news_sentiment_classification_and_dashboard_using_pyspark.py
```

Then open your browser:

```
http://localhost:8501
```

---

##  Dashboard Features

###  1. Latest Headlines Table

Displays:

- Published Date
- Source
- Headline
- Sentiment
- Probability Score

---

###  2. Sentiment Distribution

Bar chart showing count of:

- Positive
- Negative

---

###  3. Positive Sentiment Trend

Line chart over time tracking sentiment probability.

---

##  Sentiment Logic

```python
df['sentiment'] = df['title'].apply(
    lambda t: "Positive" if TextBlob(t).sentiment.polarity > 0 else "Negative"
)
```

- Polarity > 0 → Positive  
- Polarity ≤ 0 → Negative  

---

##  Data Storage

Each prediction batch is saved as:

```
predictions_parquet/pred_<uuid>.parquet
```

### Benefits

- Big data ready
- Spark-compatible
- Historical tracking enabled
- Easy integration with Spark Structured Streaming

---

## 📈 Example Output

| publishedAt | source | headline | sentiment | prob_pos |
|------------|--------|----------|-----------|----------|
| 2026-03-02 | CNN | Market hits record high | Positive | 0.65 |

---

##  Future Improvements

- Replace TextBlob with BERT / HuggingFace model
- Integrate PySpark Structured Streaming
- Add Kafka ingestion
- Add WordCloud visualization
- Add Neutral sentiment class
- Deploy on AWS / GCP / Azure
- Add Docker support
- Add Database storage (PostgreSQL / MongoDB)

---

##  Use Cases

- Media analytics
- Stock sentiment monitoring
- Political sentiment tracking
- Real-time event monitoring
- NLP + Streaming portfolio project
- Academic Big Data project

---

