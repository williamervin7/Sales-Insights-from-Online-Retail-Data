# 🚀 E-Commerce Data Analysis and Insights

This multi-notebook project provides an in-depth analysis of a UK-based online retail dataset (2010-2011). Beyond exploratory data analysis, it delves into **statistical hypothesis testing** to uncover actionable business insights regarding customer behavior, revenue distribution, and sales trends. The project is designed with modularity, demonstrating various stages of a data science workflow.

---

## 📚 Project Structure

This project is organized into several Jupyter Notebooks, each focusing on a distinct phase of the data analysis and modeling pipeline:

1.  **`1_EDA_and_Feature_Engineering.ipynb`**: Focuses on initial data understanding, cleaning, and creating new features.
2.  **`2_Statistical_Analysis_and_Hypothesis_Testing.ipynb`**: Conducts rigorous statistical tests to validate observations and uncover significant differences in key business metrics.
3.  **`3_Data_Pipeline_and_Preparation.ipynb`**: (Future Notebook) Details the construction of a robust data pipeline for preprocessing and feature engineering.
4.  **`4_Customer_Segmentation_and_Modeling.ipynb`**: (Future Notebook) Explores machine learning models for customer segmentation or predictive analytics.

---

## 📦 Dataset

-   **Source**: [Online Retail Dataset](https://www.kaggle.com/datasets/hellbuoy/online-retail-customer-clustering) (Kaggle)
-   **Records**: Approximately 541,909 transactions from December 2010 to December 2011.
-   **Key Fields**: `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, `Country`.

---

## 🛠️ Data Preprocessing & Feature Engineering (from `1_EDA_and_Feature_Engineering.ipynb`)

Initial data preparation and creation of new analytical features:

-   Converted `InvoiceDate` to datetime format.
-   Handled missing `CustomerID` entries.
-   Filtered out invalid transactions (e.g., non-positive `Quantity` or `UnitPrice`).
-   Calculated `TotalPrice` (`Quantity` × `UnitPrice`) for each transaction.
-   Engineered temporal features (`Weektype` - Weekend/Weekday) and customer-level aggregates (e.g., `Purchase Frequency`, `Total Revenue per Customer`).

---

## 📈 Key Insights & Statistical Findings (from `2_Statistical_Analysis_and_Hypothesis_Testing.ipynb`)

This notebook validates initial observations and explores deeper relationships using rigorous statistical methods.

### 1. Revenue Distribution & Customer Segmentation

-   Analyzed overall revenue distribution, identifying heavy right-skewness.
-   **Insight**: Applied **log transformation** to normalize revenue data for robust statistical analysis.
-   **Statistical Tests**:
    * **Hypothesis: Weekend vs. Weekday Revenue**: Investigated if average transaction revenue differs between weekends and weekdays.
        * **Methodology**: Independent two-sample t-test (Student's or **Welch's, based on Levene's Test for equal variances**).
        * **Key Finding**: [Briefly state your finding here, e.g., "Found a statistically significant (p < 0.001) but practically small (Cohen's d = -0.21) difference, with weekday transactions having slightly higher average revenue."].
    * **Hypothesis: Top Customers vs. Other Customers (Revenue)**: Compared the average transaction revenue of top-tier customers against others.
        * **Methodology**: Independent two-sample t-test (with variance check).
        * **Key Finding**: [Briefly state your finding here, e.g., "Confirmed Top Customers have significantly higher average transaction revenue (p < 0.001) with a substantial effect size (Cohen's d = X.XX)."].
    * **Hypothesis: Top Customers vs. Other Customers (Purchase Frequency)**: Assessed if top customers have higher purchase frequencies.
        * **Methodology**: Independent two-sample t-test (with variance check).
        * **Key Finding**: [Briefly state your finding here, e.g., "Identified a highly significant difference (p < 0.001) and large effect (Cohen's d = X.XX), indicating Top Customers purchase much more frequently."].

### 2. Revenue by Country (Planned)

-   **(Future Insight)** Will compare average revenue across different countries to identify regional performance variations.
-   **(Future Methodology)** Will utilize **ANOVA** (Analysis of Variance) or **Kruskal-Wallis H-test** (if ANOVA assumptions are violated) to compare means across multiple groups.

### 3. Revenue Distribution via Bootstrapping (Planned)

-   **(Future Insight)** Will explore the sampling distribution of key revenue metrics to understand their variability and construct non-parametric confidence intervals.
-   **(Future Methodology)** Will apply **Bootstrapping** to simulate sampling distributions and derive robust confidence intervals without strong distributional assumptions.

---

## 📈 Visualizations Used

A combination of plots to illustrate data distributions and test results:

-   Histograms (for distribution visualization, including log-transformed data)
-   Box Plots (for comparing group distributions and identifying outliers)
-   (Add others as you use them: Scatter plots, bar charts for product analysis, etc.)

---

## 📌 Tools & Libraries

-   **Python**: Primary programming language
-   **Pandas**: Data manipulation and analysis
-   **NumPy**: Numerical operations
-   **SciPy**: Statistical tests (`ttest_ind`, `levene`, `shapiro`, `kruskal`)
-   **Statsmodels**: Advanced statistical modeling (`ols`, `anova_lm`)
-   **Matplotlib / Seaborn**: Data visualization
-   **Jupyter Notebook / Google Colab**: Interactive development environment

---

## 🚀 Future Enhancements

-   Deep dive into customer segmentation (e.g., RFM analysis, clustering).
-   Predictive modeling for customer lifetime value (CLV) or churn.
-   Building a robust, automated data preprocessing pipeline.
-   Time series forecasting for sales trends.
