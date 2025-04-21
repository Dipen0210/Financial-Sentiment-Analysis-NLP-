# 📈 FinBERT Sentiment-Based Trading Signal Generator & Fine-Tuning Pipeline

This repository contains two interconnected projects:
1. **Fine-tuning FinBERT on a financial news sentiment dataset**.
2. **Using the fine-tuned FinBERT model to generate trading signals** based on real-time news, technical indicators (RSI, MACD), and performing backtesting.

---

## 📌 Project 1: Fine-Tuning FinBERT for Financial Sentiment Analysis

### 🧠 Overview

This project fine-tunes the pre-trained [FinBERT model](https://huggingface.co/yiyanghkust/finbert-tone) on a labeled dataset of financial news headlines to enhance domain-specific sentiment analysis performance.

### ✅ Results

- Precision (macro): **0.81**
- Recall (macro): **0.84**
- F1 Score (macro): **0.83**

---

## 📊 Project 2: Trading Signal Generator Using News Sentiment + Technical Indicators

### 🔍 Objective

Combine **news sentiment**, **MACD**, and **RSI** to generate actionable **BUY/SELL/HOLD** signals, and backtest the performance of these decisions on historical stock prices.

### ✅ Results

- **Starting Capital**: `$100,000`
- **Final Portfolio Value**: `$125,968`
- **Profit**: `$25,968 (+25.97%)`
- **Final Holdings**: `452 shares`
- **Total Trades Executed**: `1`
- **Last Action**: `HOLD`

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
