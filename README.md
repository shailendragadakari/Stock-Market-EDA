# 📈 S&P 500 Stock Market — Exploratory Data Analysis

![Python](https://img.shields.io/badge/Python-3.x-blue) ![SQLite](https://img.shields.io/badge/Database-SQLite-lightgrey) ![Jupyter](https://img.shields.io/badge/Notebook-Jupyter-orange) ![Libraries](https://img.shields.io/badge/Libraries-Pandas%20%7C%20Matplotlib%20%7C%20Seaborn-green)

---

## 📌 Project Overview

This project performs an end-to-end exploratory data analysis on historical S&P 500 stock price data spanning **2013 to 2018**. Using SQL queries executed via Python's built-in SQLite connector inside a Jupyter Notebook, the analysis investigates price trends, market volatility, single-day extremes, trading volume behaviour, and stock consistency across 500 companies.

The project demonstrates a complete data analyst workflow — from raw data ingestion and SQL-based exploration to insight derivation and data visualisation — entirely within a Python and Jupyter environment.

---

## 📂 Repository Structure

```stock-market-eda/
├── stock_market_eda.ipynb        # Main analysis notebook
├── .gitignore                    # Excludes data files and database
└── README.md
```

---

## 📊 Dataset

| Property | Details |
|----------|---------|
| Source | [Kaggle — S&P 500 Stock Data](https://www.kaggle.com/datasets/camnugent/sandp500) |
| Records | 619,040 rows |
| Companies | 505 stocks |
| Period | February 2013 — February 2018 |
| Columns | `date`, `open`, `high`, `low`, `close`, `volume`, `name` |

> **Note:** The raw CSV file is not included in this repository due to size. Download it directly from the Kaggle link above and place it in the `data/` folder before running the notebook.

---

## 🛠️ Tools & Technologies

- **Language:** Python 3.14.2
- **Environment:** Jupyter Notebook in VS Code
- **Database:** SQLite (via Python's built-in `sqlite3` module)
- **Libraries:** `pandas`, `matplotlib`, `seaborn`

---

## 🔍 Analysis Structure

The notebook is organised into the following sections:

| Section | Description |
|---------|-------------|
| 1. Data Loading | Imports CSV into SQLite database using Pandas |
| 2. Libraries & Connection | Establishes SQLite connection and configures plot styling |
| 3. Data Profiling | Validates row counts, company count, and date range |
| 4. Top 15 Stocks by Average Closing Price | Identifies highest nominally valued stocks over the period |
| 5. Market Volatility by Year | Measures avg daily price range per year as a volatility proxy |
| 6. Top 10 Single-Day Gains | Finds the largest single-day percentage price gains |
| 7. Volume: Up vs Down Days | Compares avg trading volume across up, down, and flat days |
| 8. Most Consistent Stocks | Uses a CTE and stability ratio to rank price consistency |
| 9. APTV Price Trend | Time-series visualisation of the most consistent stock |
| 10. Most Traded Stocks | Ranks stocks by average daily trading volume |
| 11. Top 10 Single-Day Losses | Finds the largest single-day percentage price losses |
| 12. Summary & Conclusions | Consolidated findings across all analysis sections |

---

## 💡 Key Findings

| # | Question | Finding |
|---|----------|---------|
| 1 | Highest avg closing price | PCLN (Priceline) recorded the highest avg closing price at $1,312.87, reflecting its position as one of the highest nominally valued stocks in the S&P 500 over 2013–2018 |
| 2 | Most volatile year | 2018 was the most volatile year with an avg daily price range of $2.44, likely driven by the Q4 2018 market correction triggered by interest rate hikes and trade war fears |
| 3 | Biggest single-day gain | CHD (Church & Dwight Co.) recorded the largest single-day gain at 80.58%, a highly anomalous move likely tied to a specific corporate event or data irregularity worth investigating |
| 4 | Volume trend | Flat days recorded the highest avg trading volume (5,146,096), ahead of down days (4,403,383) and up days (4,233,354), suggesting peak activity occurs during periods of market indecision where buyers and sellers are evenly matched |
| 5 | Most consistent stock | APTV (Aptiv PLC) had the highest stability ratio of 6.90, with an avg closing price of $89.49 across a price range of only $12.97, indicating remarkably steady valuation over the five-year period |
| 6 | APTV price trend | APTV traded in a tight $83–$89 band through late 2017 before staging a steady climb through January 2018, peaking at $96.02 on February 1, 2018 — consistent with its profile as a stable, gradually appreciating stock |
| 7 | Most traded stock | BAC (Bank of America) was the most actively traded stock with an avg daily volume of 93,633,800 shares — nearly 1.7x that of second-placed AAPL (54,047,900) — reflecting high retail and institutional participation driven by its low nominal share price |
| 8 | Biggest single-day loss | LNT (Alliant Energy) recorded the largest single-day loss at -49.22% on May 19, 2016, followed by WMB (-25.25%) and CHK (-20.31%), both on February 8, 2016 — notably, CHK and WMB appearing in both the most traded and biggest loss lists suggests the energy sector experienced severe stress during this period |

> **Data Quality Note:** The extreme single-day movements recorded for CHD (+80.58%) and LNT (-49.22%) are statistical outliers that warrant further investigation. Such anomalies may reflect genuine market events, corporate actions such as spin-offs or special dividends, or potential data irregularities in the source dataset. Identifying and flagging these outliers is a standard step in any rigorous data analysis workflow.

---

## ▶️ How to Run

1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/stock-market-eda.git
   cd stock-market-eda
   ```

2. Install the required Python libraries:
   ```bash
   pip install pandas matplotlib seaborn
   ```

3. Download the dataset from [Kaggle](https://www.kaggle.com/datasets/camnugent/sandp500) and place `all_stocks_5yr.csv` inside the `data/` folder.

4. Open `stock_market_eda.ipynb` in VS Code or Jupyter and run **Cell 1** once to load the data into SQLite.

5. From the next session onwards, skip Cell 1 and start from Cell 2 to reconnect to the existing database.

---

## 👤 Author

**Shailendra Gadakari**  
B.E. Computer Science — BITS Pilani Dubai  
IBM Data Science Professional Certificate — Coursera
Microsoft Power BI Data Analyst Professional Certificate — Coursera

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue)](https://www.linkedin.com/in/shailendra-gadakari-b0a465332/)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-lightgrey)](https://github.com/shailendragadakari)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
