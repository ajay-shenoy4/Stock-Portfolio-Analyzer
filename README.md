# Stock Portfolio Analyzer

A **comprehensive stock portfolio analysis tool** built in Python using **Yahoo Finance data**. This Jupyter notebook / Google Colab script takes your personal portfolio CSV file, enriches it with live market data, and produces **technical indicators, sector-level insights, performance benchmarks, and visualizations**.

Designed for **exploratory financial analysis**, portfolio monitoring, and learning applied data science / quantitative finance concepts.

---

## Quick Start Guide

### Step 1: Prepare Your Portfolio Data

Create a Google Sheet with **three columns**:

| Stock ETF | Cost/share | No. of shares |
|-----------|------------|---------------|
| AAPL      | $150.00    | 10            |
| MSFT      | $300.00    | 5             |
| GOOGL     | $2,500.00  | 2             |

**Example template:** [Sample Portfolio Sheet](https://docs.google.com/spreadsheets/d/1-RrW_DXd5mk-NPZcxgseHaA3RhyzIqlmhKvm3jApSsw/edit?usp=sharing)

### Step 2: Download as CSV

File → Download → Comma Separated Values (.csv)

### Step 3: Run in Google Colab

**[How to Use in Colab - Full Guide](https://docs.google.com/document/d/191mVnC4fQr_Pw6K8DV9PRpFXwqgsYPziaxDY8QDb_GE/edit?usp=sharing)**

1. Open the notebook in Google Colab
2. Go to **Runtime** → **Run all**
3. Under the third code cell, click **Choose Files** and upload your CSV
4. Follow interactive prompts:
   - *Would you like a graph of the price history of a stock? (yes/no):*
   - Enter stock tickers when prompted
   - Select date ranges for analysis

---

## Tech Stack

- **Python 3**
- **pandas** – data manipulation
- **numpy** – numerical computations
- **yfinance** – stock market data from Yahoo Finance
- **matplotlib** – visualization

---

## Features Overview

### **Portfolio Data Cleaning**
- Automatically removes invalid rows and footer content
- Strips `$` signs and commas from currency values
- Converts data to proper numeric formats
- Handles missing or malformed entries gracefully

### **Live Market Data Enrichment**
For each stock in your portfolio, the analyzer pulls **year-to-date data** and computes:

- Current price & previous close
- Daily price change ($ and %)
- 50-day and 100-day moving averages
- 100-day min/max range
- 1-month percent change
- Forward P/E ratio
- PEG ratio
- Dividend yield
- Sector classification

**Portfolio Metrics:**
```
Overall Stock Gain = (Current Price − Cost Per Share) × Number of Shares
```

All results exported to **`stock_data.csv`**

### **Trend Classification (Technical Analysis)**
Stocks are automatically categorized based on moving average relationships:

- Below 50-day MA
- Below both 50-day & 100-day MA (downtrend)
- Above 50-day MA
- Above both 50-day & 100-day MA (strong uptrend)

Provides a quick technical health check for your entire portfolio.

### **Sector-Level Aggregation & Visualization**
#### Sector Price Movement (1 Month)
- Aggregates daily closing prices across all owned stocks by sector
- Generates time-series plots per sector
- Identifies **which sectors drive portfolio volatility**

### **Monthly Sector Performance Table**
- Computes 1-month percent return per stock
- Aggregates performance by sector
- Flags sectors with **> ±10% monthly movement**

Shows relative sector strength or weakness at a glance.

### **Interactive Stock Price Plotter**
User-driven analysis tool:
- Enter any stock ticker
- Choose **Year-to-Date** or **custom start date**
- View historical price chart with volume

Perfect for deep dives into individual holdings.

### **Multi-Timeframe Sector Performance**
Calculates sector performance across:
- 1 Month
- 6 Months
- 1 Year
- Year-to-Date

Visualized with bar charts to identify:
- Short-term momentum
- Long-term trend consistency
- Sector rotation patterns

### **Portfolio vs Sector ETF Benchmarking**
Compares your portfolio performance against **sector ETFs**:

| Sector                 | Benchmark ETF |
|------------------------|---------------|
| Technology             | XLK           |
| Communication Services | XLC           |
| Financials             | XLF           |
| Energy                 | XLE           |
| Materials              | XLB           |
| Healthcare             | XLV           |
| Industrials            | XLI           |
| Consumer Discretionary | XLY           |
| Consumer Staples       | XLP           |
| Utilities              | XLU           |
| Real Estate            | XLRE          |

For each sector:
- Daily percent change of your holdings is averaged
- Compared against corresponding sector ETF
- Plotted for direct visual comparison

**Answers the question:** *Is my portfolio outperforming the broader sector?*

### **Individual Stock vs Sector Benchmark**
Select a **single stock** and compare its daily returns directly against its sector ETF.

Helps isolate **alpha vs beta** behavior for individual holdings.

---

## Outputs

### Files Generated:
- **`stock_data.csv`** – Complete analytics table with all metrics

### Visualizations:
- Sector trend line charts
- Stock vs sector comparison plots
- Multi-period performance bar charts
- Individual stock price histories

---
