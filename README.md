# Online Retail Data Analysis & Modeling

## Project Overview
This project is part of my journey back into Data Science after a short break. Using a real-world Online Retail dataset, I performed end-to-end data science tasks: from cleaning and exploratory analysis to statistical hypothesis testing and predictive modeling.  

The goal was to explore customer purchase behavior, uncover insights about sales and returns, and build a regression model to predict transaction amounts.  

---

## Objectives
- Clean and preprocess transactional retail data.  
- Perform **Exploratory Data Analysis (EDA)** to uncover trends and patterns.  
- Apply **probability and statistical tests** (t-test, ANOVA, chi-square) for hypothesis validation.  
- Engineer new features (time-based features, total sales, return indicators).  
- Train and evaluate a regression model to predict spending.  
- Present actionable insights for business decisions.  

---

## Dataset
- **Source:** [UCI Machine Learning Repository – Online Retail Dataset](https://archive.ics.uci.edu/ml/datasets/online+retail)  
- **Shape:** ~525k rows, 8 columns  
- **Columns:**  
  - `Invoice`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`,  
  - `Price`, `Customer ID`, `Country`  

---

## 🛠Process & Methods

### 1. Data Cleaning
- Handled missing values (`Description` had ~0.5% missing).  
- Removed invalid entries (negative quantities = refunds, zero sales).  
- Split the dataset into:
  - **Sales_df** → confirmed transactions.  
  - **Refunds_df** → returns/refunds for separate analysis.  

### 2. Feature Engineering
- Created **time-based features**: Day, Month, Year, Session (Morning/Afternoon/Evening).  
- Calculated **Total_Sales = Quantity × Price**.  
- Derived **Return Rate per country**.  
- First vs Last purchase duration per customer.  

### 3. Exploratory Data Analysis (EDA)
-  **Transaction-Level:** average basket size, purchase frequency, top invoices.  
-  **Country-Level:** UK dominated sales, followed by EIRE.  
-  **Time-Based:** November had the highest sales, Thursdays were the peak sales days.  
-  **Refunds:** ~10% return rate overall, with significant country/product differences.  

### 4. Statistical Hypothesis Testing
- **t-test:** Average spending per transaction UK vs France: significant difference.  
- **ANOVA:** Sales distribution across weekdays: sales depend on day of week.  
- **Chi-Square:** Refund rate independence from country: refunds vary significantly by geography.  

### 5. Predictive Modeling
- **Target:** Log-transformed Total Sales (`Log_TotalSales`).  
- **Preprocessing:** One-hot encoding (categoricals) + scaling (numericals).  
- **Model:** Linear Regression.  
- **Performance:**  
  - R² ≈ **0.965 (train)**, **0.965 (test)**  
  - RMSE ≈ **0.187**  
  - Model generalizes well, no signs of overfitting.  

---

## Key Insights
- **UK** is the largest contributor by far, but **EIRE** ranks surprisingly high.  
- **Thursdays** and **November** are peak sales times → valuable for marketing.  
- **Return rate ≈ 10%**, with certain countries and products driving refunds.  
- Customer purchase frequency and basket size vary significantly across groups.  

---

## How to Run
1. Clone this repo:
   ```bash
   git clone https://github.com/your-username/online-retail-analysis.git
   cd online-retail-analysis
