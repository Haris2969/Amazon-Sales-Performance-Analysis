# Technical Dashboard Review

## 1. Inspection Scope

This review is based on the supplied Power BI file, `Amazon Sales Dashboard.pbix`, and its report definition.

The report contains three visible pages and one hidden tooltip page:

| Page | Display name | Purpose |
|---|---|---|
| `c59da1335017e6d037b9` | Overview | Overall sales and geographic/trend analysis |
| `1c6f511578ee5d520677` | Product | Product/category exploration |
| `0c66500a077c89cdb186` | Product View | Selected-product performance |
| `3f8f9ea30e5e2d06ca59` | Product_Tooltip | Hidden product tooltip |

## 2. Overview Page

### KPI measures
- `All_Overall_Sale`
- `Filter_Sale`
- `Seller_Count`

### Visual inventory
- Clustered bar chart: `ship-city` by `Filter_Sale`
- Clustered bar chart: `ship-state` by `Filter_Sale`
- Line chart: Date hierarchy (Year, Month, Day) by `Filter_Sale`
- KPI cards for the measures listed above

### Filters / slicers
- `amazon-fashion - YT[Category]` category selector
- Category text search
- `Amazon[Status]` list slicer
- `Sale_Option[Name]` selector

## 3. Product Page

The report definition contains:
- Category selection controls
- Product selection using `amazon-fashion - YT[product_name]`
- Product image visual
- Page navigation

## 4. Product View Page

### KPI measures
- `Amazon[Sale_Amount]`
- `Amazon[Sale_Units]`
- `Amazon[Review]`

### Visuals and controls
- Product selector
- Product image
- Date slicer on `Amazon[Date]`
- Area chart with `Amazon[Month]` on the category axis and `Amazon[Sale_Units]` on the value axis

The saved date slicer boundaries are **2022-03-31** and **2022-06-29**.

## 5. Model References Visible in Report Metadata

| Entity | Referenced columns |
|---|---|
| `Amazon` | `Date`, `Month`, `Review`, `Sale_Amount`, `Sale_Units`, `Status`, `ship-city`, `ship-state` |
| `amazon-fashion - YT` | `Category`, `product_name` |
| `Sale_Option` | `Name` |

Measures referenced from `Amazon`: `All_Overall_Sale`, `Filter_Sale`, `Seller_Count`, `Sale_Amount`, `Sale_Units`, and `Review`.

The inspected report definition does not provide enough readable information to confirm table relationships, cardinality, filter direction, all model columns, data types, or measure formulas. Validate those details in Model view or Tabular Editor before documenting them as facts.

## 6. Recommendations Before Public Release

1. Add clean screenshots of all three visible report pages.
2. Confirm source dataset attribution and license.
3. Document each DAX measure's formula and business definition.
4. Verify table relationships and filter propagation.
5. Confirm currency, units, and date coverage.
6. Check that the PBIX does not contain private or restricted source data before publishing.
7. Add numerical insights only after validating the actual values under a clearly stated filter context.
