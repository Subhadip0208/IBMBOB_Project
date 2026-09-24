# 🛒 Indian E-Commerce Sales & Customer Behavior Analytics

**Author:** Subhadip Dutta  
**File:** `Subhadip Dutta_Indian E-Commerce Sales & Customer Behavior Analytics.ipynb`

---

## 📋 Project Description

This project performs a comprehensive end-to-end data analytics study on **Indian E-Commerce Customer Behavior & Purchase** data.  
The dataset contains **25,000 customer sessions** spanning devices, marketing channels, product categories, payment methods, discounts, cart behavior, and customer ratings — covering the full year 2024.

The project covers:

| Area | Details |
|---|---|
| **Data Cleaning** | Date parsing, categorical decoding, missing-value audit |
| **Feature Engineering** | Derived features: total spend, has_discount, time on site in minutes |
| **Exploratory Data Analysis** | Distributions, correlations, outlier detection |
| **Customer Behavior Analysis** | Device type, new vs returning, session duration |
| **Sales & Revenue Analysis** | Monthly trends, seasonal patterns, day-of-week |
| **Product & Category Analysis** | Revenue, conversion rate, price-revenue scatter |
| **Marketing Channel Analysis** | Sessions, revenue, conversion, cart abandonment per channel |
| **Cart Abandonment Analysis** | Discount impact, abandonment patterns |
| **Payment Method Analysis** | Sessions and revenue by payment method |
| **Rating & Review Analysis** | Impact of customer ratings on revenue and conversion |
| **Geographic Analysis** | Top locations by revenue and session volume |
| **Interactive Dashboard** | KPI cards + 6-panel Plotly dashboard |
| **Machine Learning** | Purchase prediction using Logistic Regression, Random Forest, Gradient Boosting |

---

## 📂 Dataset

| Property | Value |
|---|---|
| **File** | `Ecommerce.csv` |
| **Rows** | 25,000 |
| **Columns** | 29 |
| **Source** | Indian E-Commerce Customer Behavior & Purchase (Kaggle) |
| **Link** | [https://www.kaggle.com/datasets/](https://www.kaggle.com/datasets/kundanbedmutha/indian-e-commerce-customer-behavior-and-purchase/) *(refer to dataset folder)* |

### Column Reference

| Column | Description |
|---|---|
| `customer_id` | Unique customer identifier |
| `session_id` | Unique session identifier |
| `visit_date` | Date of the visit (DD-MM-YYYY) |
| `device_type` | 0=Desktop, 1=Mobile, 2=Tablet |
| `user_type` | 0=New, 1=Returning |
| `marketing_channel` | 0=Organic, 1=Email, 2=Social Media, 3=Referral, 4=Paid Search, 5=Direct |
| `product_id` | Unique product identifier |
| `product_category` | 0=Electronics, 1=Fashion, 2=Home & Kitchen, 3=Sports, 4=Books, 5=Beauty, 6=Toys, 7=Grocery |
| `unit_price` | Product unit price (₹) |
| `quantity` | Units purchased/viewed |
| `discount_percent` | Discount applied (%) |
| `discount_amount` | Monetary discount value (₹) |
| `revenue` | Actual revenue generated (₹) |
| `pages_viewed` | Pages browsed in session |
| `time_on_site_sec` | Time spent on site (seconds) |
| `added_to_cart` | 1 if item added to cart |
| `purchased` | **Target:** 1 if purchased |
| `cart_abandoned` | 1 if cart was abandoned |
| `rating` | Product rating (1–5) |
| `review_text` | Review text (encoded) |
| `review_helpful_votes` | Helpful votes count |
| `payment_method` | 0=UPI, 1=Credit Card, 2=Debit Card, 3=Net Banking, 4=COD, 5=Wallet |
| `visit_day` | Day of month |
| `visit_month` | Month number |
| `visit_weekday` | 0=Monday … 6=Sunday |
| `visit_season` | 0=Winter, 1=Spring, 2=Summer, 3=Autumn |
| `session_duration_bucket` | Very Short / Short / Long / Very Long |
| `revenue_normalized` | Normalized revenue value |
| `location` | Location ID |

---

## 🛠 Technologies Used

### Notebook (original)

| Technology | Purpose |
|---|---|
| **Python 3.10+** | Core language |
| **Pandas** | Data loading, cleaning, aggregation |
| **NumPy** | Numerical operations |
| **Matplotlib** | Static charts and plots |
| **Seaborn** | Statistical visualisations |
| **Plotly** | Interactive charts and dashboard |
| **Scikit-learn** | Machine learning (Logistic Regression, Random Forest, Gradient Boosting) |
| **Jupyter Notebook** | Interactive development environment |

### Web App (backend + frontend)

| Technology | Layer | Purpose |
|---|---|---|
| **Flask** | Backend | REST API — loads CSV, runs analytics & ML, serves JSON endpoints |
| **Flask-CORS** | Backend | Allows Dash frontend (different port) to call Flask |
| **Plotly Dash** | Frontend | Full interactive dashboard — 100% Python, no HTML/JS needed |

---

## 🏗 Project Structure

```
Indian_E-Commerce_Customer_Behavior_&_Purchase_project/
├── Ecommerce.csv                          ← dataset
├── backend/
│   └── app.py                             ← Flask REST API (port 5000)
├── frontend/
│   └── dashboard.py                       ← Plotly Dash UI  (port 8050)
├── requirements.txt                       ← notebook dependencies
├── requirements_web.txt                   ← web app dependencies (Flask + Dash)
├── Subhadip Dutta_...Analytics.ipynb      ← full analysis notebook
└── README.md
```

---

## ⚙️ Setup & Run Instructions

### 1. Prerequisites

- Python **3.10 or higher**
- pip

### 2. Install Dependencies

**For the notebook only:**
```bash
pip install -r requirements.txt
```

**For the web app (backend + frontend):**
```bash
pip install -r requirements_web.txt
```

### 3a. Run the Jupyter Notebook

```bash
python -m notebook
```
Then open `Subhadip Dutta_Indian E-Commerce Sales & Customer Behavior Analytics.ipynb`
and select **Kernel → Restart & Run All**.

### 3b. Run the Web App (Flask backend + Dash frontend)

Open **two separate terminals** inside the project folder:

**Terminal 1 — start the Flask backend:**
```bash
python backend/app.py
```
> Runs at **http://127.0.0.1:5000** — trains ML models on startup (~10 s)

**Terminal 2 — start the Dash frontend:**
```bash
python frontend/dashboard.py
```
> Runs at **http://127.0.0.1:8050** — open this URL in your browser

The dashboard has **6 tabs:**

| Tab | Contents |
|---|---|
| 📊 Overview | KPI cards, monthly revenue, device & user breakdown |
| 📅 Sales & Time | Monthly trend, day-of-week, seasonal analysis |
| 🏷️ Products | Revenue by category, rating impact, top locations |
| 📣 Marketing | Channel performance, payment methods, cart abandonment |
| 👤 Customers | New vs returning, session duration, rating analysis |
| 🤖 Machine Learning | Model accuracy table, ROC-AUC comparison, feature importances |

---

## 📊 Key Results

| Metric | Value |
|---|---|
| Total Sessions | 25,000 |
| Target Variable | `purchased` (binary classification) |
| Best ML Model | Gradient Boosting / Random Forest |
| Primary Frontend | Plotly interactive dashboard |
| ML Metrics | Accuracy, ROC-AUC, Precision, Recall, F1 |

---

## 📁 Deliverables

| File | Description |
|---|---|
| `Subhadip Dutta_Indian E-Commerce Sales & Customer Behavior Analytics.ipynb` | Full project notebook |
| `requirements.txt` | Python dependency list |
| `Subhadip Dutta_Indian E-Commerce Sales & Customer Behavior Analytics.docx` | Detailed project report |
| `README.md` | This file |
| `Ecommerce.csv` | Source dataset |

---

## 👤 Author

**Subhadip Dutta**  
Indian E-Commerce Sales & Customer Behavior Analytics Project

---

*Built with Python · Pandas · Matplotlib · Seaborn · Plotly · Scikit-learn*
