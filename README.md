# Finance Database with Python and SQL Server

This project aims to build a structured local database of financial assets (e.g., stocks, indices) using historical data from [Yahoo Finance](https://finance.yahoo.com/).

Instead of fetching data through the API every time, we store it once in a local Microsoft SQL Server database — making it faster, more stable, and ready for daily use in analytics, modeling, and reporting workflows.

## 💡 Why this project?

In finance-related work, we often reuse the same market data repeatedly — but APIs can be slow, unreliable, or rate-limited.  
With this setup, we create a **personal financial time series database**, starting with the S&P 500 index and planning to extend it with equities, ETFs, cryptocurrencies, and macroeconomic indicators.

This database will grow over time and become a reusable, local "data lake" for financial projects.

## 🛠️ Tools Used

| Tool                             | Purpose                                 | Link |
|----------------------------------|-----------------------------------------|------|
| **Python**                       | Core language for data handling         | [python.org](https://www.python.org/) |
| **Jupyter Notebook**             | Interactive development environment     | [jupyter.org](https://jupyter.org/) |
| **yfinance**                     | Download market data from Yahoo Finance | [yfinance on GitHub](https://github.com/ranaroussi/yfinance) |
| **pandas**                       | Data manipulation and time series       | [pandas.pydata.org](https://pandas.pydata.org/) |
| **pyodbc**                       | Python to MS SQL Server connection      | [pyodbc GitHub](https://github.com/mkleehammer/pyodbc) |
| **Microsoft SQL Server Express**| Local database server                   | [Download](https://www.microsoft.com/en-us/sql-server/sql-server-downloads) |
| **SQL Server Management Studio**| SQL GUI for database management         | [Download SSMS](https://aka.ms/ssmsfullsetup) |

## 📁 Project Structure

```
finance-to-sql/
├── finance_to_sql.ipynb       # Main notebook with all logic
├── requirements.txt           # Python dependencies
├── README.md                  # This file
├── .gitignore                 # Files to exclude from Git
```

## 🚀 How to Use

1. Clone the repository and navigate to the project folder.
2. Create a virtual environment (optional but recommended).
3. Install dependencies:

```bash
pip install -r requirements.txt
```

4. Install Microsoft SQL Server Express and SSMS.
5. Create a database named `FinanceDB`.
6. Run the notebook:

```bash
jupyter notebook finance_to_sql.ipynb
```

7. The notebook will:
   - Download market data using `yfinance`
   - Create a SQL table if it doesn't exist
   - Save the data into the database for future use

## 📈 Next Features

- Load multiple tickers dynamically
- Schedule automatic updates (e.g., daily)
- Add data validation / deduplication logic
- Integrate with Power BI or other tools
- Include macro & fundamentals alongside prices