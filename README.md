# E-commerce-Use-case-Data-Analytics-Dashboard-
Interactive dashboard analyzing a year of beverage retail sales — net profit, growth trends, top/worst products, and salesperson performance. Built from raw Excel with Python (pandas) and Chart.js.
# Beverage Sales Performance Dashboard

An interactive single-page dashboard analyzing a full year (2023) of beverage
retail sales — 20,000 orders across 10 stores, 100 products, and 600+ customers.
Built from raw Excel source files, with all metrics computed from the data rather
than hardcoded.

## What it shows

- **Headline KPIs** — net profit, total revenue, total orders, units sold, returns
- **Growth trend** — revenue and net profit month by month, plus order volume
- **Profit by category** — which beverage categories drive the most margin
- **Best & worst products** — top 10 and bottom 10 by net profit
- **Salesperson performance** — units sold, sales value, and net profit per person

## Data model

A star schema with one fact table and three dimension tables:

- `fact_table` — one row per order (quantity, returns, payment, date, revenue, profit)
- `products_table` — product details, sales price, cost price
- `sales_persons_table` — salesperson and store info
- `monthly_store_targets` — monthly sales goals per store

## Tech

- **Python (pandas)** — data loading, cleaning, metric calculation
- **HTML / CSS / JavaScript + Chart.js** — the dashboard
- Self-contained single HTML file; opens in any browser, no server needed

## Data quality note

The per-store target metric was found to be unreliable: the fact table has no store
reference, so sales can't be attributed to individual stores without mapping each
sale through its salesperson. This is documented rather than hidden, and the metric
was excluded from the dashboard.

## How to run

Open `beverage_sales_dashboard.html` in any browser.
