# 🛒 Django Marketplace Analytics — Advanced ORM Project

A lightweight **Django ORM learning project** designed to master **advanced database querying** without building a full-fledged app.

This project focuses entirely on **Django ORM concepts** such as annotations, aggregations, subqueries, window functions, and query optimizations — the exact topics asked in real interviews.

No frontend.  
No unnecessary features.  
Only **pure ORM mastery**.

---

# 📘 Project Goals

- Build a minimal marketplace backend with Products, Customers, Orders, and OrderItems.
- Learn **intermediate → advanced-level Django ORM** by implementing real analytics.
- Keep code clean using **QuerySets, Managers, and service layers**.
- Practice concepts used in production and interview questions.

---

# 🚀 Features & Learning Roadmap

Each feature corresponds to one ORM concept you’ll learn while building it.

---

## 🔵 PHASE 1 — Models & Basic ORM
**Learn:**
- Django models  
- One-to-many relationships  
- related_name  
- Basic ORM (filter, exclude, order_by)

**Tasks:**
- Create models: `Customer`, `Category`, `Product`, `Order`, `OrderItem`
- Insert sample data via Django shell
- Practice simple queries:
  - All orders of a customer
  - All products in a category
  - Filter products by price

---

## 🟠 PHASE 2 — Aggregations & Annotations
**Learn:**
- `annotate`, `aggregate`
- `Sum`, `Avg`, `Count`, `Max`, `Min`
- Group-by style queries

**Tasks:**
- Calculate total revenue
- Total products sold
- Orders per customer
- Spending per customer

---

## 🟠 PHASE 3 — F Expressions (Database-Side Math)
**Learn:**
- Arithmetic using F expressions
- Updating values without fetching
- Race conditions and atomic updates

**Tasks:**
- Apply discount to products
- Increase prices in a category
- Compute `quantity * price` revenue

---

## 🟠 PHASE 4 — Q Expressions (Advanced Filtering)
**Learn:**
- OR, AND, NOT logic
- Combining multiple conditions

**Tasks:**
- Products with `price < 500 OR rating > 4`
- Premium customers who spent more than X
- Orders created last 30 days AND more than N items

---

## 🟣 PHASE 5 — Query Optimization
**Learn:**
- `select_related`
- `prefetch_related`
- N+1 query problem
- Using django-debug-toolbar

**Tasks:**
- Optimize fetching orders with customers
- Optimize products with categories
- Optimize order → items → product loading

---

## 🔴 PHASE 6 — Subqueries & OuterRef
**Learn:**
- Subquery()
- OuterRef()
- Exists()
- Correlated subqueries

**Tasks:**
- Last order date per customer
- Total quantity sold per product (via subquery)
- “Customers who bought X also bought Y”

---

## 🔴 PHASE 7 — Window Functions (Optional / PostgreSQL)
**Learn:**
- DenseRank(), Rank()
- Partitioning
- Cumulative sums

**Tasks:**
- Rank customers by spending
- Rank products by total sales
- Monthly cumulative revenue

---

## 🔴 PHASE 8 — Custom QuerySets & Managers
**Learn:**
- Writing reusable ORM code
- Chaining QuerySets
- Creating domain-specific methods

**Tasks:**
- `Product.objects.active()`
- `Product.objects.with_sales()`
- `Customer.objects.top_spenders()`

---

## 🔴 PHASE 9 — Build the Analytics Layer
**Learn:**
- Designing “service” functions
- Keeping ORM queries separate from views
- Clean backend architecture

**Tasks:**
Create functions like:
- `get_top_selling_products()`
- `get_customer_lifetime_value()`
- `get_monthly_revenue()`
- `get_also_bought_products()`
- `get_ranked_customers()`

---


---

# 🛠️ Tech Stack

| Component | Tool |
|----------|------|
| Language | Python 3.x |
| Framework | Django |
| Database | SQLite / PostgreSQL (recommended for window functions) |
| Toolkit | Django ORM, Django Debug Toolbar |

---

# ▶️ How to Run

```bash
git clone <repo-url>
cd marketplace_analytics

# create virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

pip install -r requirements.txt

python manage.py migrate
python manage.py seed_data   # optional test data

python manage.py runserver
