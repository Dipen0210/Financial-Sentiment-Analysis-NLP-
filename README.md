# 📈 FinBERT Sentiment-Based Trading Signal Generator & Fine-Tuning Pipeline

This repository contains two interconnected projects:
1. **Fine-tuning FinBERT on a financial news sentiment dataset**.
2. **Using the fine-tuned FinBERT model to generate trading signals** based on real-time news, technical indicators (RSI, MACD), and performing backtesting.

---

## 📌 Project 1: Fine-Tuning FinBERT for Financial Sentiment Analysis

### 🧠 Overview

This project fine-tunes the pre-trained [FinBERT model](https://huggingface.co/yiyanghkust/finbert-tone) on a labeled dataset of financial news headlines to enhance domain-specific sentiment analysis performance.

### 🔧 Steps

1. **Environment Setup**
   ```bash
   pip install transformers datasets evaluate torch
   ```

2. **Data Preparation**
   - Load the dataset (`all-data.csv`)
   - Clean and map labels to IDs
   - Split into train/test sets

3. **Tokenization**
   - Applied `AutoTokenizer` from FinBERT
   - Used HuggingFace `Dataset.map` for batch tokenization

4. **Model Setup & Training**
   - Used `AutoModelForSequenceClassification`
   - Configured `TrainingArguments`
   - Trained via HuggingFace `Trainer`

5. **Evaluation**
   - Calculated accuracy, precision, recall, F1-score
   - Achieved ~85% overall accuracy on test set
   - Visualized confusion matrix

6. **Saving and Export**
   - Saved fine-tuned model to `./my-finbert-finetuned`
   - Zipped model for download

### ✅ Results

- Precision (macro): **0.81**
- Recall (macro): **0.84**
- F1 Score (macro): **0.83**

---

## 📊 Project 2: Trading Signal Generator Using News Sentiment + Technical Indicators

### 🔍 Objective

Combine **news sentiment**, **MACD**, and **RSI** to generate actionable **BUY/SELL/HOLD** signals, and backtest the performance of these decisions on historical stock prices.

### 🔗 Components

1. **Load Fine-Tuned FinBERT Model**
   ```python
   finbert = pipeline("sentiment-analysis", model="./my-finbert-finetuned")
   ```

2. **Fetch News with NewsAPI**
   ```python
   newsapi = NewsApiClient(api_key="your_api_key")
   ```

3. **Sentiment Scoring**
   - Extract sentiment label and confidence score for each headline.

4. **Ticker Identification**
   - Map companies in headlines to ticker symbols using a custom dictionary.

5. **Technical Indicators**
   - **RSI**: Uses a 14-day rolling window
   - **MACD**: Difference of EMA(12) and EMA(26), with signal line

6. **Signal Aggregation Logic**
   ```python
   final_score = mean([sentiment_score, rsi_signal, macd_signal])
   ```

7. **Decision Mapping**
   - >0.33 = BUY  
   - <-0.33 = SELL  
   - else = HOLD

8. **Visualization**
   - Plots stock prices with signal overlays

9. **Backtesting Engine**
   - Simulates portfolio using signals
   - Calculates virtual PnL

### ✅ Results

- **Starting Capital**: `$100,000`
- **Final Portfolio Value**: `$125,968`
- **Profit**: `$25,968 (+25.97%)`
- **Final Holdings**: `452 shares`
- **Total Trades Executed**: `1`
- **Last Action**: `HOLD`

---

## 📂 Repository Structure

```bash
├── FinBERTFineTuning.ipynb        # Fine-tune FinBERT pipeline
├── FinalCode.ipynb                # Signal generation & backtesting
├── my-finbert-finetuned/          # Saved model directory
├── my-finbert-finetuned.zip       # Zipped model
├── all-data.csv                   # Sentiment dataset
├── README.md                      # Project overview (this file)
```

---

## 🚀 Future Work

- Integrate real-time stock execution via broker API
- Improve feature weighting with ML optimization
- Expand ticker list and news coverage
- Add support for multi-timeframe backtesting

---

## 🤖 Tech Stack

- Python, Pandas, NumPy
- HuggingFace Transformers & Datasets
- YFinance, NewsAPI
- Matplotlib, Scikit-learn

---
