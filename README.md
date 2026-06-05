# 🛒 Customer Purchase Pattern Analyzer

An end-to-end **retail / e-commerce analytics** project that turns raw customer
transaction data into business insight using an **interactive Excel dashboard**
(PivotTables, PivotCharts, Slicers & a Timeline). It analyses customer buying
behaviour, spending trends and loyalty to help a business improve **customer
retention and sales strategy**.

![Dashboard Preview](images/dashboard_preview.png)

---

## 🎯 Objective
Analyse customer buying behaviour, purchase frequency and spending trends from
transactional data to identify **high-value customers, popular products,
top-performing regions and retention opportunities** — the everyday work of a
Data / Business / Marketing Analyst in retail and e-commerce.

## 🧰 Tools Used
**Microsoft Excel** only — Tables, formulas (`SUMIFS`, `COUNTIF`, `SUMPRODUCT`,
`TEXT`, `IF`), PivotTables, PivotCharts, Slicers, Timeline and Conditional
Formatting. *(The dataset and workbook are generated reproducibly with Python
scripts in [`scripts/`](scripts/), but the analysis itself is 100% Excel.)*

---

## 📦 Dataset Description
`data/customer_purchases.csv` — **200 transactions** across **46 customers**,
spanning Jan–Dec 2024. 20 business columns:

| Column | Description |
|---|---|
| Customer ID / Name | Unique customer identifier and name |
| Age / Gender / City / Region / Occupation | Customer demographics |
| Product Category / Product Name | What was bought |
| Purchase Date | Transaction date (2024) |
| Quantity Purchased / Unit Price / Total Purchase Value | Order economics |
| Payment Method / Purchase Channel | UPI, Card, COD… / Website, App, In-Store |
| Customer Segment | Premium / Regular / Budget (by spend) |
| Loyalty Status | Gold / Silver / Bronze (by frequency) |
| Discount Used / Purchase Frequency / Last Purchase Date | Behaviour features |

A second file, `data/customer_purchases_raw.csv`, intentionally contains
**duplicates, missing values and inconsistent text** to demonstrate the
data-cleaning workflow.

---

## 🔬 Methodology
1. **Data Collection** – transactional dataset (`data/`).
2. **Data Cleaning** – remove duplicates, handle missing `Unit Price`
   (replace with average), standardise names (`TRIM`/`PROPER`), fix category
   spelling, validate dates.
3. **Feature Engineering** – `Total Purchase Value = Qty × Unit Price`,
   `Month`, `Age Group`, `Purchase Frequency`, `Customer Segment`, `Loyalty Status`.
4. **EDA & Metrics** – PivotTables for revenue, AOV, frequency, CLV.
5. **Segmentation & Trend Analysis** – by segment, region, category, month.
6. **Visualisation** – KPI cards + 8 PivotCharts + heatmap on one dashboard.
7. **Insight & Reporting** – see [`reports/Project_Report.md`](reports/Project_Report.md).

## 📐 Key Metrics (KPIs)
| Metric | Value |
|---|---|
| Total Revenue | **₹23.9 Lakh** (₹2,385,136) |
| Unique Customers | **46** |
| Average Order Value (AOV) | **₹11,926** |
| Repeat Purchase Rate | **85%** |
| Avg Customer Value / Basic CLV | **₹51,851** |

---

## 📊 Visualisations on the Dashboard
- KPI cards: Revenue, Customers, AOV, Repeat Rate, CLV
- Revenue Trend by Month (line) · Revenue by Product Category (bar)
- Revenue by Customer Segment · by Region · by Age Group (columns)
- Top 10 Customers by Revenue (bar) · Payment Method Share (pie)
- Customers by Loyalty Tier · **Region × Category revenue heatmap**
- **Slicers** (Region, Category, Segment, Loyalty) + **Purchase Date Timeline**
  that filter every chart simultaneously.

## 💡 Key Insights
- **Pareto holds:** the top **20% of customers generate ~60% of revenue** —
  ideal candidates for a loyalty / VIP programme.
- **Electronics** is the dominant category (~67% of revenue); Groceries the
  smallest — informs inventory and promotion focus.
- **East & North regions** lead revenue; **South** lags and is a growth target.
- **Festive peak in October 2024** (Diwali) — plan campaigns & stock for Q4.
- **UPI dominates payments (~58%)**, confirming a digital-first customer base.
- **Premium segment** drives the largest revenue share — protect with retention.
- **85% repeat purchase rate** signals strong loyalty worth nurturing.

---

## 📁 Repository Structure
```
customer-purchase-pattern-analyzer/
├── data/
│   ├── customer_purchases.csv          # clean analytical dataset (200 rows)
│   └── customer_purchases_raw.csv      # messy version for cleaning demo
├── workbook/
│   └── Customer_Purchase_Pattern_Analyzer.xlsx   # interactive dashboard
├── images/
│   └── dashboard_preview.png           # dashboard screenshot
├── reports/
│   └── Project_Report.md               # full written report
├── scripts/                            # reproducible generators (Python)
│   ├── generate_dataset.py
│   └── build_workbook.py
└── README.md
```

## ▶️ How to Use
1. Open `workbook/Customer_Purchase_Pattern_Analyzer.xlsx`.
2. Go to the **Dashboard** sheet.
3. Use the **Slicers** and **Timeline** to filter by region, category, segment,
   loyalty tier or date — all visuals update instantly.
4. The **Data** sheet holds the source table (`tblSales`); **Calc** holds the
   PivotTables (hidden by default).

*To regenerate from scratch (optional): `python scripts/generate_dataset.py`
then `python scripts/build_workbook.py` — requires Excel + `pywin32`, `pandas`.*

## ✅ Conclusion
This project demonstrates the complete analyst workflow — data cleaning,
feature engineering, KPI calculation, segmentation, visualisation and insight
generation — entirely in Excel, in a format directly usable by a retail or
e-commerce business to grow revenue and retain customers.

---
*Built as a job-ready Data Analytics portfolio project.*
