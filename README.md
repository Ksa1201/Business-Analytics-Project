# Business-Analytics-Project
Business Analytics undergrad exploring data visualization, predictive modeling, and BI tools | Building projects in Python, SQL &amp; Power BI
# 📈 Stock Market Analytics Pipeline

A end-to-end data engineering and analytics project that ingests live stock market data, computes technical indicators, stores them in a lightweight data warehouse, and serves an interactive dashboard — all from a single Jupyter notebook.

---

## 🗂️ Project Overview

This pipeline automates the full journey from raw stock data to interactive visualization:

```
yfinance API → Data Ingestion → Feature Engineering → DuckDB Warehouse → Streamlit Dashboard
```

Stocks tracked: **AAPL · MSFT · GOOGL · TSLA · NKE**

---

## 🚀 Features

- **Live Data Ingestion** — Fetches 1 year of OHLCV data per ticker using `yfinance` and saves raw CSVs locally
- **Technical Indicator Engine** — Computes MA(20), MA(50), RSI(14), Daily Return, and 20-day Rolling Volatility
- **DuckDB Warehouse** — Stores the transformed dataset in an embedded analytical database (`warehouse.duckdb`)
- **Interactive Dashboard** — Streamlit app with candlestick charts, moving averages, RSI panel, and KPI metrics
- **Public Tunnel** — Exposes the dashboard via a Cloudflare tunnel for easy sharing with a public URL

---

## 🛠️ Tech Stack

| Layer | Tool |
|---|---|
| Data Ingestion | `yfinance` |
| Data Transformation | `pandas` |
| Data Warehouse | `DuckDB` |
| Dashboard | `Streamlit` + `Plotly` |
| Tunneling | `cloudflared` |

---

## 📦 Installation

```bash
pip install yfinance duckdb streamlit plotly pyngrok
```

---

## ▶️ How to Run

1. **Open the notebook** `Stock_Market_Pipeline.ipynb` in Jupyter or Google Colab
2. **Run all cells in order:**
   - Cell 1 — Fetches stock data and saves raw CSVs to `data/raw/`
   - Cell 2 — Computes technical indicators and creates a combined dataframe
   - Cell 3–5 — Loads transformed data into DuckDB and verifies the schema
   - Cell 6 — Writes the Streamlit dashboard app to `dashboard_app.py`
   - Cell 7 — Starts the Streamlit server and creates a public Cloudflare tunnel URL

3. **Open the printed tunnel URL** to view the live dashboard in your browser

---

## 📊 Dashboard Features

- **Ticker Selector** — Switch between stocks from the sidebar
- **KPI Cards** — Latest Close Price, RSI, Volatility, and Daily Return
- **Candlestick Chart** — OHLC price chart overlaid with MA(20) and MA(50)
- **RSI Panel** — RSI(14) chart with overbought (70) and oversold (30) threshold lines

---

## 📁 Project Structure

```
├── Stock_Market_Pipeline.ipynb   # Main pipeline notebook
├── dashboard_app.py              # Auto-generated Streamlit app
├── data/
│   ├── raw/                      # Raw CSV files per ticker
│   └── warehouse.duckdb          # DuckDB analytical database
```

---

## 📐 Technical Indicators Computed

| Indicator | Description |
|---|---|
| MA_20 | 20-day Simple Moving Average |
| MA_50 | 50-day Simple Moving Average |
| Daily_Return | Percentage change in closing price |
| RSI_14 | 14-period Relative Strength Index |
| Volatility_20 | 20-day rolling standard deviation of returns |

---

## 🙋 Author

Built as part of a Business Analytics portfolio project to demonstrate skills in data engineering, financial analytics, and dashboard development.
