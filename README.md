# Reverse Logistics and Returns Analysis

## One-Line Summary

A supply chain analytics case study using Python, SQL, and Power BI to analyze e-commerce returns, quantify reverse logistics impact, and support operational improvement decisions.

## Business Problem

Product returns are a major challenge in e-commerce operations. High return volumes increase reverse logistics costs, extend processing time, affect customer satisfaction, add warehouse workload, create packaging waste, and contribute to avoidable sustainability impacts.

For supply chain teams, returns are not only a customer service issue. They influence inventory recovery, fulfillment planning, warehouse capacity, product quality feedback, margin protection, and sustainability performance.

## Project Objective

The objective of this project is to use data analytics to understand return patterns, identify high-return product categories and reasons, measure cost and processing impact, and summarize reverse logistics KPIs through SQL analysis and a Power BI dashboard.

The project is designed as a practical business intelligence case study for e-commerce reverse logistics and returns management.

## Why This Project Matters in Supply Chain Management

This project connects directly to core supply chain management areas:

- Reverse logistics: Measures returned order volume, return reasons, and return processing behavior.
- Return rate analysis: Identifies which product categories contribute most to returns.
- Cost control: Quantifies return cost impact by category and overall returned orders.
- Operational efficiency: Reviews return processing time and operational workload.
- Sustainability: Tracks CO2 emissions, packaging waste, CO2 saved, and waste avoided fields available in the dataset.
- Inventory and fulfillment planning: Highlights categories and regions that may need closer operational review.
- Business intelligence: Converts raw and processed data into analysis-ready outputs for SQL and Power BI reporting.

## Dataset Overview

The repository includes two CSV files:

- `data/raw/returns_sustainability_dataset.csv`
- `data/processed/returns_cleaned_for_sql_powerbi.csv`

The processed dataset contains 5,000 e-commerce order records and 27 fields. The available fields include:

- Order and product information: `order_id`, `product_id`, `order_date`, `product_category`, `product_price`, `order_quantity`, `order_value`
- Customer information: `user_id`, `user_age`, `user_gender`, `user_location`
- Fulfillment and payment information: `shipping_method`, `payment_method`, `discount_applied`, `discount_bin`
- Return information: `return_status`, `return_reason`, `days_to_return`, `returned`
- Cost and profit fields: `return_cost`, `profit_loss`
- Sustainability fields: `co2_emissions`, `packaging_waste`, `co2_saved`, `waste_avoided`
- Time fields: `order_month`, `order_year`

Note: The repository does not include separate data documentation explaining whether the dataset is real, synthetic, or sample data. To be added manually.

## Tools and Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- SQL
- Power BI
- Jupyter Notebook
- GitHub

## Key Business Questions

- What is the overall return rate for the e-commerce order dataset?
- Which product categories generate the highest number of returns?
- Which product categories have the highest return rates?
- What are the most common reasons for returned products?
- Which categories create the highest return cost impact?
- Which categories have longer return processing times?
- What sustainability impact is associated with returned products?
- How can return analytics support cost control, warehouse planning, and reverse logistics improvements?

## Methodology

1. Data collection/import from the available CSV dataset.
2. Data cleaning and standardization in Python.
3. Exploratory data analysis for returns, categories, reasons, locations, shipping methods, payment methods, and discounts.
4. SQL analysis for operational aggregations and KPI-style queries.
5. KPI calculation for total orders, returned orders, return rate, return cost, and processing time.
6. Dashboard development in Power BI using the processed CSV.
7. Insight generation from verified dataset outputs.
8. Business recommendation development for reverse logistics improvement.

## Python Analysis Summary

The notebook `notebooks/Reverse_Logistics_Analysis.ipynb` prepares and analyzes the returns dataset. It performs the following work:

- Loads the raw returns dataset from `data/raw/returns_sustainability_dataset.csv`
- Standardizes column names to lowercase
- Checks dataset shape, data types, and missing values
- Creates a boolean `returned` flag from `return_status`
- Converts `order_date` into date format
- Creates `order_month` and `order_year` fields for trend analysis
- Performs consistency checks on non-returned orders and return costs
- Calculates core KPIs such as total orders, returned orders, return rate, total return cost, and average return cost
- Reviews return reasons, product categories, user locations, monthly return trends, shipping methods, payment methods, and discount bins
- Exports the processed dataset to `data/processed/returns_cleaned_for_sql_powerbi.csv`

## SQL Analysis Summary

The SQL file `sql/reverse_logistics_analysis.sql` contains business analysis queries for a table named `returns_raw`. The queries cover:

- Total orders and returned orders
- Overall return rate
- Returns and return rate by product category
- Return reasons among returned orders
- Return cost impact by product category
- Return processing time by product category
- Sustainability metrics by product category
- Yearly return trend

These queries are intended to be run after loading `data/processed/returns_cleaned_for_sql_powerbi.csv` into a SQL database table named `returns_raw`.

## Power BI Dashboard Summary

The repository includes a Power BI file:

`dashboard/Reverse_Logistics_Analytics.pbix`

The dashboard is intended to communicate reverse logistics performance through KPIs and visuals such as:

- Total orders, returned orders, and return rate
- Category-level return performance
- Return reason breakdown
- Regional or location-based return patterns
- Return processing time
- Return cost impact
- Sustainability metrics such as CO2 emissions and packaging waste
- Operational insights for reverse logistics decision-making

Dashboard screenshots to be added manually.

![Dashboard Overview](images/dashboard_overview.png)

![Return Analysis](images/return_analysis.png)

![Cost and Sustainability](images/cost_sustainability.png)

## Key Insights

The following insights are supported by the available processed dataset:

- Total orders: 5,000
- Returned orders: 1,450
- Overall return rate: 29.0%
- Clothing generated the highest number of returns, with 661 returned orders.
- Clothing had the highest category return rate, at approximately 37.43%.
- The most common return reasons were Defective, Changed Mind, Wrong Item, and Size Issue.
- Clothing generated the highest total return cost impact, followed by Electronics.
- Average return processing time was highest for Electronics, followed closely by Clothing.
- Return rate increased from 26.48% in 2022 to 31.36% in 2024, then decreased to 28.33% in 2025.

Dashboard-specific findings: To be added manually after final dashboard review.

## Business Recommendations

- Investigate high-return categories, especially Clothing, to identify product quality, sizing, description, or expectation gaps.
- Improve product information, images, sizing guidance, and fit details to reduce avoidable returns.
- Track return reasons by category to separate preventable returns from expected customer behavior.
- Prioritize warehouse resources for categories with higher return volumes or longer processing times.
- Monitor regional or location-based return patterns to identify fulfillment, delivery, or customer experience issues.
- Review Electronics and Clothing return workflows because they show higher average processing times.
- Track packaging waste, CO2 emissions, CO2 saved, and waste avoided to connect return reduction with sustainability goals.
- Use yearly return trends to evaluate whether return reduction initiatives improve operational performance over time.

## Limitations

- The dataset may not represent all e-commerce operations.
- The repository does not include source documentation confirming whether the dataset is real, synthetic, or sample data.
- External factors such as delivery partners, supplier quality, product descriptions, customer behavior, and return policy design may influence returns.
- Analysis depends on the available fields and data quality in the CSV files.
- Financial impact estimates should be validated with real business cost data before being used for operational decisions.
- Power BI visuals require Power BI Desktop to open and review the `.pbix` file.
- More advanced root-cause analysis would require additional fields such as SKU-level details, supplier information, fulfillment center, delivery SLA, customer complaints, and inspection outcomes.

## Future Improvements

- Add dashboard screenshots to the `images/` folder.
- Add a data dictionary in the `docs/` folder.
- Add predictive modeling for return risk.
- Add customer segmentation analysis.
- Add supplier, SKU, and product quality analysis.
- Add inventory recovery and fulfillment center impact analysis.
- Add automated Power BI dashboard refresh.
- Add a Streamlit app if an interactive web version is useful.
- Add scenario analysis for cost reduction and sustainability improvement.

## Folder Structure

```text
Reverse-Logistics-and-Returns-Analysis/
|-- data/
|   |-- raw/
|   |   |-- returns_sustainability_dataset.csv
|   |-- processed/
|   |   |-- returns_cleaned_for_sql_powerbi.csv
|-- notebooks/
|   |-- Reverse_Logistics_Analysis.ipynb
|-- sql/
|   |-- reverse_logistics_analysis.sql
|-- dashboard/
|   |-- Reverse_Logistics_Analytics.pbix
|-- docs/
|-- images/
|-- README.md
|-- requirements.txt
|-- .gitignore
|-- LICENSE
```

## How To Review The Project

1. Start with this README to understand the business problem and workflow.
2. Open `notebooks/Reverse_Logistics_Analysis.ipynb` to review the Python cleaning and analysis steps.
3. Review `sql/reverse_logistics_analysis.sql` for SQL-based operational analysis.
4. Open `dashboard/Reverse_Logistics_Analytics.pbix` in Power BI Desktop to explore the dashboard.
5. Add dashboard screenshots to the `images/` folder using the placeholder names shown above.

## Academic CV Project Description

Title:
Reverse Logistics and Returns Analysis for E-Commerce Operations

Duration:
To be added manually

Technologies:
Python, Pandas, NumPy, Matplotlib, SQL, Power BI, Jupyter Notebook, GitHub

Objective:
Analyze e-commerce return patterns to understand the operational, cost, and sustainability impact of reverse logistics. Use Python, SQL, and Power BI to convert returns data into supply chain KPIs, dashboard visuals, and business recommendations.

Brief Description:
Developed a supply chain analytics case study focused on reverse logistics and e-commerce returns management. The project analyzes order, product, customer, return, cost, processing time, and sustainability fields to identify return drivers, evaluate category-level return behavior, and support operational decision-making. The final workflow combines Python-based data preparation, SQL aggregation queries, and Power BI dashboarding to present reverse logistics insights in a business intelligence format suitable for supply chain planning and performance improvement.

Individual Role:

- Cleaned and prepared the e-commerce returns dataset for analysis.
- Performed Python-based exploratory analysis of return rates, return reasons, product categories, locations, shipping methods, payment methods, and discount patterns.
- Designed KPI calculations for total orders, returned orders, return rate, return cost, and processing time.
- Wrote SQL queries for operational return analysis, category-level aggregation, cost impact, processing time, sustainability metrics, and yearly trends.
- Developed a Power BI dashboard file for reverse logistics reporting and business intelligence review.
- Converted analytical findings into supply chain-focused insights and business recommendations.

Key Findings:

- Total orders: 5,000
- Returned orders: 1,450
- Overall return rate: 29.0%
- Clothing had the highest return volume and highest category return rate in the dataset.
- To be added manually after final dashboard review.

Learning Outcomes:

- Built practical understanding of reverse logistics analytics and e-commerce returns management.
- Learned how to design operational KPIs for returns, cost impact, processing time, and sustainability.
- Applied Python and SQL to prepare, validate, and summarize supply chain analytics data.
- Practiced Power BI dashboarding for business intelligence and executive reporting.
- Strengthened supply chain decision-making by connecting data analysis to operational recommendations.

## Author

Mohit Kalicharan Ranganath

Engineering Management graduate focused on Supply Chain Analytics, Business Intelligence, Data Analytics, and Operations Analytics.
