# Customer Shopping Analysis

This project is an end-to-end **Customer Shopping Analysis** transforming raw retail data into **actionable business insights** through Python-based data cleaning, SQL analytics, and an interactive Power BI dashboard.

---

## 📊 Dashboard Showcase

The final deliverable is an **interactive Power BI dashboard** that allows business teams to:

* Filter insights by **season**, **location**, and **customer type**
* Track revenue trends and shopping behavior
* Identify high-value segments for marketing

> Designed for **data-driven decisions** and business storytelling.

---

## 🧩 Tech Stack

| Stage         | Technology      | Purpose                           |
| ------------- | --------------- | --------------------------------- |
| Data Cleaning | Python (Pandas) | Transform & enrich raw data       |
| Database      | PostgreSQL      | Scalable data storage & querying  |
| Connector     | SQLAlchemy      | Seamless Python ➝ SQL integration |
| Visualization | Power BI        | Interactive dashboards & insights |

---

## 🔄 Project Workflow

This project follows a **3-phase data pipeline**:

### ✅ 1️⃣ Data Cleaning & Preparation (Python)

Raw dataset: `customer_shopping_behavior.csv` (3,900 rows)

Key transformations performed:

* 🧹 **Missing Value Imputation**

  * 37 missing `review_rating` values filled using **median rating per product category**
* 🏷️ **Column Standardization**

  * Converted headers to `snake_case` for SQL compatibility
* 🧠 **Feature Engineering**

  * `age_group` via statistical quartiles → Young Adult / Adult / Middle-aged / Senior
  * `purchase_frequency_days` converted into numeric values (e.g., Weekly → 7)
* 🚫 **Redundant Column Removal**

  * Dropped duplicate column `promo_code_used`

➡️ Final cleaned dataset loaded into PostgreSQL table: **`customer`**

---

### 📈 2️⃣ Data Analysis (SQL)

10 business-driven queries executed to uncover trends, revenue patterns & customer behavior.

### ✅ Q1. Revenue by Gender  
```sql
SELECT gender, SUM(purchase_amount) AS revenue
FROM customer
GROUP BY gender;
```
<img width="240" height="114" alt="Q1 (Revenue by Gender)" src="https://github.com/user-attachments/assets/b180e558-f2fa-47fa-ad43-e11b6658882e" />

### 📊 3️⃣ Data Visualization (Power BI)

Live connection to PostgreSQL database to ensure **real-time, refreshable insights**.

---

## 🔍 Key Insights & Business Questions Answered

| Question                     | Insight                          | Value Delivered                      |
| ---------------------------- | -------------------------------- | ------------------------------------ |
| Revenue by Gender            | Men spent far more               | Revenue focus on male audience       |
| High-Spending Discount Users | 839 customers identified         | Target for profitable promo strategy |
| Top Rated Products           | Gloves, Sandals, Boots...        | Inventory optimization               |
| Shipping Type Impact         | Spend nearly identical           | Express shipping not revenue driver  |
| Subscriber Value             | Non-subscribers = $170k+ revenue | Big conversion opportunity           |
| Discount-Driven Products     | Hat & Sneakers most influenced   | Price sensitivity segmentation       |
| Customer Segmentation        | Loyal: 3,116                     | Retention program potential          |
| Top Products by Category     | "Hero" products identified       | Perfect for marketing campaigns      |
| Repeat Buyers & Subscription | 2,518 not subscribed             | Upsell campaign focus                |
| Revenue by Age Group         | Young Adult leads                | Demographic targeting                |

---

## 🎯 Business Recommendations

Strategic actions based on findings:

✅ Convert **2,518 loyal non-subscribers** → membership program, special onboarding campaigns

✅ Implement **loyalty rewards** for 3,100+ regular buyers to boost retention

✅ Optimize discount strategy

* Promote price-sensitive items (Hats, Sneakers)
* Protect margins on high-demand products

✅ Marketing campaign focus

* "Young Adult" & "Middle-aged" segments → highest spending
* Feature **top performing products** in ads

---

## 🚀 How to Run This Project

### ✅ Prerequisites

* Python 3.x
* PostgreSQL installed and running
* Power BI Desktop
* Required Python libraries:

  ```bash
  pip install pandas sqlalchemy psycopg2-binary
  ```

### ✅ Setup & Execution

1️⃣ Create a PostgreSQL database → `customer_behaviour`
2️⃣ Update credentials in `main.py`
3️⃣ Place `customer_shopping_behavior.csv` in the same folder
4️⃣ Run the pipeline:

```bash
python main.py
```

✅ Automatically loads cleaned data into PostgreSQL

### ✅ SQL Analysis

Run queries from `analysis.sql` in pgAdmin or DBeaver

### ✅ Dashboard

Open: `customer_behaviour.pbix` in Power BI Desktop

* Update connection path when prompted

---

## 📁 Project Structure

```
├── main.py                # Python data cleaning + PostgreSQL loader
├── analysis.sql           # SQL business insights
├── customer_behaviour.pbix # Power BI dashboard file
├── customer_shopping_behavior.csv # Raw dataset
└── README.md              # Project documentation
```

---

## 🏁 Final Outcome

✅ A complete retail analytics system
✅ SQL-powered decision intelligence
✅ Dashboard-based story for stakeholders

> This project showcases **data engineering + analytics + visualization** expertise for real-world business value.

---

### ⭐ Contributions & Feedback!

If you'd like to enhance or explore this project further — feel free to contribute or reach out!
