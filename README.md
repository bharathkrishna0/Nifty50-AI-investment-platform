
# 📈 NIFTY-50 Investment Intelligence Platform
> Data-driven investment intelligence using 21 years of NSE India market data (2000–2021)

---

## 🏆 Key Results

| Module | Metric | Result |
|--------|--------|--------|
| Stock Predictor | LSTM R² Score | **0.9898** |
| Stock Predictor | LSTM MAE | **₹23.09** |
| Stock Predictor | Directional Accuracy | **51.86%** |
| Portfolio | Aggressive Annual Return | **29.57% p.a.** |
| Portfolio | ₹1L invested (2000–2021) | **₹2.70 Crore** |
| Portfolio | Best Sharpe Ratio | **0.979** |
| Risk | Conservative Max Drawdown | **-39.18%** |
| Risk | Aggressive Max Drawdown | **-66.95%** |

---

## 📁 Project Structure

```
nifty50-investment-intelligence/
├── notebooks/
│   ├── 01_data_loading.ipynb
│   ├── 02_eda.ipynb
│   ├── 03_stock_predictor.ipynb
│   └── 04_portfolio_risk.ipynb
├── src/
│   ├── app.py              ← Streamlit dashboard
│   └── requirements.txt
├── results/
│   ├── model_results.csv
│   ├── portfolio_weights.csv
│   ├── portfolio_risk_metrics.csv
│   └── stock_risk_metrics.csv
├── images/
│   ├── eda_overview.png
│   ├── model_comparison.png
│   ├── portfolios.png
│   ├── backtest.png
│   └── risk_dashboard.png
└── README.md
```

---

## 🚀 How to Run

### 1. Clone the repo
```bash
git clone https://github.com/YOUR_USERNAME/nifty50-investment-intelligence
cd nifty50-investment-intelligence
```

### 2. Install dependencies
```bash
pip install -r src/requirements.txt
```

### 3. Download dataset
Download both datasets from Kaggle and place CSVs in a `data/` folder:
- [NIFTY-50 Stock Market Data](https://www.kaggle.com/datasets/rohanrao/nifty50-stock-market-data)
- [India Stock Data NSE 1990–2020](https://www.kaggle.com/datasets/stoicstatic/india-stock-data-nse-1990-2020)

### 4. Run notebooks in order
```
01_data_loading.ipynb  → loads + cleans data
02_eda.ipynb           → exploratory analysis + charts
03_stock_predictor.ipynb → ARIMA + LSTM models
04_portfolio_risk.ipynb  → portfolio + risk modules
```

### 5. Launch dashboard
```bash
streamlit run src/app.py
```

---

## 📊 Modules

### 1. 📈 Stock Predictor Engine
Forecasts future stock prices using two models:

| Model | MAE | RMSE | R² | Dir. Acc |
|-------|-----|------|----|----------|
| ARIMA | 499.35 | 613.37 | -1.013 | 1.89% |
| **LSTM** | **23.09** | **43.71** | **0.9898** | **51.86%** |

LSTM uses 60-day sequences with a 2-layer architecture trained for 50 epochs.
ARIMA's negative R² confirms why deep learning is necessary for complex stock patterns.

### 2. 💼 Portfolio Construction
Three investor profiles built using mean-variance optimisation:

| Profile | Ann. Return | Volatility | Sharpe | ₹1L → |
|---------|------------|-----------|--------|--------|
| Conservative | 15.90% | 18.12% | 0.546 | ₹19.97L |
| Balanced | 28.54% | 23.43% | 0.962 | ₹2.25 Cr |
| **Aggressive** | **29.57%** | **24.07%** | **0.979** | **₹2.70 Cr** |

### 3. ⚠️ Risk Assessment
Comprehensive risk metrics per portfolio:

| Profile | Sharpe | Sortino | Max Drawdown | VaR 95% |
|---------|--------|---------|-------------|---------|
| Conservative | 0.546 | 0.664 | -39.18% | -1.647% |
| Balanced | 0.962 | 1.201 | -64.38% | -2.161% |
| Aggressive | 0.979 | 1.263 | -66.95% | -2.177% |

### 4. 🖥️ Interactive Dashboard
4-page Streamlit app with:
- Market overview + normalised price trends
- Stock explorer with MA, RSI indicators
- Portfolio builder with live optimisation
- Risk-return scatter map for all 50 stocks

---

## 🛠 Tech Stack

| Category | Tools |
|----------|-------|
| Data | pandas, numpy |
| ML / DL | PyTorch, scikit-learn, statsmodels |
| Optimisation | scipy |
| Visualisation | plotly, matplotlib, seaborn |
| Dashboard | Streamlit |
| Environment | Google Colab |

---

## 📄 Dataset
- **NIFTY-50 Stock Market Data** — Kaggle (rohanrao)
- **India Stock Data NSE 1990–2020** — Kaggle (stoicstatic)
- 470,434 records · 50 companies · 21 years (2000–2021)

---

## 👥 Team
Built as part of a data science competition on AI-powered investment intelligence.
