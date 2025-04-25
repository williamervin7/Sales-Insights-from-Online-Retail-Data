# 📊 E-Commerce Data Analysis

This project analyzes the UK-based online retail dataset from 2010-2011. The goal is to extract business insights by identifying top customers, popular products, revenue distribution, and sales trends over time.

---

## 📦 Dataset

- **Source**: [Online Retail Dataset](https://www.kaggle.com/datasets/hellbuoy/online-retail-customer-clustering)
- **Records**: Transactions from December 2010 to December 2011
- **Fields**: `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, `Country`

---

## 🔧 Preprocessing Steps

- Converted `InvoiceDate` to datetime format.
- Removed missing `CustomerID` entries.
- Filtered out transactions with non-positive `UnitPrice`.
- Created `TotalPrice` = `Quantity` × `UnitPrice`.

---

## 📈 Key Insights

### 1. Top Customers

- Top 10 customers contributed **~17.26%** of total revenue.
- Total unique customers: **4,338**
- Cumulative revenue chart showed ~80% of sales came from top ~900 customers.

### 2. Monthly Sales Trends

- Set `InvoiceDate` as index.
- Resampled monthly using `resample('ME')` to capture total monthly sales.
- Plotted monthly sales to visualize business performance over time.

### 3. Popular Products

- Top products in Oct–Nov 2011 identified by `TotalPrice`.
- Bar chart visualized top 10 product sales during this promotional period.

### 4. Quantity vs Revenue

- Compared top 10 products by **Quantity Sold** vs **Total Revenue**.
- Created grouped bar chart for easy side-by-side comparison.

### 5. Price Distribution

- Filtered `TotalPrice` values below the 80th percentile using `scipy.stats.norm`.
- Visualized price distribution with histogram.

---

## 📌 Tools Used

- **Pandas**: Data manipulation
- **Matplotlib / Seaborn**: Visualizations
- **NumPy / SciPy**: Statistical filtering
- **Jupyter Notebook**: Interactive analysis

---

