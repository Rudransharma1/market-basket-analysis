![Project Cover](COVER.jpg)

# Market Basket Analysis – Retail Sales Optimization

## Project Description
This project applies **Market Basket Analysis (MBA)** to grocery transaction data
to identify frequently purchased items and strong product associations. The goal
is to help retail businesses improve **sales, revenue, product placement, and
marketing strategies** using data-driven insights.

The analysis uses **unsupervised learning techniques** such as **Apriori** and
**FP-Growth** to uncover hidden patterns in customer purchase behavior and convert
them into actionable business recommendations.

---

## Business Problem
Retail customers often purchase multiple items together in a single transaction.
Understanding these purchase patterns enables businesses to:

- Design effective cross-selling strategies
- Create profitable product bundles
- Optimize store layout and shelf placement
- Improve targeted promotions

Without analytical insights, these decisions rely heavily on intuition rather
than data.

---

## Dataset
- **Source:** Grocery retail transactions
- **Records:** 38,765 transactions
- **Features:**
  - `Member_number` – Unique transaction ID
  - `Date` – Transaction date
  - `itemDescription` – Product purchased

📊 **Dataset file:**  
[Dataset.csv](Dataset.csv)

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
- Identified categorical purchase data
- Verified absence of missing values

---

### Step 2 — Data Cleaning & Preprocessing
The transactional dataset was prepared through:

- Converting the `Date` column to datetime format
- Extracting new features:
  - Day
  - Month
  - Year
  - Day of week
- Removing duplicate records (~759 duplicates)
- Converting numeric day/month values to readable names
- Grouping items into broader categories
- Transforming data into basket format for MBA algorithms

---

### Step 3 — Exploratory Data Analysis (EDA)
EDA helped understand shopping behavior:

- Identified 17 unique product categories
- Analyzed transaction frequency by:
  - Month
  - Day of week
- Identified top-selling items:
  - **Whole Milk** was the most frequently purchased item
- Identified top-selling category:
  - **Dairy Products**

---

### Step 4 — Association Rule Mining Concepts
Market Basket Analysis is based on three key metrics:

- **Support:** Frequency of an item or itemset
- **Confidence:** Likelihood of purchasing item B given item A
- **Lift:** Strength of association (>1 indicates strong relationship)

These metrics quantify relationships between products.

---

### Step 5 — Apriori Algorithm
The **Apriori algorithm** was used to identify frequent itemsets.

**Process:**
- Set minimum support threshold (0.10)
- Generated frequent itemsets
- Calculated support, confidence, and lift
- Filtered strong rules for business relevance

**Key Findings:**
- Dairy products showed the highest support
- Dairy and meat products were frequently purchased together
- Grain products and beverages showed strong lift values when paired with meat

---

### Step 6 — FP-Growth Algorithm
To improve performance on large datasets, **FP-Growth** was also applied.

**Why FP-Growth:**
- Faster than Apriori
- Avoids repeated database scans
- Scales efficiently for large transaction datasets

Results validated the patterns identified by Apriori.

---

## Business Insights
Key insights include:

- Strong cross-selling opportunities between dairy, meat, and grain products
- Seasonal and weekday trends affecting transaction volume
- Opportunities to bundle high-selling and low-selling items

---

## Business Recommendations
- **Product Bundling:** Bundle frequently purchased items (e.g., dairy + meat)
- **Store Layout Optimization:** Place associated products nearby
- **Promotions:** Offer discounts on low-traffic days (e.g., Mondays)
- **Loyalty Programs:** Reward multi-item purchases
- **Seasonal Campaigns:** Increase promotions during low-traffic months

---

## Project Files (Click to View)

- 📊 **Dataset:**  
  [Dataset.csv](Dataset.csv)

- 📓 **Jupyter Notebook:**  
  [Code.ipynb](Code.ipynb)

- 📄 **Final Report:**  
  [Report.docx](Report.docx)

---

## Future Improvements
- Apply analysis on larger real-world datasets
- Automate rule selection using business constraints
- Deploy insights in an interactive dashboard
- Extend analysis to customer segmentation

---

## Conclusion
This project demonstrates how **Market Basket Analysis** can uncover meaningful
patterns in transactional data and translate them into practical retail
strategies that improve decision-making and customer experience.
