# 🛒 Market Basket Analysis

This project focuses on **Market Basket Analysis** using transaction data from an online retail dataset. The goal is to discover meaningful associations between products, providing valuable insights for merchandising strategies like product placement, bundling, and promotional offers.

---

## 📂 Dataset

The dataset used is **Online Retail.xlsx**, which contains over 500,000 transactions from a UK-based online retailer. Each transaction includes fields like `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, and `CustomerID`,`Country`.

---

## ⚙️ Steps Performed

### 1. **Data Loading & Exploration**
- Loaded the dataset using `pandas`.
- Explored the structure using `.head()`, `.dtypes`, and `.shape()`.

### 2. **Data Cleaning**
- Removed transactions with:
  - Zero or negative quantities (returns).
  - Invoices starting with "C" (credit notes).
  - Missing product descriptions.
- Created a filtered DataFrame with only valid transactions.
- Reduced the dataset to include only  **5,000 unique invoices**.

### 3. **Data Transformation**
- Grouped product descriptions by invoice to form a **list of transactions**.
- Used `TransactionEncoder` from **mlxtend** to one-hot encode the data into a boolean DataFrame suitable for association rule mining.

### 4. **Association Rule Mining**
- Applied both the **Apriori** and **FP-Growth** algorithms with a minimum support of 0.04.
- Generated **association rules** using a minimum confidence threshold of 0.5.
- Sorted rules based on **lift**, to highlight the strongest associations.

### 5. **Key Insights**
Some notable associations discovered:
- **ROSES REGENCY TEACUP AND SAUCER** ⇄ **GREEN REGENCY TEACUP AND SAUCER**  
  - Lift: **12.99** — Strong co-occurrence.
- **HEART OF WICKER LARGE** ⇄ **HEART OF WICKER SMALL**  
  - Confidence: **63.02%**
- **SET OF 6 SPICE TINS PANTRY DESIGN** ⇄ **SET OF 3 CAKE TINS PANTRY DESIGN**  
  - Lift: **6.15**

These associations highlight opportunities for **cross-selling**, **bundling**, and **store layout optimization**.

### 6. **Validation & Visualization**
- Used **Chi-Square Tests** to validate the statistical significance of associations.
- Visualized product co-occurrence using **heatmaps** via `seaborn`.

---

## 📊 Final Outcome

The project demonstrated:
- How to prepare retail data for association rule mining.
- How to extract and interpret product relationships.
- How to validate findings with statistical tests.
- How to generate actionable insights for business strategy.

Both **Apriori** and **FP-Growth** produced similar frequent itemsets and rules, with the latter offering better performance for larger datasets.

---

## 📦 Libraries Used
- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `mlxtend`
- `scipy`

---

## 💡 Business Value

This analysis can help businesses:
- Improve **store layout** by placing related items together.
- Design **product bundles** for promotions.
- Personalize **recommendation engines**.
- Optimize **inventory** based on frequently co-purchased items.

---

