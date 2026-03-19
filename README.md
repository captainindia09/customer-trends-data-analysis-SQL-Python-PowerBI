# 🛍️ Customer Shopping Behavior Analysis: Data Strategy Portfolio

## 📌 Project Architecture
This repository demonstrates an end-to-end data engineering and analytics workflow. It transforms raw retail data into actionable business intelligence using a modern stack: **Python (Pandas) → SQL (PostgreSQL/MySQL) → Power BI**.

---

## 🚀 The Data Lifecycle

### 1. Data Ingestion & Exploratory Data Analysis (EDA)
The journey begins in the `Customer_Shopping_Behavior_Analysis.ipynb` notebook. I perform an initial audit of 3,900 customer records to understand the demographic distributions (Age, Gender) and purchasing habits (Category, Frequency).

### 2. Advanced Data Cleaning (Python)
I implemented a robust cleaning pipeline to ensure data integrity:
- **Missing Value Imputation**: Instead of dropping records, I used category-specific medians to fill in missing `Review Ratings`, preserving the statistical distribution.
- **Structural Standardization**: All columns were converted to `snake_case` for SQL compatibility and code readability.
- **Feature Engineering**:
  - **Age Segmentation**: Applied `pd.qcut` to create `age_group` categories (Young Adult, Adult, Middle-aged, Senior) for easier demographic analysis.
  - **Temporal Normalization**: Mapped textual purchase frequencies (e.g., "Fortnightly") to actual numeric days (e.g., `14`) to enable mathematical calculations on LTV (Lifetime Value).
- **Redundancy Removal**: Dropped duplicate indicators (like `promo_code_used` when `discount_applied` already covered the logic).

### 3. Database Integration (SQL)
The cleaned dataset is programmatically pushed to a SQL database. Using `SQLAlchemy` and `psycopg2`, the Python script creates a high-performance table (`customer`).
*   **Queries**: I use `customer_behavior_sql_queries.sql` to answer critical business questions:
    - Identifying the highest-spending loyal customers.
    - Calculating average ratings per product category.
    - Analyzing payment method preferences across different locations.

### 4. Interactive Visualization (Power BI)
The final stage connects the SQL database to `customer_behavior_dashboard.pbix`. 
- **KPI Tracking**: Real-time tracking of total revenue and average purchase amounts.
- **Behavioral Analysis**: Slicing the data by season, shipping type, and subscription status.
- **Actionable Insights**: Visualizing which locations are "hot" for specific clothing categories.

---

## 🛠️ Tech Stack & Requirements
- **Language**: Python 3.12+
- **Libraries**: Pandas, SQLAlchemy, Psycopg2, Matplotlib
- **Database**: PostgreSQL / MySQL / SQL Server
- **BI Tool**: Microsoft Power BI Desktop

---

## 📂 Repository Breakdown
- `Customer_Shopping_Behavior_Analysis.ipynb`: The core analytical engine (Python).
- `customer_behavior_sql_queries.sql`: Advanced SQL queries for deep-dives.
- `customer_behavior_dashboard.pbix`: The visual storytelling layer.
- `customer_shopping_behavior.csv`: The raw source data.
- `Business Problem Document.pdf`: Context and objectives for the analysis.

---

## 👨‍💻 Developed by
**Captain India**  
*Data Strategist & Analytics Engineer*  
[Your LinkeIn/Portfolio Link here]
