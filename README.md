# Amazon Sales & Product Performance Analysis

An interactive Power BI portfolio project focused on exploring Amazon sales performance, seller activity, geographic distribution, sales trends, and product-level metrics.

## Dashboard Preview

> Dashboard screenshots will be added to the `Screenshots/` folder. Open the Power BI report to explore the interactive visuals.

## Project Overview

This project presents sales and product-related information through a multi-page Power BI report. It combines high-level performance indicators with geographic analysis, date-based trends, category filtering, and product-level exploration.

### Business Questions

1. What are the overall sales and seller counts?
2. How do selected sales compare with the overall sales measure?
3. Which shipping cities and states contribute most to the selected sales measure?
4. How do sales change over time?
5. How can users narrow the report by category, sale option, status, date, and product?
6. How do individual products perform in terms of sales amount, units, and reviews?

## Dashboard Pages

| Page | Description |
|---|---|
| **Overview** | High-level sales KPIs, sales by shipping city/state, and sales trend |
| **Product** | Product category and product selection experience |
| **Product View** | Selected product metrics, image, date filter, and monthly units trend |
| **Product_Tooltip** | Hidden tooltip page used for product-related context |

### 1. Overview

**KPI measures referenced**
- `All_Overall_Sale`
- `Filter_Sale`
- `Seller_Count`

**Visuals**
- Sales by shipping city (`ship-city`)
- Sales by shipping state (`ship-state`)
- Sales trend using the Date hierarchy

**Filters**
- Product category and category search
- Order status
- Sale option

### 2. Product

The Product page provides category and product selection controls, product imagery, and navigation to product-focused analysis.

### 3. Product View

**Measures referenced**
- `Sale_Amount`
- `Sale_Units`
- `Review`

**Visuals and controls**
- Selected product image and product selector
- Date range slicer
- Monthly sales-units area chart

The saved date slicer selection in the report is **31 March 2022 to 29 June 2022**. This is the saved selection, not a claim about the complete dataset date coverage.

## Tools & Technologies

- **Microsoft Power BI Desktop** — report development and interactive visualization
- **DAX** — measures referenced by report visuals
- **Power Query / Power BI data model** — data preparation and modeling environment
- **Git & GitHub** — version control and project documentation

## Measures Referenced

The report references these measures from the `Amazon` model entity:

- `All_Overall_Sale`
- `Filter_Sale`
- `Seller_Count`
- `Sale_Amount`
- `Sale_Units`
- `Review`

The report definition identifies measure names and their visual usage; it does not expose their DAX expressions in the inspected report metadata. Add formulas and business definitions only after validating them in Power BI Desktop.

## Fields Referenced by Report Visuals

| Model entity | Fields visible in report metadata |
|---|---|
| `Amazon` | `Date`, `Month`, `Review`, `Sale_Amount`, `Sale_Units`, `Status`, `ship-city`, `ship-state` |
| `amazon-fashion - YT` | `Category`, `product_name` |
| `Sale_Option` | `Name` |

This is not necessarily the complete source schema.

## Repository Structure

```text
Amazon-Sales-Performance-Analysis/
├── README.md
├── PowerBI/
│   └── Amazon_Sales_Dashboard.pbix
├── Documentation/
│   └── Technical_Dashboard_Review.md
└── Screenshots/
    └── README.md
```

## How to Use

1. Install [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/).
2. Clone or download this repository.
3. Open `PowerBI/Amazon_Sales_Dashboard.pbix`.
4. If prompted, configure access to the original data source.
5. Explore the report pages and interact with the slicers.

## Skills Demonstrated

- Power BI dashboard development
- KPI reporting and DAX measure usage
- Sales and product performance analysis
- Geographic and time-series visualization
- Interactive filtering and report navigation
- Business-focused dashboard documentation

## Documentation & Limitations

See [Technical Dashboard Review](Documentation/Technical_Dashboard_Review.md) for the page-by-page visual inventory and model references.

The PBIX report definition does not independently verify the full source dataset, row count, refresh history, DAX formulas, data relationships, or numerical business findings. These details should be confirmed in Power BI Desktop before publishing them as facts.

## Author

**Haris Ali Paracha**  
Data Analyst | Business Analyst | Power BI | SQL | Business Intelligence

---
*Portfolio project documentation prepared from the supplied Power BI report.*
