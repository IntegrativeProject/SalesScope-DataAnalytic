# Sales Scope

A collection of utilities for exploratory data analysis and data cleaning on a sales dataset connected to a PostgreSQL database.

## Project Overview

This repository contains scripts to perform: data cleaning (outlier detection, date validation, integrity checks), data quality checks (null analysis per table), and exploratory data analysis (metrics and charts). Outputs are saved in the `reports/` directory.

## Main Components

- `src/data_cleaning.py` – Detects outliers using IQR, validates dates, and checks referential integrity between `orders`, `order_items`, and `products`. Produces `reports/data_cleaning_report.txt`.
- `src/data_quality_check.py` – Checks for null values and row counts for tables (`users`, `products`, `orders`, `order_items`). Produces `reports/data_quality_report.txt`.
- `src/eda_analysis.py` – Prepares the dataset, computes metrics (e.g. average ticket), and creates charts (`reports/sales_by_hour.png`, `reports/top_5_products.png`) and `reports/eda_metrics.csv`.
- `src/db_connection.py` – Manages database connections using `DATABASE_URL` from a `.env` file.
- `src/test_connection.py` – Simple script to validate database connectivity.

## Requirements

Dependencies are listed in `requirements.txt`. Key packages:

- python-dotenv
- psycopg2-binary
- sqlalchemy
- pandas
- numpy

Quick setup (use a virtual environment):

```bash
python -m venv .venv
.venv\Scripts\activate    # Windows
pip install -r requirements.txt
```

## Configuration

Create a `.env` file in the project root with the `DATABASE_URL` environment variable pointing to your PostgreSQL database, for example:

```
DATABASE_URL=postgresql+psycopg2://user:password@host:port/database_name
```

Note: the project normalizes common SQLAlchemy-style URLs (those containing `+psycopg2`) to a `postgresql://` form when using `psycopg2` directly. Using either `postgresql+psycopg2://...` (for SQLAlchemy) or `postgresql://...` (for psycopg2) is supported.

Ensure the database contains the tables expected by the scripts: `users`, `products`, `orders`, `order_items`, `roles`.

## Usage

- Test DB connection:

```bash
python src/test_connection.py
```

- Run data cleaning report:

```bash
python src/data_cleaning.py
# Output: reports/data_cleaning_report.txt
```

- Run data quality checks:

```bash
python src/data_quality_check.py
# Output: reports/data_quality_report.txt
```

- Run EDA (metrics and charts):

```bash
python src/eda_analysis.py
# Outputs: reports/eda_metrics.csv, reports/sales_by_hour.png, reports/top_5_products.png
```

## Project Structure

- `requirements.txt` — project dependencies
- `reports/` — generated reports (txt, csv, png)
- `src/` — source scripts

## Notes and Best Practices

- Verify that `DATABASE_URL` has read permissions for the required tables before running scripts.
- Scripts assume table and column names like `order_id`, `product_id`, `user_id`, `created_at`, `price`, `quantity`, `total_price`, `total_amount`.
- Adjust SQL queries in the scripts if your schema differs.

## Contributions

Contributions are welcome. Suggested improvements:

- Add automated tests (pytest)
- Support for other SQL backends
- Add logging and CLI options

## License

No license specified — contact the project owner for clarification.
