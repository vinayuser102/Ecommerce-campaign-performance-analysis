# E-Commerce Campaign Performance Analysis

## Project Overview
This project analyzes e-commerce advertising campaign performance using **Excel and Power BI**.  
The objective is to evaluate campaign efficiency, advertising spend effectiveness, and identify high-performing campaigns using key marketing metrics such as **Spend, Sales, CTR, and ROAS**.

The analysis includes Excel-based calculations and an interactive **Power BI dashboard** to visualize campaign performance trends.

---

## Business Questions

### Question 1 – Excel Analysis
Calculate product shipping and storage metrics from raw dimensions and selling prices.

Objectives:
- Transform raw product dimensions (L x B x H) into meters
- Calculate packaging volume and 3-month storage cost
- Derive the **Buying Price** after deducting storage cost, channel commission (15%), returns (10%), and closing fee (order value based)
- Prepare data for operational logistics decisions


---

### Question 2 – Excel Business Metrics
Analyze 2024 sales data (2,628 purchase orders, 3 SKUs) and determine inventory planning metrics.

Objectives:
- Evaluate sales performance by **units sold** and **revenue** (Quantity × Wholesale Price)
- Estimate 3-month stock requirements from average monthly sales
- Calculate reorder quantities against opening stock (as of 1 Jan 2025)
- Support operational planning


---

### Question 3 – Power BI Dashboard
Build an interactive **PPC Campaign Performance Dashboard** to analyze advertising metrics.

Dashboard Metrics:
- Total Spend
- Total Sales
- CTR (Click-Through Rate)
- ROAS (Return on Ad Spend)

Dashboard Visualizations:
- Sales by Campaign
- Clicks by Campaign
- Spend vs Sales Trend
- Campaign Performance Table
- Interactive Filters (Date & Campaign)

The dashboard covers the **full analysis period (31 Aug 2024 – 31 Dec 2024)** and all 36 campaigns by default.


---

## Dashboard Preview



<img width="636" height="363" alt="Screenshot 2026-03-11 134410" src="https://github.com/user-attachments/assets/112b230f-78cf-4a19-a286-a9228fa90b91" />


## Key Metrics (Full Period: 31 Aug 2024 – 31 Dec 2024)

| Metric | Value |
| --- | --- |
| Campaigns analyzed | 36 |
| Advertising spend | $165,999.58 |
| Total sales | $376,751.77 |
| Impressions / Clicks | 7,490,947 / 29,948 |
| CTR (click-through rate) | ~0.40% |
| ROAS (return on ad spend) | 2.27 (range 0.00 – 5.89 across campaigns) |
| 7-day orders | 252 |

## Key Insights

- A small number of campaigns generate the majority of sales revenue — the top 5 by spend account for roughly one-third of total advertising spend.
- Higher ad spend does not always produce higher **ROAS** (best performer `MHI-VS-25019 | SP | Auto` achieves 5.89 on ~$431 spend, while top spender `Wall Decor Check` returns 2.81).
- Certain campaigns have high **click volume but lower conversion efficiency**.
- 5 of 36 campaigns recorded spend with **zero attributed sales** (e.g. `MHI-OB-26004 | SP | Manual | ASIN | Category`, $5,328.93 spend / $0 sales), signaling clear optimization candidates.
- Sales performance fluctuates across days, suggesting opportunities for campaign optimization.

---

## Corrections & Data Notes

The following corrections were applied to keep the calculations accurate and unambiguous:

- **Q1 – Buying Price formula (commission counted once):** the buying-price calculation previously deducted the 15% channel commission twice (once inline and once via the computed Commission column). It now subtracts each cost exactly once: `Selling Price − Storage Cost − Commission − Returns − Closing Fee`.
- **Q1 – Dimension parsing:** dimension text is parsed by splitting on `X` (whitespace-insensitive) so values with trailing spaces parse correctly; header typo `Dimentions` corrected to `Dimensions`.
- **Q2 – Column F populated:** the empty `Sales` column F is now a **Line Total** (`Quantity × Wholesale Price`) for all 2,628 rows.
- **Q2 – Units vs Revenue clarified:** the `Total Sales 2024` metric actually sums **quantity**, so it is labelled **Total Units Sold 2024**, and a separate **Total Revenue 2024** column was added (`SUMIF` over Line Total) to avoid ambiguity.
- **Q3 – Dashboard date filter:** the Power BI dashboard had a leftover hard-coded date filter (3 Nov – 31 Dec 2024) applied to the KPI cards and all charts, which hid 7 of 36 campaigns (including the top spender). The filter was removed so the dashboard shows the full period by default; the **Date slicer** is the only date control.

---

## Tools Used

- Microsoft Excel
- Power BI
- Data Analysis
- Business Analytics

---

## Project Structure

ecommerce-campaign-performance-analysis
│
├── Datasets
│ ├── Q1.xlsx
│ ├── Q2.xlsx
│ └── Q 3.xlsx
│
├── Excel Analysis
│ ├── Vinaysharma_Q1_Solution.xlsx
│ └── Vinaysharma_Q2_Solution.xlsx
│
├── Power-bi Dashboard
│ ├── VinaySharma_PPC_Campaign_Dashboard.pbix
│ └── Dashboard_Preview.png
│
└── README.md
