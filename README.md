# 📊 Sales Trend Analysis (Task 6)

## ✅ Objective
Analyze **monthly revenue** and **order volume** using SQL aggregations on an e-commerce dataset.

---

## 📁 Dataset
**File**: `online_sales_dataset.csv`  
**Key Columns**:
- `InvoiceDate`: Date of the order
- `InvoiceNo`: Unique order identifier
- `Quantity`: Units sold
- `UnitPrice`: Price per unit

---

## 🧪 Tools Used
- Google Colab
- Python (pandas, sqlite3)
- SQLite (in-memory)

---

## 📌 Task Requirements
1. **Extract month** from order date using SQL
2. **Group by year/month**
3. Calculate **monthly revenue** using `SUM(UnitPrice * Quantity)`
4. Count **distinct orders** per month using `COUNT(DISTINCT InvoiceNo)`
5. **Order results** by year and month
6. **Limit** results to specific date ranges (e.g., 2023)

---

## 💻 Implementation Steps
1. Uploaded CSV to Colab
2. Parsed date column (`InvoiceDate`)
3. Loaded data into SQLite in-memory database
4. Executed SQL query for:
   - Revenue by month
   - Volume by month
5. Displayed result in tabular form

---

## 🧾 SQL Query Used

```sql
SELECT 
    STRFTIME('%Y', InvoiceDate) AS year,
    STRFTIME('%m', InvoiceDate) AS month,
    SUM(UnitPrice * Quantity) AS total_revenue,
    COUNT(DISTINCT InvoiceNo) AS order_volume
FROM 
    online_sales
WHERE 
    InvoiceDate BETWEEN '2023-01-01' AND '2023-12-31'
GROUP BY 
    year, month
ORDER BY 
    year, month
