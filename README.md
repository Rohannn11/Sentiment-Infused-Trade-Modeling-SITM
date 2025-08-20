# 📈 Sentiment-Driven Trading Data Science

## 📖 Project Overview
This repository contains a **complete data science workflow** for sentiment-driven trading analytics.  
It processes raw trade and market sentiment data, performs exploratory analysis, engineers predictive features, applies clustering, and trains machine learning models to predict profitable trades.

The approach focuses on uncovering how **market sentiment regimes** influence profitability, leverage, and trade behavior.

---

## 🧠 Objectives
- ✅ Create a validated, sentiment-integrated dataset from raw trading and sentiment data.
- 📊 Explore relationships between sentiment regimes, PnL, leverage, and win rates.
- 🛠️ Engineer temporal and volatility-adjusted features for predictive modeling.
- 📍 Apply clustering to segment traders and market conditions.
- 📉 Train, evaluate, and backtest models for profitability prediction.

---

## 🔍 Key Steps

### 1️⃣ Data Ingestion & Validation
**Loaded datasets:**
- `historical_data.csv` → 211,224 trades
- `fear_greed_index.csv` → 2,644 daily sentiment values

**Performed:**
- Duplicate checks
- Missing value analysis
- Outlier detection via IQR

**Derived:**
- Notional value = `size × price`
- UTC & IST timestamps

**Produced:**
- `trades_cleaned.csv` (validated trades)  
- `daily_aggregates.csv` (summarized daily metrics)


### 2️⃣ Exploratory Data Analysis
- **Missingness** by column and over time  
- **Sentiment distribution:**  
  - Fear: 61,837 trades  
  - Greed: 50,303 trades  

- **Relationships found:**  
  - Greed → higher leverage & cumulative PnL  
  - Fear → lower returns but potentially safer trades  

- **Visualizations:**
  - Cumulative PnL by sentiment regime
  - Sentiment–symbol sensitivity


### 3️⃣ Feature Engineering
- **Temporal Features:**
  - Lagged metrics (1, 3, 7 days)
  - Rolling mean & standard deviation (3, 7, 14 days)
- **Derived Metrics:**
  - Volatility-adjusted PnL
  - Win streaks
- **Categorical Encoding:**  
  - Trade side  
  - Coin symbol

### 4️⃣ Clustering & Regime Analysis
- Trader clustering from daily aggregates
- Sentiment regime detection
- Market regimes via **Hidden Markov Models (HMM)**
- Regime transition statistics


### 5️⃣ Modeling & Backtesting
- **Model:** LightGBM classifier for binary profitability prediction
- **Train/Test Split:** Time-based (80/20) to avoid leakage
- **Backtest Strategy:** Only select trades with predicted probability ≥ 0.75
- **Result:** **+59% PnL uplift** vs baseline


## 📊 Key Results
- **Cleaned Data:** 211k+ trades with standardized formats and sentiment integration
- **Sentiment Impact:** Market regimes significantly affect leverage, volatility, and profitability
- **Model Outcome:**  
  - Baseline PnL: `1,007,553.65`  
  - Model-selected trades PnL: `1,603,733.55`
- **Artifacts:** 50+ CSVs, 20+ plots, interactive charts

## 🚀 Getting Started

### Prerequisites
- Python **3.9+**


### Running the Notebooks
1. `DataIngestion&Validation.ipynb` → Prepare and clean datasets  
2. `ExploratoryDataAnalysis&Analytics.ipynb` → Explore sentiment patterns and relationships  
3. `FeatureEngineering&MODELS4.ipynb` → Engineer features, train models, and backtest  

---

## 📜 License
This project is licensed under the **MIT License** – see the `LICENSE` file for details.

---

## 🙌 Acknowledgments
- **Sentiment Data** → Fear & Greed Index  
- **Libraries** → Pandas, NumPy, SciPy, LightGBM, Matplotlib, Plotly



├── ds_report.pdf
├── README.md
└── LICENSE
