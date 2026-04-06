# Investment Banking Valuation Toolkit

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A comprehensive, production‑ready valuation toolkit that calculates the intrinsic value of any public company using five different methodologies, generates sensitivity tables and heatmaps, and produces a professional **football field chart** – exactly as used in investment banking pitch books.

---

## Overview

This project automates the entire valuation process for a given stock ticker. It fetches real‑time financial data from **Yahoo Finance** and **SEC EDGAR** (via `yfinance`), then performs:

- **Discounted Cash Flow (DCF) Analysis**
- **Comparable Company Analysis (Trading Comps)**
- **Precedent Transaction Analysis**
- **Leveraged Buyout (LBO) Analysis**
- **Sum‑of‑the‑Parts (SOTP) Analysis**

For each method, the toolkit produces a valuation range, and the results are consolidated into a **football field chart**. Full sensitivity analysis (2D tables and heatmaps) is provided for DCF and LBO models. All outputs are saved as Excel files and PNG images, ready to be included in reports or presentations.

---

## Key Features

- **Fully automated data collection** – no manual input beyond the ticker symbol.
- **Five valuation methodologies** – covers the core techniques used by investment banks.
- **Sensitivity analysis** – DCF sensitivity (WACC vs. terminal growth) and LBO sensitivity (purchase multiple vs. exit multiple) with heatmaps.
- **Trading Comps percentile valuations** – 25th, 50th, 75th percentiles of EV/Revenue, EV/EBITDA, and P/E.
- **Football field chart** – compares all valuation ranges with the current share price and the median of all midpoints.
- **Excel export** – all results, sensitivity tables, and percentile valuations are saved in a multi‑sheet Excel workbook.
- **Visualisations** – heatmaps and football field chart are saved as high‑resolution PNG files.

---

## Data Sources

| Source          | Data                                                          | Access                        |
|-----------------|---------------------------------------------------------------|-------------------------------|
| Yahoo Finance   | Stock price, financial statements (income, balance sheet, cash flow), market cap, shares outstanding, peer data | `yfinance` |
| Wikipedia       | S&P 500 constituents (for peer selection)                    | `requests` + `pandas`         |
| SEC EDGAR       | Financial facts (via Yahoo Finance) – no separate API required | `yfinance` |

All data is free, public, and updated daily.

---
## Example Output: General Electric (GE)

We ran the toolkit for GE Aerospace (ticker: GE) on April 2025. Below are the results.

Valuation Ranges
|Methodology	|Low ($)	|High ($)	|Midpoint ($) |
|-------------|---------|---------|-------------|
Comparable Company Analysis |	200.04	| 415.85	| 307.95|
Sum‑of‑the‑Parts (SOTP) |	99.97 |	149.95 |	124.96
Discounted Cash Flow (DCF) |	107.41 |	129.26 |	118.34
Precedent Transactions |	58.08 |	176.97 |	117.53
Leveraged Buyout (LBO) |	43.03 |	64.55 |	53.79

Current share price: $281.16

Median of all valuation midpoints: $118.34 (approx)
