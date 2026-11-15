# Customer Shopping Behavior Analysis

An end-to-end data analytics project that studies customer shopping behavior using **Python (pandas)**, **MySQL**, and **Power BI**.

## Overview

This project analyzes 3,900 customer transactions across four product categories (Clothing, Accessories, Footwear, Outerwear). The goal is to understand spending patterns, customer segments, product preferences, and subscription behavior, so that a business can make better decisions.

## Tools Used

| Stage | Tool |
|---|---|
| Data loading, cleaning, feature engineering | Python (pandas) |
| Database connection | SQLAlchemy + PyMySQL |
| Business analysis | MySQL 8.0 |
| Dashboard | Power BI |

## Dataset

- 3,900 rows and 18 columns
- Customer details: age, gender, location, subscription status
- Purchase details: item, category, purchase amount (USD), season, size, color
- Behavior: discount applied, previous purchases, purchase frequency, review rating, shipping type
- 37 missing values in the Review Rating column

## Project Workflow

**1. Data cleaning and EDA (Python)**
- Explored the data with `df.info()` and `df.describe()`
- Filled 37 missing review ratings using the median rating of each product category
- Renamed columns to snake_case
- Created `age_group` and `purchase_frequency_days` features
- Found that `promo_code_used` duplicated `discount_applied` and dropped it
- Loaded the cleaned data into MySQL

**2. Analysis (MySQL)**

Ten business questions answered with SQL (aggregations, CTEs, window functions):

1. Revenue by gender
2. High-spending customers who used discounts
3. Top 5 products by average rating
4. Standard vs. Express shipping spend
5. Subscribers vs. non-subscribers
6. Discount-dependent products
7. Customer segmentation (New, Returning, Loyal)
8. Top 3 products per category
9. Repeat buyers and subscriptions
10. Revenue by age group

**3. Dashboard (Power BI)**

An interactive dashboard with KPI cards, charts, and filters for subscription status, gender, category, and shipping type.

![Customer Behavior Dashboard](dashboard/dashboard.png)

## Key Insights

- Male customers generated about 68% of total revenue.
- Subscribers are 27% of customers, but their average spend ($59.49) is almost the same as non-subscribers ($59.87).
- About 80% of customers fall in the Loyal segment (3,116 of 3,900).
- Express shipping customers spend about $2 more per purchase than Standard shipping customers.
- Hats have the highest discount rate (50% of purchases), followed by Sneakers and Coats.
- Young Adults bring the highest revenue, but the gap between age groups is small.
- Most repeat buyers (2,518 of 3,476) are not subscribed, so there is room to convert them.

## Business Recommendations

- Promote exclusive benefits to increase subscriptions
- Reward repeat buyers with a loyalty program
- Review the discount policy to balance sales and margin
- Highlight top-rated and best-selling products in campaigns
- Target high-revenue age groups and express-shipping users

## How to Run

1. Install the libraries: `pip install pandas sqlalchemy pymysql`
2. Create the database in MySQL 8.0 or later: `CREATE DATABASE customer_behavior;`
3. Run `notebooks/analysis.ipynb`. Enter your own MySQL username and password in the connection step.
4. Run the queries in `sql/queries.sql` in MySQL Workbench.
5. Open `dashboard/customer_behavior.pbix` in Power BI Desktop.

## Author

**Dharanidevan**
BCA graduate | Data Analytics | Python, SQL, Power BI
LinkedIn: add your link here
