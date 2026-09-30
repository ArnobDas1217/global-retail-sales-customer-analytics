# Global Retail Sales & Customer Analytics

A Power BI project built around a fictional global retail business. The goal was to take raw sales, customer, product, geography, channel, segment, date, and returns data and turn it into something that could actually be used to understand the business.

The analysis covers sales, profitability, product performance, discounts, customers, returns, regional performance, and seasonality.

> **Note:** The dataset is synthetic/anonymized and is used for portfolio and analytical purposes.

---

## What I worked on

I built the project from the data preparation stage through to the final dashboard:

- Cleaned and transformed the raw data using Power Query
- Checked data types, missing values, duplicates, and key relationships
- Built a star-schema data model in Power BI
- Created DAX measures for the main business metrics
- Used the model to investigate profitability, customers, discounts, returns, and seasonality
- Built a four-page Power BI report
- Summarized the main findings and their possible business implications

The idea was to start with business questions rather than simply building charts.

---

## Tools

- Power BI
- Power Query
- DAX
- Data Modeling
- Excel/CSV data

---

## Data Model

The model is built around sales transactions with supporting dimension tables.

### Fact tables

- `FactSales`
- `FactReturns`

### Dimension tables

- `DimDate`
- `DimCustomer`
- `DimProduct`
- `DimGeography`
- `DimChannel`
- `DimSegment`

`FactSales` is connected to the customer, product, geography, channel, segment, and date dimensions. Returns are linked to the corresponding sales order lines.

---

## Data Preparation

The source data included a few realistic data-quality issues that needed to be handled before analysis.

Some of the work done in Power Query included:

- Cleaning whitespace from text fields
- Standardizing inconsistent category names
- Checking and setting appropriate data types
- Handling blank shipping-cost values
- Checking date formats
- Validating primary and foreign keys
- Checking for duplicate dimension records
- Checking for negative quantities
- Validating sales and profit calculations

I kept the intentional blank shipping-cost records rather than treating them as errors.

---

## Key Numbers

Across the full 2023–2025 dataset:

| Metric | Value |
|---|---:|
| Total Sales | 22.54M |
| Total Profit | 3.99M |
| Profit Margin | 17.71% |
| Total Orders | 50K |
| Total Customers | 9K |
| Total Units Sold | 211K |
| Average Order Value | 453.28 |
| Average Discount | 6.56% |
| Return Rate | 4.11% |

---

## Dashboard

The report is split into four pages.

### 1. Executive Overview

A high-level view of the business.

It includes:

- Total Sales
- Total Profit
- Profit Margin
- Total Orders
- Total Customers
- Average Order Value
- Monthly sales trend
- Sales by region
- Profit margin by category
- Low-margin sales contribution

---

### 2. Profitability & Product Performance

This page looks more closely at where revenue and profit are coming from.

The analysis includes:

- Profit by category
- Sales vs. profit margin by product
- Profit margin by subcategory
- Average discount vs. profit margin
- High-sales, low-margin products
- Subcategory-level profitability

---

### 3. Customers, Returns & Seasonality

This page focuses on customers, returns, and changes in sales throughout the year.

It includes:

- Return rate by subcategory
- Return rate by region
- Return rate by customer segment
- Sales by customer segment
- Segment-level profit margin and AOV
- Sales and average discount over time

---

### 4. Business Insights & Recommendations

The final page summarizes the main findings from the analysis rather than adding more visualizations.

---

## What I Found

### Low-margin revenue is a significant part of sales

Subcategories with profit margins below 10% account for **33.68% of total sales**, but contribute only **14.18% of total profit**.

This creates a clear gap between revenue contribution and profit contribution and makes these subcategories worth investigating further.

### Revenue is not heavily concentrated among a few customers

The top 10 customers account for only **2.11% of total revenue**.

This means the business's revenue is spread across a relatively large customer base rather than being heavily dependent on a small number of customers.

### Higher-discount subcategories tend to have lower margins

In this dataset, the subcategories with average discounts above 7% have profit margins below 10%.

The relationship is visible in the discount-vs-margin analysis, although the analysis does **not** establish that discounts directly cause lower margins.

### Some categories have noticeably higher return rates

The overall return rate is **4.11%**.

The highest return rates in the analysis include:

- Footwear — 8.25%
- Womenswear — 7.83%
- Sportswear — 7.80%
- Menswear — 7.28%
- Accessories — 7.03%

These categories could be investigated further for potential product, sizing, quality, or fulfillment-related issues.

---

## Business Takeaways

The analysis points to a few areas that would be worth investigating in a real retail business:

- Review pricing and discounting for consistently low-margin subcategories.
- Investigate high-sales products that generate relatively little profit.
- Look more closely at categories with unusually high return rates.
- Monitor promotional periods to understand the trade-off between sales growth and margin.
- Continue monitoring customer concentration as the business grows.

These are areas for further investigation rather than conclusions about the underlying causes.

---

## DAX Measures

Some of the main measures used in the report include:

- Total Sales
- Total Profit
- Total Orders
- Total Units
- Total Customers
- Average Order Value
- Profit Margin
- Average Discount
- Sales LY
- YoY Sales Growth %
- Profit LY
- YoY Profit Growth %
- Running Total Sales
- Customer Revenue
- Revenue Contribution %
- Total Returns
- Return Rate
- Low Margin Sales
- Low Margin Sales Contribution %
- Top 10 Customer Contribution %

A dedicated date table was also used for the time-based analysis.

---

## Project Structure

The repository currently contains the Power BI report:

```text
global-retail-sales-customer-analytics/
│
└── Retail Sales Dashboard.pbix
```

---

## Why I Built This

I wanted this project to go beyond making a few Power BI charts.

The main exercise was understanding the complete workflow:

**Raw Data → Cleaning → Data Modeling → DAX → Analysis → Dashboard → Business Insights**

---

## Author

**Arnob Das**

B.Sc. Computer Science Honours  
Kolkata, India
