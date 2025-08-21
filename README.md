# Sentiment-Infused Trade Modeling (SITM)

**A machine learning framework that combines market sentiment with trading data to model profitability, uncover market regimes, and enhance trade decision-making.**

---

## Introduction
Sentiment-Infused Trade Modeling (SITM) is an end-to-end data science pipeline that integrates market sentiment indices (e.g., Fear & Greed Index) with historical trade data to predict profitable opportunities.  
The project combines robust data engineering, exploratory analysis, and advanced ML modeling to extract actionable insights and validate strategies through backtesting.

---

## Pipeline Workflow
- **Data Ingestion & Validation**  
  - Load 200K+ raw trades and sentiment data.  
  - Handle missing values, duplicates, and outliers.  
  - Clean timestamps, derive notional values, and create daily aggregates.  

- **Exploratory Data Analysis (EDA)**  
  - Assess data quality and missingness over time.  
  - Visualize sentiment-driven PnL and leverage dynamics.  
  - Generate automated PDF reports with charts and tables for stakeholders.  

- **Feature Engineering & Modeling**  
  - Create lagged and rolling features to capture temporal dependencies.  
  - Segment traders and market states via clustering and Hidden Markov Models.  
  - Train a LightGBM classifier to predict profitable trades.  
  - Evaluate performance with time-based splits to avoid leakage.  

- **Backtesting & Validation**  
  - Apply probability thresholds for trade selection.  
  - Demonstrated approximately 59% uplift in PnL versus baseline.  
  - Achieved greater than 99% win rate for high-confidence trades.  

---

## Key Results
- Sentiment regimes:  
  - Greed → higher leverage, higher cumulative PnL.  
  - Fear → safer but less profitable trades.  

- Trader clustering:  
  - Four clusters identified with distinct leverage and PnL behavior.  

- Predictive modeling:  
  - LightGBM classifier provided strong predictive performance.  
  - Feature importance highlighted key drivers of profitability.  

- Backtesting:  
  - Real-world validation confirmed significant profitability improvements.  

---

## Repository Structure
- **Notebooks**  
  - `DataIngestion&Validation.ipynb` – Data preparation and validation.  
  - `ExploratoryDataAnalysis&Analytics.ipynb` – Exploratory analysis and automated reports.  
  - `FeatureEngineering&MODELS4.ipynb` – Feature creation, clustering, ML modeling, and backtesting.  

- **Outputs**  
  - Cleaned datasets (`trades_cleaned.csv`, `daily_aggregates.csv`).  
  - Clusters and regimes (`trader_clusters.csv`, `sentiment_regimes.csv`).  
  - Model outputs (`lightgbm_feature_importances.csv`, `backtest_results.csv`).  
  - Visualizations (PNG, HTML) and automated PDF report.  

---

## Tech Stack
- Python: Pandas, NumPy, SciPy, Scikit-learn, LightGBM.  
- Visualization: Matplotlib, Seaborn, Plotly.  
- Modeling: Clustering, Hidden Markov Models, Gradient Boosting.  
- Reporting: ReportLab (automated PDFs).  
- Environment: Google Colab + Drive integration.  

---

## Future Enhancements
- Incorporate external data (volatility indices, macroeconomic signals).  
- Explore ensemble models (LightGBM + XGBoost + Random Forest).  
- Extend to real-time deployment for trading decision support.  

---

## License
MIT License – free to use and adapt with attribution.

---

## Repository Tagline
**A sentiment-driven ML pipeline for smarter trade modeling and profitability insights.**
