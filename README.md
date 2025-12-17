![Project Cover](cover.jpg)

# Market Basket Analysis – Retail Sales Optimization

## Project Description

This project applies **Market Basket Analysis (MBA)** to transactional grocery data to
identify **frequently purchased items** and **strong product associations**.
The objective is to help retail businesses improve **sales, revenue, product placement,
and marketing strategies** using data-driven insights.

The analysis uses **unsupervised machine learning techniques** to discover hidden
patterns in customer purchase behavior and translate them into actionable
business recommendations.

---

## Business Problem
Retail customers often purchase multiple items together during a single shopping trip.
Understanding **which products are frequently bought together** enables businesses to:

- Design effective cross-selling strategies
- Create profitable product bundles
- Optimize store layout and shelf placement
- Improve targeted promotions

Without data-driven analysis, these decisions rely on intuition rather than evidence.

---

## Dataset
- **Source:** Kaggle – Grocery retail transactions
- **Records:** 38,765 transactions
- **Features:**
  - `Member_number` – Unique transaction ID
  - `Date` – Transaction date
  - `itemDescription` – Product purchased

📂 **View dataset:**  
[data/Groceries_dataset.csv](data/Groceries_dataset.csv)

---

## Tools & Technologies
- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- MLxtend
- Jupyter Notebook

---

## Step-by-Step Workflow

### Step 1 — Data Understanding
- Reviewed transaction structure
- Identified categorical nature of purchase data
- Verified absence of missing values

---

### Step 2 — Data Cleaning & Preprocessing
The raw transactional data was prepared for analysis through the following steps:

- Converted `Date` column to datetime format
- Extracted new features:
  - Day
  - Month
  - Year
  - Day of week
- Removed duplicate records (~759 duplicates)
- Converted numeric day and month values to readable names
- Created a new column `itemCategory` to group similar products
- Transformed transaction data into basket format suitable for MBA algorithms

---

### Step 3 — Exploratory Data Analysis (EDA)
EDA was performed to understand customer shopping behavior:

- Identified **17 unique product categories**
- Analyzed transaction frequency by:
  - Month
  - Day of week
- Identified top-selling items
  - *Whole Milk* was the most frequently purchased item
- Identified top-selling category
  - *Dairy Products* ranked highest

These insights helped contextualize later association rules.

---

### Step 4 — Association Rule Mining Concepts
Market Basket Analysis is based on **Association Rule Mining**, which uses three key metrics:

- **Support:** Frequency of item or itemset in transactions
- **Confidence:** Likelihood of purchasing item B given item A
- **Lift:** Strength of association (>1 indicates strong relationship)

These metrics quantify how items are related in customer purchases.

---

### Step 5 — Apriori Algorithm
The **Apriori algorithm** was applied to identify frequent itemsets and generate
association rules.

**Process:**
- Defined minimum support threshold (0.10)
- Generated frequent itemsets
- Calculated support, confidence, and lift
- Filtered strong rules for business relevance

**Key Findings:**
- Dairy products had the highest support
- Dairy products and meat were frequently purchased together
- Grain products, beverages, and vegetables showed strong lift values when paired with meat

---

### Step 6 — FP-Growth Algorithm
To improve efficiency on large datasets, **FP-Growth** was also applied.

**Why FP-Growth:**
- Faster than Apriori
- Avoids repeated database scans
- Scales better for large transaction datasets

Results from FP-Growth validated the frequent itemsets discovered by Apriori.

---

### Step 7 — Business Insights
Key insights derived from the analysis include:

- Strong cross-selling opportunities between dairy, meat, and grain products
- Seasonal and weekday patterns affecting transaction volume
- Opportunities for bundling high-selling and low-selling products

---

## Business Recommendations
Based on the analysis, the following strategies are recommended:

- **Product Bundling:** Combine frequently purchased items (e.g., dairy + meat)
- **Store Layout Optimization:** Place strongly associated products strategically
- **Promotional Campaigns:** Offer discounts on low-traffic days (e.g., Mondays)
- **Loyalty Programs:** Reward customers for multi-item purchases
- **Seasonal Campaigns:** Increase promotions during low-traffic months (e.g., September)

---

## Project Files (Click to View)

- 📊 Dataset:  
  [Groceries_dataset.csv](data/Groceries_dataset.csv)

- 📓 Jupyter Notebook:  
  [Market_Basket_Analysis_Group1.ipynb](notebook/Market_Basket_Analysis_Group1.ipynb)

- 📄 Final Report:  
  [ML-FinalProject-Group1.docx](reports/ML-FinalProject-Group1.docx)

---

## Future Improvements
- Apply analysis on larger real-world retail datasets
- Automate rule selection using business constraints
- Deploy insights into a dashboard for decision-makers
- Extend analysis to customer segmentation
market-basket-analysis/
├── README.md
├── cover.jpg
├── data/
│   └── Groceries_dataset.csv
├── notebook/
│   └── Market_Basket_Analysis_Group1.ipynb
├── reports/
│   └── ML-FinalProject-Group1.docx

