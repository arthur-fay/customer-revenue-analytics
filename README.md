# E-Commerce Executive Dashboard

## Start here — original report and interactive companion

| What to inspect | Link |
| --- | --- |
| **Original Power BI dashboard** | [Dashboard screenshot](01%20Raw%20Screenshots/Ecommerce_Executive_Dashboard.png) · [Power BI file](03%20PBIX%20FILE/Ecommerce_Executive_Dashboard.pbix) · [PDF export](04%20Exports/Ecommerce_Executive_Dashboard.pdf) |
| **Dimensional model and DAX** | [Data model](#data-model) · [Selected measures](#selected-dax-measures) |
| **Companion browser lab** | [Open the E-Commerce Analytics Lab](https://arthur-fay.github.io/lab/ecommerce/) · [Lab source and tests](https://github.com/arthur-fay/arthur-fay.github.io/tree/main/lab/ecommerce) |
| **Broader engineering portfolio** | [Arthur Fay — The Architect Lab](https://arthur-fay.github.io/) |

**Scope and provenance.** The metrics below are **rounded figures reported by this Power BI project's README** (for example, 99K orders and R$15.84M revenue), not a transaction-level export published by the browser lab. The separate static-site lab explores the documented model and DAX and calculates **explicitly hypothetical** what-if scenarios. Scenario outputs must not be interpreted as observed business results or forecasts. The companion lab has tests in the portfolio repository; this original Power BI repository does **not claim a CI-tested web service**.

An end-to-end e-commerce analytics project built with SQL, Google Colab, and Power BI. The project transforms transactional data into an interactive executive dashboard focused on revenue, customers, order performance, delivery reliability, and product-category performance.

## Dashboard Preview

![E-Commerce Executive Dashboard](01%20Raw%20Screenshots/Ecommerce_Executive_Dashboard.png)

## Annotated Dashboard

![Annotated E-Commerce Dashboard](02%20Annotated%20Images/Ecommerce_Executive_Dashboard_Annotated.png)

## Project Overview

This project was created to provide business leaders with a clear view of overall e-commerce performance.

The dashboard allows users to:

- Track total orders, revenue, customers, and average order value
- Monitor delivery and on-time delivery performance
- Analyze monthly revenue trends
- Identify the highest-revenue product categories
- Compare completed, failed, and incomplete orders
- Filter the dashboard by year range and order status

## Key Performance Indicators

| KPI | Result |
|---|---:|
| Total Orders | 99K |
| Total Revenue | R$15.84M |
| Total Customers | 96K |
| Average Order Value | R$159.33 |
| Delivery Rate | 97.02% |
| On-Time Delivery Rate | 91.88% |

## Key Business Insights

- Health and beauty generated the highest product-category revenue at approximately R$1.44M.
- Watches and gifts followed with approximately R$1.31M.
- Monthly revenue increased considerably throughout the analysis period.
- Completed orders represented the overwhelming majority of all orders.
- Approximately 97% of orders were delivered successfully.
- More than 91% of delivered orders arrived on time.
- The dashboard includes year-range and order-status filters for interactive analysis.

## Dashboard Features

- Six executive KPI cards
- Monthly revenue trend analysis
- Top 10 product categories by revenue
- Orders by status comparison
- Interactive year-range slicer
- Interactive order-status slicer
- Dynamic cross-filtering between visuals
- Incomplete-month filtering for accurate trend reporting
- Professional dashboard annotations for portfolio presentation

## Data Model

![E-Commerce Data Model](01%20Raw%20Screenshots/Ecommerce_Data_Model.png)

The Power BI model uses a dimensional structure with fact and dimension tables.

### Fact Tables

- `fact_orders`
- `fact_order_items`
- `fact_cohort_retention`

### Dimension Tables

- `dim_date`
- `dim_customer`
- `dim_product`
- `dim_seller`
- `dim_payment_method`
- `dim_order_status`

### Measure Table

- `KPI_Measures`

The relationships support filtering across dates, customers, products, sellers, payment methods, and order statuses.

## Selected DAX Measures

```DAX
Total Orders =
COUNTROWS(fact_orders)
```

```DAX
Total Revenue =
SUM(fact_order_items[merchandise_revenue])
    + SUM(fact_order_items[freight_revenue])
```

```DAX
Average Order Value =
DIVIDE(
    [Total Revenue],
    [Total Orders],
    0
)
```

```DAX
Delivery Rate % =
DIVIDE(
    [Delivered Orders],
    [Total Orders],
    0
)
```

```DAX
On-Time Delivery Rate % =
DIVIDE(
    [On-Time Delivered Orders],
    [Delivered Orders],
    0
)
```

## Tools and Technologies

- SQL
- Google Colab
- Power BI Desktop
- Power Query
- DAX
- Data modeling
- Data visualization
- Business intelligence
- GitHub

## Repository Structure

```text
customer-revenue-analytics/
├── 01 Raw Screenshots/
│   ├── Ecommerce_Executive_Dashboard.png
│   └── Ecommerce_Data_Model.png
├── 02 Annotated Images/
│   └── Ecommerce_Executive_Dashboard_Annotated.png
├── 03 PBIX FILE/
│   └── Ecommerce_Executive_Dashboard.pbix
├── 04 Exports/
│   └── Ecommerce_Executive_Dashboard.pdf
└── README.md
```

## Project Files

- [Download the Power BI dashboard](03%20PBIX%20FILE/Ecommerce_Executive_Dashboard.pbix)
- [View the dashboard PDF](04%20Exports/Ecommerce_Executive_Dashboard.pdf)
- [View the clean dashboard image](01%20Raw%20Screenshots/Ecommerce_Executive_Dashboard.png)
- [View the annotated dashboard image](02%20Annotated%20Images/Ecommerce_Executive_Dashboard_Annotated.png)
- [View the data model](01%20Raw%20Screenshots/Ecommerce_Data_Model.png)

## Skills Demonstrated

- Data cleaning and transformation
- Relational and dimensional data modeling
- KPI development with DAX
- Interactive dashboard development
- Time-series analysis
- Product-category analysis
- Operational-performance analysis
- Data storytelling
- Executive reporting
- GitHub repository documentation

## Author

**Arthur Fay**

Data Analytics and Business Intelligence Portfolio Project
