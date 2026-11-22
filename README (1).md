# Superstore Sales & Profit Analysis
### SQL Server | Power BI | Business Intelligence Portfolio Project

---

## Project at a Glance

This project explores Superstore order data to evaluate business performance across products, categories, customers, and regions. The work combines SQL-based data validation and analysis with a Power BI report designed to communicate the results clearly.

| Area | Project detail |
|---|---|
| Dataset | 10,194 order-line records |
| Orders | 5,111 distinct orders |
| Customers | 804 distinct customers |
| Analysis tools | SQL Server, SSMS, Power BI Desktop |
| Query language | T-SQL |
| Reporting | Power BI, DAX |
| Main outputs | 3 SQL analytical views and 1 consolidated Power BI report |

## Business Questions

The analysis was designed to answer five practical questions:

1. What are the overall sales, profit, and profit margin?
2. Which product categories and subcategories contribute most to sales and profit?
3. Which regions perform best, and where is profitability weaker?
4. How do discount levels relate to profitability in Furniture?
5. Which areas should management investigate to improve profitability?

## Data and Preparation

The working SQL Server table is `dbo.clean_superstore_orders`.

The dataset includes order and shipping dates, customer and product details, segment, region, category, subcategory, sales, quantity, discount, and profit.

Data-quality checks covered:
- Missing values in key fields and text columns.
- Non-positive sales and quantities.
- Discount values outside the expected 0–1 range.
- Shipping dates earlier than order dates.
- Exact duplicate records.

Four exact duplicate rows (two duplicate pairs) were identified and retained by project decision. They are disclosed rather than silently removed.

**Date caveat:** The dataset contains records dated after the reporting date used during project work. A published version of the report should apply and state a clear reporting cutoff. The source records were not deleted to address this.

## SQL Analysis

Three SQL views were created and used as Power BI data sources:

| View | Purpose |
|---|---|
| `dbo.vw_monthly_regional_category_performance` | Monthly performance by region and category, including sales, profit, margin, quantity, and supporting counts. |
| `dbo.vw_subcategory_performance` | Sales, profit, margin, discounts, and order/customer counts by category and subcategory. |
| `dbo.vw_furniture_discount_profitability` | Furniture Tables and Bookcases performance grouped by discount percentage. |

The additive sales, profit, and quantity totals were reconciled against the source table. Distinct counts and percentage measures are non-additive: they must be recalculated at the required reporting level rather than summed or averaged blindly across groups.

## Power BI Report

The final work is consolidated into one Power BI Desktop file with two report pages:

### Executive Overview
- Total Sales
- Total Profit
- Profit Margin

### Sales & Profit Analysis
- Monthly sales trend
- Sales by region
- Sales and profit by category
- Discount versus profit margin by category
- Profit by subcategory
- Furniture discount versus profit margin

### Overall KPI Results

| KPI | Result |
|---|---:|
| Total Sales | 2,326,534.35 |
| Total Profit | 292,296.81 |
| Profit Margin | 12.56% |

These are the reconciled totals for the imported dataset used in the project. Apply the documented reporting cutoff before presenting them as current-to-date figures.

## Key Findings

- **Technology** recorded sales of 839,893.28, profit of 146,543.38, and a 17.45% profit margin.
- **Office Supplies** recorded a 17.22% margin, while **Furniture** recorded only 2.61%, despite substantial sales.
- **West** was the strongest region by sales and profit. **Central** had the weakest regional margin at 7.92%.
- **Tables, Bookcases, and Supplies** were loss-making subcategories in the analysis.
- **Copiers** had the highest subcategory profit (56,093.94) and margin (37.21%).
- In the analyzed Furniture subcategories, higher discount levels were associated with weaker margins. This is an observed relationship, not proof of causation.

## Business Recommendations

1. Review pricing, costs, and discount approval rules for Tables and Bookcases.
2. Investigate the drivers of Central region's lower margin, including product mix, discounting, and costs.
3. Protect the profitability of strong Technology products and assess sustainable growth opportunities.
4. Review the cost and discount structure of loss-making subcategories, including Supplies.
5. Evaluate promotions using profit and margin as well as sales.
6. Apply a clear reporting-date cutoff and disclose it in the published dashboard.

## Repository Structure

Use a structure similar to this when uploading the project:

```text
Superstore-Sales-Profit-Analysis/
├── README.md
├── PowerBI/
│   └── Superstore_Sales_Profit_Analysis1final.pbix
├── SQL/
│   ├── Superstore_SQL_Scripts_vw_monthly_regional_performance.sql
│   ├── Superstore_SQL_Scripts_vw_subcategory_performance.sql
│   └── Superstore_SQL_Scripts_vw_furniture_profitability.sql
├── Screenshots/
│   ├── executive-overview.png
│   └── sales-profit-analysis.png
└── Documentation/
    └── Business_Findings_and_Recommendations.pdf
```

## Skills Demonstrated

- SQL data exploration and quality validation
- Aggregation and analytical view development
- Business KPI calculation and reconciliation
- Profitability and discount analysis
- Power BI report development
- Translating analysis into business findings and recommendations

## Notes and Limitations

- This is a descriptive analysis of the supplied dataset; it does not establish causal relationships.
- The four exact duplicate rows were retained by project decision and should be considered when interpreting record-level counts.
- Distinct order/customer counts and percentage measures are non-additive.
- The reporting cutoff must be explicitly applied and stated because the source contains future-dated records relative to the project reporting date.

---

## Author

**Name:** Add your preferred professional name  
**LinkedIn:** Add your LinkedIn profile URL  
**GitHub:** Add your GitHub profile URL
