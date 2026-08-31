# 💳 Credit Card Financial Dashboard

![SQL](https://img.shields.io/badge/SQL-MySQL%208.0-4479A1?logo=mysql&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?logo=powerbi&logoColor=black)
![License](https://img.shields.io/badge/License-MIT-green.svg)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)
![Records](https://img.shields.io/badge/Records-10K%2B-blue)

`#sql` `#mysql` `#credit-card-analytics` `#data-analysis` `#financial-dashboard` `#powerbi` `#fintech`

**Turning raw credit card transaction data into a decision-ready financial dashboard — powered by SQL, visualized in Power BI.**

---

## 🎯 What is this?

Banks and fintechs sit on a goldmine of transaction and customer data — but raw tables don't tell a story. This project builds the full pipeline from **structured SQL database → cleaned relational data → interactive dashboards**, answering the real questions a bank's analytics team would ask:

> Who are our highest-value customers? Which card tier drives the most revenue? Where is delinquency risk concentrated? How does spending shift across quarters?

---

## 📊 The Numbers at a Glance

| Metric | Value |
|---|---|
| 💰 Total Revenue | **$55M** |
| 💵 Total Transaction Amount | **$45M** |
| 📈 Total Interest Earned | **$8M** |
| 🔢 Total Transactions | **656K** |
| 👥 Customer & Card Records | **10,000+** |
| 🗓️ Coverage | Full quarterly breakdown (Q1–Q4) |

---

## 🖼️ Dashboards

### Credit Card Transaction Report
Revenue, interest, and transaction volume sliced by card category, expenditure type, customer job, education level, and payment channel (swipe / chip / online) — with quarter-over-quarter trend tracking.

### Credit Card Customer Report
A 360° customer view: revenue and income by age group, marital status, gender, dependent count, and geography — plus a top-5-states breakdown and satisfaction scoring.

*(See `docs/` for the full report exports)*

---

## 🗃️ Data Model

The database (`ccdb`) is built around two core entities, linked by `Client_Num`:

| Table | Description |
|---|---|
| `cc_detail` | Card-level data — category, credit limit, revolving balance, transaction amount/count, utilization ratio, interest earned, delinquency flag |
| `cust_detail` | Customer-level data — age, gender, income, job, education, marital status, satisfaction score, location |

Each table also has a corresponding `*_add` (additional/incremental) dataset, simulating how new weekly data would be appended in a real production pipeline.

```
Client_Num (PK)
   ├── cc_detail    → card behavior & revenue metrics
   └── cust_detail  → demographic & customer profile
```

---

## 🛠️ Tech Stack

- **MySQL 8.0+** — schema design, data storage & querying
- **Power BI** — interactive dashboard & visualization layer
- **CSV** — raw source data ingestion

---

## 📂 Repo Structure

```
credit-card-financial-dashboard/
├── dataset/
│   ├── cc_detail.csv        # Card & transaction data
│   ├── cc_add.csv           # Incremental card data
│   ├── cust_detail.csv      # Customer profile data
│   └── cust_add.csv         # Incremental customer data
├── docs/
│   ├── transaction_report.pdf
│   └── customer_report.pdf
├── transaction.sql          # Database & table creation scripts
├── LICENSE
└── README.md
```

---

## 🚀 Getting Started

1. Clone the repo
   ```bash
   git clone https://github.com/aditya-datahub/credit-card-financial-dashboard.git
   ```
2. Run `transaction.sql` in MySQL to create the `ccdb` database and its tables
3. Import the CSV files from `dataset/` into their matching tables
4. Open the Power BI reports in `docs/` to explore the dashboards, or connect Power BI directly to your MySQL instance for live data

---

## 💡 What I'd Explore Next

- Build a **credit risk scoring model** using delinquency, utilization ratio, and income data
- Add **cohort analysis** to track customer revenue over their lifecycle
- Automate the weekly `*_add` ingestion into a proper ETL pipeline

---

## 📜 License

Released under the [MIT License](LICENSE) — use it, learn from it, remix it.

---

⭐ If this project helped you understand SQL-to-BI workflows, consider giving it a star!
