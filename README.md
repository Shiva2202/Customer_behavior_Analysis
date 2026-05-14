# 🛍️ Customer Shopping Behavior Analysis

> A full-cycle data analytics project analyzing 3,900 retail transactions to uncover spending patterns, customer segments, and product preferences — supporting strategic business decisions.

---

## 📌 Overview

This project walks through a complete end-to-end data analytics workflow: from raw data ingestion and cleaning in Python, to structured querying in SQL, to visual storytelling in Power BI and a polished presentation in Gamma. The goal is to extract actionable insights on customer behavior — who spends the most, which products drive revenue, and how discounts and subscriptions affect purchasing patterns.

---

## 📂 Dataset

| Attribute | Details |
|---|---|
| Source | Retail transaction records |
| Rows | 3,900 purchases |
| Columns | 18 features |
| Missing Data | 37 values in `Review Rating` (imputed) |

**Key Features:**
- **Demographics** — Age, Gender, Location, Subscription Status
- **Purchase Details** — Item, Category, Purchase Amount (USD), Season, Size, Color
- **Behavior** — Discount Applied, Previous Purchases, Frequency, Review Rating, Shipping Type

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| **Python** (pandas) | Data loading, cleaning, EDA, feature engineering |
| **PostgreSQL** | SQL-based business analysis and querying |
| **Power BI** | Interactive dashboard and visual reporting |
| **Gamma** | Presentation slide deck |
| **Jupyter Notebook** | Development environment for Python analysis |

---

## 🔄 Project Steps

### 1. 🐍 Data Loading & Exploration (Python)
- Imported dataset using `pandas`
- Used `df.info()` and `.describe()` to understand structure and statistics
- Identified 37 missing values in the `Review Rating` column

### 2. 🧹 Data Cleaning
- Imputed missing `Review Rating` values using **category-level median**
- Renamed all columns to **snake_case** for consistency
- Verified redundancy between `discount_applied` and `promo_code_used` → dropped `promo_code_used`

### 3. ⚙️ Feature Engineering
- Created `age_group` column by binning customer ages into: Young Adult, Adult, Middle-aged, Senior
- Created `purchase_frequency_days` to quantify how often customers shop

### 4. 🗄️ Database Integration
- Connected Python script to **PostgreSQL** using `SQLAlchemy`
- Loaded cleaned DataFrame into the database for structured querying

### 5. 🔍 SQL Analysis (Business Questions Answered)

| # | Query | Key Finding |
|---|---|---|
| 1 | Revenue by Gender | Male: $157,890 vs Female: $75,191 |
| 2 | High-Spending Discount Users | 839 customers used discounts but spent above average |
| 3 | Top 5 Products by Rating | Gloves (3.86), Sandals (3.84), Boots (3.82) |
| 4 | Shipping Type vs. Spend | Express: $60.48 vs Standard: $58.46 |
| 5 | Subscribers vs. Non-Subscribers | Similar avg. spend (~$59.6), 73% are non-subscribers |
| 6 | Discount-Dependent Products | Hat (50%), Sneakers (49.66%), Coat (49.07%) |
| 7 | Customer Segmentation | Loyal: 3,116 · Returning: 701 · New: 83 |
| 8 | Top 3 Products per Category | Jewelry, Blouse, Sandals, Jacket lead their categories |
| 9 | Repeat Buyers & Subscriptions | 958 repeat buyers subscribed vs. 2,518 who did not |
| 10 | Revenue by Age Group | Young Adults top with $62,143 |

### 6. 📊 Power BI Dashboard
- Built an interactive dashboard with slicers for Subscription Status, Gender, Category, and Shipping Type
- Visuals include: donut chart (subscription split), bar charts (revenue/sales by category and age group), and KPI cards

### 7. 📑 Report & Presentation
- Written report documenting methodology, findings, and recommendations
- Slide deck built in **Gamma** covering dataset overview, key insights, and business actions

---

## 📊 Dashboard Preview

The Power BI dashboard presents:
- **KPI Cards** — 3.9K Customers | $59.76 Avg. Purchase | 3.75 Avg. Rating
- **Subscription split** — 27% Subscribers, 73% Non-Subscribers
- **Revenue & Sales** breakdowns by Category and Age Group
- **Interactive filters** — Subscription Status, Gender, Category, Shipping Type

---

## 📈 Key Results & Insights

- **Male customers** account for roughly **2× the revenue** of female customers
- **Young Adults** are the highest-revenue age group ($62,143)
- **80%+ of customers** are classified as Loyal (5+ purchases) — strong retention base
- **Subscription rate is low at 27%** despite repeat buyers showing willingness to engage
- **Hat, Sneakers, and Coat** are the most discount-dependent products (~50% discounted purchases)
- **Express shipping users** spend slightly more on average — a potential upsell signal

---

## 💡 Business Recommendations

1. **Boost Subscriptions** — Promote exclusive benefits to convert the 2,518 repeat non-subscribers
2. **Loyalty Programs** — Reward Returning customers to accelerate their move into the Loyal segment
3. **Review Discount Policy** — High discount dependency on items like Hat and Sneakers may be eroding margins
4. **Targeted Marketing** — Prioritize Young Adults and express-shipping users for premium campaigns
5. **Product Positioning** — Spotlight top-rated items (Gloves, Sandals, Boots) in featured placements

---

## ▶️ How to Run

### Prerequisites
```bash
pip install pandas sqlalchemy psycopg2 jupyter
```

### Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/customer-shopping-behavior-analysis.git
   cd customer-shopping-behavior-analysis
   ```

2. **Open the Jupyter Notebook**
   ```bash
   jupyter notebook Customer_Shopping_Behavior_Analysis.ipynb
   ```

3. **Run all cells** to load, clean, and engineer features from the dataset

4. **Set up PostgreSQL** and update the connection string in the notebook:
   ```python
   engine = create_engine("postgresql://username:password@localhost:5432/your_db")
   ```

5. **Run SQL queries** from the `sql/` folder in your PostgreSQL client (pgAdmin, DBeaver, etc.)

6. **Open the Power BI file** (`customer_behavior_dashboard.pbix`) in Power BI Desktop to explore the dashboard

---

## 📁 Project Structure

```
customer-shopping-behavior-analysis/
│
├── Customer_Shopping_Behavior_Analysis.ipynb   # Python EDA & cleaning notebook
├── customer_behavior_dashboard.pbix            # Power BI dashboard
├── Customer_Shopping_Behavior_Analysis.pdf     # Full project report
├── Customer-Shopping-Behavior-Analysis_ppt.pdf # Presentation slide deck
├── sql/                                        # SQL query files
│   └── business_queries.sql
├── data/                                       # Raw dataset (CSV)
│   └── shopping_behavior.csv
└── README.md
```

---



---

*Feel free to ⭐ this repository if you found it useful!*
