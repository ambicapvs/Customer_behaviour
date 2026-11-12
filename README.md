# 🛒 Customer Shopping Behavior Analysis

An end-to-end data analytics project that explores customer purchase behavior using **Python** for exploratory data analysis, **MySQL** for querying, and **Power BI** for interactive dashboards.

---

## 📌 Project Overview

The goal of this project is to understand how customers shop: who buys what, how much they spend, and which factors influence their purchases. The insights can help businesses improve marketing, product strategy, and customer retention.

**Workflow:**

```
Raw Data (CSV) ──► Python (Cleaning & EDA) ──► MySQL (Storage & SQL Analysis) ──► Power BI (Dashboard)
```

---

## 🧰 Tech Stack

| Tool | Purpose |
|------|---------|
| **Python** (pandas) | Data cleaning and exploratory data analysis |
| **SQLAlchemy + PyMySQL** | Loading the cleaned data into MySQL |
| **MySQL** | Querying and answering business questions |
| **Power BI** | Interactive dashboard and visual reporting |
| **Jupyter Notebook** | Development environment |

---

## 📂 Repository Structure

```
customer-shopping-behavior-analysis/
│
├── data/
│   └── customer_data.csv            # Raw dataset
│
├── notebooks/
│   └── customer_eda.ipynb           # Data cleaning, EDA & MySQL load
│
├── sql/
│   └── customer_analysis.sql        # SQL queries for business questions
│
├── dashboard/
│   ├── customer_dashboard.pbix      # Power BI dashboard file
│   └── dashboard_preview.png        # Screenshot of the dashboard
│
└── README.md
```

> ✏️ Update the file names above to match your repository.

---

## 📊 Dataset

- **Source:** [Add dataset source / link here]
- **Rows:** [number of rows]
- **Columns:** [number of columns]
- **Key fields:** [e.g. Customer ID, Age, Gender, Category, Purchase Amount, Location, Season, Payment Method, Review Rating, Subscription Status]

---

## 🐍 Step 1: Data Cleaning & EDA (Python)

Performed in Jupyter Notebook using pandas, Matplotlib, and Seaborn:

- Checked data types, missing values, and duplicates
- Handled missing values and standardized column names
- Created new features (e.g. age groups) for better analysis
- Explored distributions of age, spending, and ratings
- Analyzed purchase patterns by category, gender, season, and location

The cleaned data was then loaded into MySQL using SQLAlchemy:

```python
from sqlalchemy import create_engine, text
import pandas as pd

engine = create_engine("mysql+pymysql://<user>:<password>@localhost:3306/customer_behavior")

with engine.begin() as conn:
    df.to_sql("customer", conn, if_exists="replace", index=False)
```

---

## 🗄️ Step 2: SQL Analysis (MySQL)

SQL queries were written to answer key business questions, such as:

1. What is the total revenue by gender?
2. Which product categories generate the most revenue?
3. Who are the top customers by total spend?
4. How do subscribers compare to non-subscribers in spending?
5. Which payment methods are most popular?
6. How does spending vary across seasons and locations?
7. Which age groups contribute the most revenue?

Example query:

```sql
SELECT category,
       COUNT(*) AS total_orders,
       ROUND(SUM(purchase_amount), 2) AS total_revenue
FROM customer
GROUP BY category
ORDER BY total_revenue DESC;
```

All queries are available in [`sql/customer_analysis.sql`](sql/customer_analysis.sql).

---

## 📈 Step 3: Power BI Dashboard

An interactive dashboard was built in Power BI to present the findings visually.

**Dashboard features:**

- KPI cards: total customers, total revenue, average purchase amount, average rating
- Revenue and sales by category
- Customer breakdown by gender and age group
- Subscription status analysis
- Interactive slicers for filtering by gender, category, season, and more

![Dashboard Preview](dashboard/dashboard_preview.png)

---

## 💡 Key Insights

> ✏️ Replace these with your actual findings.

- [Insight 1, e.g. which category brings in the most revenue]
- [Insight 2, e.g. which age group or gender spends the most]
- [Insight 3, e.g. how subscribers' spending compares to non-subscribers]
- [Insight 4, e.g. seasonal trends in purchases]

---

## ✅ Recommendations

> ✏️ Replace these with recommendations based on your insights.

- [Recommendation 1]
- [Recommendation 2]
- [Recommendation 3]

---

## 🚀 How to Run This Project

1. **Clone the repository**
   ```bash
   git clone https://github.com/<your-username>/customer-shopping-behavior-analysis.git
   cd customer-shopping-behavior-analysis
   ```

2. **Install dependencies**
   ```bash
   pip install pandas numpy matplotlib seaborn sqlalchemy pymysql jupyter
   ```

3. **Set up MySQL**
   ```sql
   CREATE DATABASE customer_behavior;
   ```

4. **Run the notebook** in `notebooks/` to clean the data and load it into MySQL (update your MySQL username and password first).

5. **Run the SQL queries** in `sql/customer_analysis.sql` using MySQL Workbench or any SQL client.

6. **Open the dashboard** file `dashboard/customer_dashboard.pbix` in Power BI Desktop.

---

## 👤 Author

**[Your Name]**
- LinkedIn: [your-linkedin-url]
- GitHub: [your-github-url]
- Email: [your-email]

---

⭐ If you found this project helpful, consider giving it a star!
