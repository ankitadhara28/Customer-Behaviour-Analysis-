# 🛍️ Retail Customer Behavior Analysis using Python, PostgreSQL & Power BI

A data analytics project focused on understanding customer purchasing behavior, spending patterns, and product preferences using Python, PostgreSQL, and Power BI.

---

## 📌 Business Problem

Retail businesses generate large amounts of customer transaction data but often struggle to convert it into actionable insights. Understanding how demographics, subscriptions, discounts, and purchasing habits influence revenue can help businesses improve customer retention, optimize marketing strategies, and increase profitability.

This project analyzes customer shopping behavior to uncover key trends and provide data-driven business recommendations.

---

## 🎯 Project Objectives

* Analyze customer spending patterns across demographics
* Identify top-performing products and categories
* Measure the impact of discounts and subscriptions
* Segment customers based on purchasing behavior
* Build an interactive dashboard for business stakeholders
* Generate actionable recommendations to improve revenue and customer engagement

---

## 📂 Dataset Summary

| Feature        | Details                      |
| -------------- | ---------------------------- |
| Total Records  | 3,900                        |
| Total Columns  | 18                           |
| Missing Values | 37 values in `Review Rating` |

### Key Features

#### Customer Demographics

* Age
* Gender
* Location
* Subscription Status

#### Purchase Information

* Item Purchased
* Category
* Purchase Amount
* Season
* Size
* Color

#### Customer Behavior

* Discount Applied
* Promo Code Used
* Previous Purchases
* Purchase Frequency
* Review Rating
* Shipping Type

---

## 🛠️ Tech Stack

| Tool       | Purpose                   |
| ---------- | ------------------------- |
| Python     | Data Cleaning & EDA       |
| Pandas     | Data Manipulation         |
| PostgreSQL | SQL Analysis              |
| Power BI   | Dashboard & Visualization |

---

## 🔍 Methodology

### 1️⃣ Exploratory Data Analysis (Python)

#### Data Exploration

* Loaded dataset using Pandas
* Examined structure using `df.info()`
* Generated descriptive statistics using `df.describe()`

#### Data Cleaning

* Identified missing values in `review_rating`
* Imputed missing ratings using median values grouped by product category
* Standardized column names into `snake_case`

#### Feature Engineering

* Created `age_group` categories
* Derived customer behavior metrics
* Performed consistency checks on business attributes

#### Data Validation

* Found `discount_applied` and `promo_code_used` represented identical information
* Removed redundant column to improve data quality

#### Database Integration

* Loaded cleaned dataset into PostgreSQL for advanced SQL analysis

---

### 2️⃣ SQL Analysis (PostgreSQL)

Business questions were answered using SQL queries involving:

* Aggregations
* Grouping & Filtering
* Conditional Logic
* Window Functions
* Ranking Functions
* Common Table Expressions (CTEs)

#### Analysis Performed

| #  | Analysis                                 |
| -- | ---------------------------------------- |
| 1  | Revenue by Gender                        |
| 2  | High-Spending Discount Users             |
| 3  | Top 5 Products by Rating                 |
| 4  | Shipping Type Comparison                 |
| 5  | Subscribers vs Non-Subscribers           |
| 6  | Discount-Dependent Products              |
| 7  | Customer Segmentation                    |
| 8  | Top 3 Products per Category              |
| 9  | Repeat Buyers & Subscription Correlation |
| 10 | Revenue by Age Group                     |

#### Example SQL Query

```sql
SELECT gender,
       SUM(purchase_amount) AS total_revenue
FROM shopping_behavior
GROUP BY gender
ORDER BY total_revenue DESC;
```

---

### 3️⃣ Dashboard Development (Power BI)

An interactive dashboard was created to enable business users to explore customer behavior dynamically.

#### Dashboard Filters

* Subscription Status
* Gender
* Category
* Shipping Type

#### Dashboard KPIs

* Total Customers
* Average Purchase Amount
* Average Review Rating
* Customer Subscription Distribution
* Revenue by Category
* Revenue by Age Group
* Sales by Age Group

---

## 📊 Dashboard Preview

![Customer Behavior Dashboard](assets/dashboard.png)

---

## 📈 Key Insights

### Revenue by Gender

* Male customers generated approximately **$157,890**
* Female customers generated approximately **$75,191**
* Male customers contributed a significantly larger share of total revenue

### Top-Rated Products

| Product | Average Rating |
| ------- | -------------- |
| Gloves  | 3.86           |
| Sandals | 3.84           |
| Boots   | 3.82           |
| Hat     | 3.80           |
| Skirt   | 3.78           |

### Shipping Type Analysis

* Express shipping customers spent slightly more on average
* Express: **$60.48**
* Standard: **$58.46**

### Subscription Analysis

* 73% of customers are non-subscribers
* 27% are subscribers
* Non-subscribers generated higher total revenue due to larger customer volume
* Average spending remains similar across both groups

### Discount Dependency

Products most frequently purchased with discounts:

1. Hat (50%)
2. Sneakers (49.66%)
3. Coat (49.07%)
4. Sweater (48.17%)
5. Pants (47.37%)

### Customer Segmentation

Segmentation based on previous purchase history:

* New Customers: 83
* Returning Customers: 701
* Loyal Customers: 3,116

### Revenue by Age Group

| Age Group   | Revenue |
| ----------- | ------- |
| Young Adult | $62,143 |
| Middle-aged | $59,197 |
| Adult       | $55,978 |
| Senior      | $55,763 |

---

## 📊 Dashboard Highlights

* Young Adult customers generate the highest revenue.
* Loyal customers dominate the customer base.
* Accessories contribute significantly to sales performance.
* Subscription status has minimal effect on average purchase value.
* Express shipping customers tend to spend slightly more than standard shipping users.

---

## 💡 Business Recommendations

### Increase Subscription Adoption

Introduce:

* Exclusive member discounts
* Loyalty rewards
* Early-access promotions

### Strengthen Loyalty Programs

Reward repeat customers through:

* Points systems
* Personalized offers
* Referral incentives

### Optimize Discount Strategy

Products with high discount dependency should be reviewed to:

* Protect profit margins
* Reduce excessive promotional reliance

### Promote High-Rated Products

Feature highly rated products in:

* Marketing campaigns
* Product recommendations
* Homepage placements

### Target High-Value Segments

Focus marketing efforts on:

* Young Adult customers
* Loyal customers
* Higher-spending shipping segments

---

## 🔮 Future Enhancements

* Customer Lifetime Value (CLV) Analysis
* RFM Segmentation
* Churn Prediction Modeling
* Purchase Forecasting
* Product Recommendation System
* Customer Retention Analytics

---

## 📁 Project Structure

```text
📦 customer-shopping-behavior-analysis
├── 📂 assets
│   └── dashboard.png
├── 📂 data
│   └── shopping_behavior.csv
├── 📂 notebooks
│   └── eda_cleaning.ipynb
├── 📂 sql
│   └── business_queries.sql
├── 📂 dashboard
│   └── customer_behavior.pbix
└── README.md
```

---

## 🚀 Getting Started

### Clone Repository

```bash
git clone https://github.com/your-username/customer-shopping-behavior-analysis.git
cd customer-shopping-behavior-analysis
```

### Install Dependencies

```bash
pip install pandas sqlalchemy psycopg2
```

### Run Notebook

```bash
jupyter notebook notebooks/eda_cleaning.ipynb
```

Ensure PostgreSQL is running and update the database connection string before executing the SQL integration steps.

---

## 📄 License

This project is licensed under the MIT License.
