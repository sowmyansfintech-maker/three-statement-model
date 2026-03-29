# 📑 3-Statement Financial Forecasting Model

![Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=flat&logo=microsoft-excel&logoColor=white)
![Finance](https://img.shields.io/badge/Domain-Investment_Banking-0a66c2?style=flat)
![License](https://img.shields.io/badge/License-MIT-green?style=flat)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=flat)

> A fully integrated Income Statement → Balance Sheet → Cash Flow Statement model built to Wall Street standards — the foundational tool behind every M&A deal, buyout, and valuation on Wall Street.

---

## 📌 Overview

This model reconstructs **3–4 years of historical financials** for a real public company and projects them forward — wiring all three statements together so that every assumption flows automatically through the entire model.

This is the **core deliverable** required in Investment Banking, Private Equity, and Corporate Finance recruiting.

---

## 🗂️ Project Structure

```
three-statement-model/
│
├── model/
│   └── three_statement_model.xlsx      # The full Excel model
│
├── docs/
│   ├── assumptions.md                  # Key forecast drivers & rationale
│   └── methodology.md                  # Step-by-step build notes
│
├── data/
│   └── source_financials.pdf           # Raw 10-K / annual report data
│
├── screenshots/
│   ├── income_statement.png
│   ├── balance_sheet.png
│   └── cash_flow.png
│
├── .gitignore
├── LICENSE
└── README.md
```

---

## 🔬 Model Architecture

### The Three Statements — Fully Integrated

```
Income Statement
      │
      ▼
  Net Income ──────────────────────────┐
      │                                 │
      ▼                                 ▼
Cash Flow Statement              Balance Sheet
  Operating CF ───────► Cash ──► Assets / Equity
  Investing CF
  Financing CF
```

Every number connects. Change one revenue assumption — every statement updates automatically.

---

### Statement 1 — Income Statement
| Line Item             | Method                              |
|-----------------------|-------------------------------------|
| Revenue               | YoY growth % assumption             |
| COGS                  | Gross margin % of revenue           |
| Gross Profit          | Revenue − COGS                      |
| Operating Expenses    | % of revenue or fixed growth        |
| EBITDA                | Calculated                          |
| D&A                   | % of PP&E (Balance Sheet linked)    |
| EBIT                  | EBITDA − D&A                        |
| Interest Expense      | Linked to Debt Schedule             |
| EBT                   | EBIT − Interest                     |
| Net Income            | EBT × (1 − Tax Rate)               |

### Statement 2 — Balance Sheet
- Assets: Cash (plug), Receivables (Days Sales Outstanding), Inventory (Days Inventory Outstanding), PP&E (CapEx − D&A roll)
- Liabilities: Payables (Days Payable Outstanding), Debt (Debt Schedule linked)
- Equity: Retained Earnings roll (Prior + Net Income − Dividends)

### Statement 3 — Cash Flow Statement
Built using the **indirect method**:
```
Net Income
+ D&A (non-cash add-back)
± Changes in Working Capital
= Operating Cash Flow

− CapEx
= Free Cash Flow (FCF)
```

---

## 📐 Wall Street Formatting Conventions

This model follows industry-standard formatting exactly:

| Convention     | Rule                                                  |
|----------------|-------------------------------------------------------|
| 🔵 Blue font   | Hard-coded inputs typed manually (historical data)    |
| ⚫ Black font  | Formula-driven outputs (calculated cells)             |
| Header rows    | Bold, dark background, white text                     |
| Negatives      | Shown in parentheses `(1,234)` not with minus signs   |
| Units          | Stated clearly — `$ in millions` in header            |
| Tab structure  | Cover → IS → BS → CF → Working Capital → DCF         |

> ⚠️ Recruiters will open your Excel file and judge the formatting before reading a single number.

---

## 📊 Key Forecast Assumptions

| Driver               | Assumption          | Rationale                          |
|----------------------|---------------------|------------------------------------|
| Revenue Growth       | X% YoY             | Based on analyst consensus + trend |
| Gross Margin         | X%                  | 3-year historical average          |
| D&A                  | X% of PP&E          | Company guidance                   |
| CapEx                | X% of Revenue       | Historical capex intensity         |
| DSO                  | X days              | Historical working capital cycle   |
| Tax Rate             | X%                  | Effective rate from 10-K           |

*(Full assumption rationale in `docs/assumptions.md`)*

---

## 🚀 How to Use

1. **Download** `model/three_statement_model.xlsx`
2. **Enable macros** if prompted
3. **Navigate tabs** — Cover → Income Statement → Balance Sheet → Cash Flow
4. **Change assumptions** in the blue cells only — all outputs recalculate automatically
5. **Check the balance sheet** — Assets must equal Liabilities + Equity at all times

---

## 🧰 Tools Used

| Tool           | Purpose                            |
|----------------|------------------------------------|
| Microsoft Excel | Full model build                  |
| Yahoo Finance  | Historical financial data          |
| SEC EDGAR      | 10-K annual report source          |

---

## 📄 License

MIT — see [LICENSE](LICENSE)
