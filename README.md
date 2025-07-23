# 📊 E-Commerce Data Analysis

This project analyzes the UK-based online retail dataset from 2010–2011. The goal is to extract business insights by identifying top customers, popular products, revenue distribution, and sales trends over time. Statistical testing and exploratory analysis are broken out into separate notebooks for clarity.

---

## 📦 Dataset

- **Source**: [Online Retail Dataset](https://www.kaggle.com/datasets/hellbuoy/online-retail-customer-clustering)  
- **Records**: Transactions from December 2010 to December 2011  
- **Fields**: `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, `Country`  

---

## 📂 Project Structure

- `eda_notebook.ipynb`: Exploratory data analysis  
- `stats_notebook.ipynb`: Statistical analysis  
- *(More notebooks may be added — e.g., modeling, pipelines, etc.)*

---

## 🔧 Preprocessing Steps

- Converted `InvoiceDate` to datetime format  
- Removed missing `CustomerID` entries  
- Filtered out transactions with non-positive `UnitPrice`  
- Created `TotalPrice` = `Quantity × UnitPrice`  

---

## 📈 EDA Highlights

### 1. Top Customers
- Top 10 customers contributed **~17.26%** of total revenue  
- Total unique customers: **4,338**  
- ~80% of revenue came from ~900 customers  

### 2. Monthly Sales Trends
- Resampled monthly using `resample('ME')` to visualize business performance  
- Seasonal dips and spikes aligned with holidays and end-of-year activity  

### 3. Popular Products
- Identified top 10 products by `TotalPrice` in Oct–Nov 2011  
- Visualized high-performing products during promotional periods  

### 4. Quantity vs Revenue
- Compared top 10 products by **Quantity Sold** vs **Revenue Generated**  
- Found discrepancies: some items sold often but brought in less revenue  

### 5. Price Distribution
- Focused on `TotalPrice` values below the 80th percentile  
- Histogram used to visualize overall spending patterns  

---

## 📊 Statistical Analysis Highlights

Key tests and insights from `stats_notebook.ipynb`:

- **Normality Testing**  
  - Used Shapiro-Wilk test on `Revenue`  
  - Result: Data is **not normally distributed** → non-parametric tests preferred  

- **Country Revenue Comparison**  
  - Used Kruskal-Wallis H test to compare revenue across top countries  
  - Found **statistically significant differences** in revenue distributions  

- **Product Popularity Tests**  
  - Compared purchase patterns of top vs low-performing products  
  - Significant variation in quantity sold vs revenue earned per item  

- **Customer Segmentation Basis**  
  - Used descriptive stats (mean, median, IQR) to identify potential customer groups  
  - Laid groundwork for clustering or segmentation models (planned for later phase)  

---

## 🛠 Tools Used

- **Pandas**: Data manipulation  
- **Matplotlib / Seaborn**: Visualizations  
- **NumPy / SciPy**: Statistical tests  
- **Jupyter Notebook**: Interactive analysis  

---

## ✅ Next Steps

- Break out modeling into a dedicated notebook  
- Build pipeline for customer segmentation  
- Introduce machine learning to predict purchasing behavior  

