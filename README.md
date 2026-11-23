# Amazon Sales & Product Performance Analysis

An interactive Power BI dashboard that analyses Amazon fashion sales by state, city, order status and product, with a written business report of findings and recommendations.

![Overview](Screenshots/1.OVERVIEW.PNG)

## Dashboard Preview

| Product | Product View |
|---|---|
| ![Product](Screenshots/2.PRODUCT.PNG) | ![Product View](Screenshots/3.PRODUCT_VIEW.PNG) |

![Product tooltip](Screenshots/4.TOOLTIP.PNG)
## Project Overview

The report covers **31 March to 29 June 2022 (91 days)** and combines headline KPIs, geographic analysis, a daily sales trend and a product drill-down. It has four pages:

| Page | Description |
|---|---|
| **Overview** | Sales KPIs, sales by city and state, order status slicer, daily sales trend, Sales/Units toggle |
| **Product** | Category list and image-led product gallery |
| **Product View** | Single-product KPIs, date range slicer, units by date, related products |
| **Product_Tooltip** | Hidden hover card with product KPIs and units by month |

## Business Questions

1. How large is the sales base and how did it move from April to June?
2. Which states and cities generate the most sales?
3. How concentrated is demand in a few markets?
4. What does order status say about fulfilment risk?
5. How do individual products perform over time?
6. Which dashboard metrics need correcting before they are trusted?

## Key KPIs

| KPI | Value |
|---|---|
| Total Sales (unfiltered) | 120.30K |
| Seller Count | 19.25K |
| Average daily sales | about 1,320 |
| Peak day | 1,947 (early May 2022) |
| Order statuses available | 13 (6 are failure or return statuses) |

## Key Findings

1. **Demand is concentrated by state.** Maharashtra (about 21K, 17.5%) and Karnataka (about 16K, 13.3%) lead. The top 3 states make up about 40% of sales and the top 5 about 57%.
2. **Sales are metro-driven.** Bengaluru (about 11K), Hyderabad (9K), Mumbai (7K), Chennai (6K) and New Delhi (6K) together make up about 32% of sales. Kerala and Andhra Pradesh have no city in the top 12, so their demand is spread across many small towns.
3. **Daily sales peaked in early May.** Sales hit 1,947, then fell about 48% within roughly two weeks to a low of 1,016. From late May to June they stayed between about 1,000 and 1,480. The highest labelled June day is about 16% below the highest labelled April day.
4. **Fulfilment risk is not measured.** The data has statuses such as Cancelled, Lost in Transit, Damaged and Returned, but the dashboard only uses status as a filter and never shows the mix.
5. **Product performance varies widely.** The BODYCARE Boxer for Boys Pack of 2 sold 55 units (about 31K). The $15 Ties Necktie and Pocket Square Set sold 3 units (about 5K). The boxer sold 22 units in April, 14 in May (-36%) and 19 in June.

## Recommendations

- Verify the Returned, Review and Seller Count definitions.
- Add a status mix chart plus delivered, cancellation and return rates by state and city.
- Protect stock and delivery speed in the top states and metros.
- Overlay promotions and stock data on the daily trend to explain the May spike.
- Add category and product rankings and separate volume leaders from the long tail.
- Standardise city and state text and label units and currency on every card.

## Known Issues and Next Steps

| # | Issue | Evidence | Suggested fix |
|---|---|---|---|
| 1 | Returned and Review look inconsistent with units | One product shows 55 units but Returned = 600 and Review = 660 | Confirm each measure definition |
| 2 | Month axis in wrong order | Tooltip shows April, June, May | Sort the Month axis by month number |
| 3 | Partial days at both ends | First day 161, last day 649 | Exclude or annotate partial days |
| 4 | Inconsistent text casing | "pune" and "Gujarat" among upper-case names | Standardise city and state text |
| 5 | Two identical sales cards | Total Sales and Sales both show 120.30K | Label "All data" and "Current selection" |
| 6 | Seller Count undefined | 19.25K with no definition | Document the measure |
| 7 | Units and currency unlabelled | Sales behaves like a count, Amount like a value | Label every card |

## Tools & Technologies

- **Microsoft Power BI Desktop**: report development and interactive visuals
- **DAX**: measures `All_Overall_Sale`, `Filter_Sale`, `Seller_Count`, `Sale_Amount`, `Sale_Units`, `Review`
- **Power Query / data model**: `Amazon` fact table, `amazon-fashion - YT` product table, `Sale_Option` toggle
- **Git & GitHub**: version control and documentation

## Repository Structure

```
Amazon-Sales-Performance-Analysis/
│
├── README.md
│
├── PowerBI/
│   └── Amazon Sales Dashboard.pbix
│
├── Documentation/
│   ├── Amazon Sales Dashboard — Business Analysis Report.pdf
│   └── Technical_Dashboard_Review.md
│
└── Screenshots/
    ├── 1.OVERVIEW.PNG
    ├── 2.PRODUCT.PNG
    ├── 3.PRODUCT_VIEW.PNG
    └── 4.TOOLTIP.PNG
## How to Use

1. Install [Microsoft Power BI
