# Financial Sentiment Classification using FinBERT & Traditional ML Models

This project focuses on building a robust **financial news sentiment analysis system** by combining **traditional machine learning models** with a fine-tuned transformer model (**FinBERT**). It classifies financial headlines and articles into `positive`, `neutral`, or `negative` sentiments and compares multiple modeling approaches on both performance and interpretability.

### 🔍 Key Highlights

- ✅ **Fine-tuned FinBERT** on a labeled financial sentiment dataset using Hugging Face Transformers
- ✅ Evaluated and compared with:
  - Logistic Regression
  - Naive Bayes
  - SVM
  - Random Forest
- ✅ Achieved **84.2% accuracy** with FinBERT on real financial news data
- ✅ Visualized:
  - Learning curves (loss vs. epoch)
  - Model comparison (train/test accuracy)
  - Sentiment distribution across sources (Reddit, Alpha Vantage, Yahoo Finance)
- ✅ Integrated live data from:
  - 📈 [Alpha Vantage](https://www.alphavantage.co/) News API
  - 💬 Reddit (r/stocks)
  - 📰 Yahoo Finance RSS feeds
- ✅ Built a sentiment dashboard using **Streamlit**
- ✅ Integrated **hyperparameter tuning** with Optuna to boost model performance

### 🧠 Technologies Used

- Python, Pandas, Scikit-learn, Matplotlib, Seaborn
- Transformers (Hugging Face), FinBERT, Optuna
- APIs: Alpha Vantage, Reddit (PRAW), Yahoo Finance RSS
- Deployment: Streamlit for interactive dashboards

### 📦 Use Cases

- Portfolio risk analysis from sentiment
- Real-time news classification and alerting
- Input for trading signals and NLP-based financial dashboards

> ⚡ This project demonstrates real-world NLP applications in finance and highlights the effectiveness of domain-specific transformers like FinBERT.

