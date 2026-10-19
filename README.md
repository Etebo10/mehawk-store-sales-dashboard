 Mehawk Store Sales Dashboard

An interactive Excel dashboard that turns 9,994 retail orders (2011-2014) into clear answers: what sells, what makes money, and where profit is leaking.

![Excel 2016+](https://img.shields.io/badge/Excel-2016%2B-217346?logo=microsoftexcel&logoColor=white)
![Formulas](https://img.shields.io/badge/Built%20with-Formulas%20%7C%20No%20Macros-66F2C2)
![License](https://img.shields.io/badge/License-MIT-blue)

![Dashboard preview](images/dashboard.png)

---

 The headline numbers

| Total Sales | Total Profit | Profit Margin | Units Sold | Order Lines |
|:-----------:|:------------:|:-------------:|:----------:|:-----------:|
| $2,297,201 | $286,397 | 12.5% | 37,873 | 9,994 |

 What the data says

1. Discounts are the biggest profit leak. Order lines discounted above 20% earn a **-37% margin**. Undiscounted lines earn +29.5%.
2. Furniture sells but barely profits. It brings in $742K in sales at a **2.5% margin**, against about 17% for Technology and Office Supplies. Tables lose $17,725 overall.
3. Q4 carries the year. October to December delivers **38% of annual sales**. November is the best month, February the weakest.
4. Growth is real. Sales rose **52%** from 2011 to 2014, and margin improved from 10.2% to 12.7%.
5. Central is the weak region. Its 7.9% margin is the lowest of the four, against 14.9% in the West.

Full analysis and recommendations: [docs/INSIGHTS.md](docs/INSIGHTS.md)

---

 Quick start

1. Download `dashboard/Mehawk_Store_Dashboard.xlsx`.
2. Open it in Excel 2016 or newer and click Enable Editing.
3. Use the four dropdown buttons at the top (Year, Region, Segment, Month). Pick "All" to clear a filter.

That is it. No macros, no add-ins, nothing to install.

---

## What is inside the workbook

| Sheet | What it gives you |
|---|---|
| Dashboard | 4 KPI cards, 4 "top performer" cards, 9 charts, a live Top 10 products table |
| Pivot Summary | 7 summary tables (Month, Ship Mode, Segment, Sub-Category, Year, Category, Region). Each shows share, rank, profit, margin and the top performer |
| Rankings | Pareto (80/20) of sub-categories, all 49 states, top and bottom products, top customers |
| Insights | 12 live findings with recommendations, discount-impact table, year-over-year growth |
| Notes | How it works, data checks, and live reconciliation checks |
| Engine | The calculation sheet that feeds the dashboard |
| Database | The cleaned source data (9,994 rows) |

## Repository structure

```
mehawk-store-sales-dashboard/
├── README.md
├── LICENSE
├── dashboard/
│   └── Mehawk_Store_Dashboard.xlsx    <- the main deliverable
├── data/
│   └── mehawk_store_orders.csv        <- the same data as plain CSV
├── docs/
│   ├── INSIGHTS.md                    <- findings and recommendations
│   └── DATA_DICTIONARY.md             <- every column explained
└── images/
    ├── dashboard.png
    └── social-preview.png
```

---

 How it works

- Filters are dropdown cells.** Each dropdown feeds a small set of `SUMIFS` formulas on the Engine sheet. Charts read from there, so everything updates the moment you change a filter.
- Fully formula-driven.** About 28,000 formulas, no hard-coded results and no macros. Change the data and every number, ranking and chart follows.
- Built for Excel 2016.** Only compatible functions are used: `SUMIFS`, `COUNTIFS`, `AVERAGEIFS`, `INDEX`, `MATCH`, `LARGE`, `RANK`, `IFERROR`.
- Self-checking.** The Notes sheet has live checks that confirm the summary totals match the database.

 Skills shown in this project

Data cleaning and validation, KPI design, dashboard design, advanced Excel (named ranges, SUMIFS and INDEX/MATCH ranking, conditional formatting, data validation), Pareto analysis, discount and profitability analysis, and business storytelling.

 Notes and limitations

- Filters are dropdowns rather than Excel slicers, because slicers require PivotTables. Steps to add real slicers are on the Notes sheet.
- The Year, Month, Region and Segment charts ignore their own filter on purpose, so you always see the full comparison.
- The `Country` column is blank on 41% of rows (all filled rows are "United States"). It is not used in any calculation.
- Row IDs 3406 and 3407 are identical apart from the ID. They are kept, and the impact is under $300.
- Currency is shown in $. The source data holds no currency symbol.

 Data

Order-level retail data: 9,994 order lines, 20 columns, orders from 4 Jan 2011 to 31 Dec 2014. See [docs/DATA_DICTIONARY.md](docs/DATA_DICTIONARY.md).

 Author

Ogunleti Gideon | Data Analyst
[LinkedIn](https://www.linkedin.com/in/xxxx) | [GitHub](https://github.com/etebo10) | ogunletigideon10@gmail.com

 License

Released under the [MIT License](LICENSE).
