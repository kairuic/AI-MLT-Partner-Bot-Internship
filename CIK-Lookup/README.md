# SEC EDGAR CIK Lookup

A Python module that retrieves company data from SEC EDGAR and allows fast lookup of a company's CIK number by name or stock ticker, and retrieves annual and quarterly filings.

## Setup

Install the required dependency:

```bash
pip install requests
```

## Usage

```python
from app import SecEdgar

se = SecEdgar("https://www.sec.gov/files/company_tickers.json")

# Lookup by ticker
se.ticker_to_cik("AAPL")  # → (320193, "AAPL", "Apple Inc.")

# Lookup by company name
se.name_to_cik("Apple Inc.")  # → (320193, "AAPL", "Apple Inc.")

# Get annual 10-K filing
se.annual_filing(cik, 2024)  # → (form, date, accession, document, url)

# Get quarterly 10-Q filing
se.quarterly_filing(cik, 2024, 2)  # → (form, date, accession, document, url)
```
