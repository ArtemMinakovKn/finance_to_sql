# Finance Database with Python and SQL Server

This project builds a structured local database of financial asset prices using historical data from [Yahoo Finance](https://finance.yahoo.com/) — stored permanently in Microsoft SQL Server for high-performance use in analytics, modeling, and reporting.

The latest version supports **automated downloading of all S&P 500 constituents** and **direct insertion into SQL Server**, without overloading memory or relying on large intermediate files.

---

## 💡 Why This Project?

In finance, we often reuse the same market data across many tasks — but APIs can be slow, limited, or unreliable.  
This setup creates a **personal, reusable, local financial data warehouse**, starting with stocks from the S&P 500 index.  
The database is designed to grow over time — and serve as a fast, stable source for backtesting, research, dashboards, and production models.

---

## 🛠️ Tools Used

| Tool                             | Purpose                                 | Link |
|----------------------------------|-----------------------------------------|------|
| **Python**                       | Core language for automation            | [python.org](https://www.python.org/) |
| **Jupyter Notebook**             | Interactive development environment     | [jupyter.org](https://jupyter.org/) |
| **yfinance**                     | Historical price data                   | [yfinance GitHub](https://github.com/ranaroussi/yfinance) |
| **pandas**                       | Data manipulation                       | [pandas.pydata.org](https://pandas.pydata.org/) |
| **pyodbc**                       | Python ↔ SQL Server connectivity        | [pyodbc GitHub](https://github.com/mkleehammer/pyodbc) |
| **Microsoft SQL Server Express**| Local SQL database                      | [Download](https://www.microsoft.com/en-us/sql-server/sql-server-downloads) |
| **SQL Server Management Studio**| Database GUI                            | [Download SSMS](https://aka.ms/ssmsfullsetup) |
| **tqdm**                         | Progress bar for loops                  | [tqdm PyPI](https://pypi.org/project/tqdm/) |

---

## 📁 Project Structure

```
finance-to-sql/
├── finance_to_sql.ipynb        # Main notebook with all logic
├── utils_sql.py                # (Optional) Modularized DB helpers
├── requirements.txt            # Python dependencies
├── README.md                   # Project documentation
├── .gitignore                  # Files to exclude from Git
```

---

## 🚀 How to Use

1. Clone this repository and navigate to the folder.
2. (Optional) Create a virtual environment.
3. Install Python dependencies:

```bash
pip install -r requirements.txt
```

4. Install SQL Server Express and SSMS.
5. Create a database named `FinanceDB` in SQL Server.
6. Run the Jupyter notebook:

```bash
jupyter notebook finance_to_sql.ipynb
```

The notebook will:
- Connect to your SQL Server
- Create the `StockPrices` table (if missing)
- Download historical data for **all S&P 500 stocks**
- Insert each record directly into the database

---

## 🧪 Example Query Function

To query the database later for any stock and start date:

```python
df = load_stock_data("AAPL", "2010-01-01")
```

This fetches the data for Apple Inc. since 2010 directly from your SQL database.

---

## 📈 Next Features

- Schedule automatic daily updates
- Add deduplication & data validation
- Integrate Power BI or Tableau dashboards
- Add ETF, crypto, and macroeconomic series
- Deploy query interface as a local web app (e.g., Flask or Streamlit)
