# 📊 Sales Performance Dashboard

## 🚀 Project Overview  
This project presents an interactive **Sales Performance Dashboard** built using **Power BI**. It provides insights into sales, profit, customer segments, and regional performance to support data-driven decision-making.

---

## 📂 Source Dataset  

This project uses a **[Sales_Performance](https://github.com/jaysharma03/Sales_Performance_maincraft_task4/blob/main/Sales_performance_dataset.zip)** containing:

- Orders (Sales, Profit, Quantity)  
- Customers (Region, Segment)  
- Products (Category, Sub-Category)  
- Calendar (Date, Month, Year)  

Structured using a **Star Schema** for efficient analysis.

---

## 🛠️ Tools & Technologies  
- Power BI  
- DAX (Data Analysis Expressions)  
- Data Modeling (Star Schema) 

---

## 📊 Key Insights  
 
- 🌍 **Regional Performance:**  
  - West region is the **top revenue contributor (360K)**  
  - South region is the **lowest performing (191K)**  

- 💻 **Category Performance:**  
  - Technology generates the **highest profit (~70K)**  
  - Furniture has **very low profit (~8K)**  

- 👥 **Customer Segments:**  
  - Consumer segment contributes the **largest share (~52%)**  
  - Corporate and Home Office follow   

---

## 🧠 Business Insights  
- Sales show **steady growth with fluctuations**  
- West region is the **main revenue driver**  
- Technology category is **most profitable**  
- Consumer segment contributes the most  
- Furniture category needs improvement  

---

## 🗂️ Data Model  

![Data Model](https://github.com/jaysharma03/Sales_Performance_maincraft_task4/blob/main/Sales_Data_Modeling.JPG)

### ⭐ Star Schema  

**Fact Table:**  
- Order Table (Sales, Profit, Quantity)

**Dimension Tables:**  
- Customer Dataset  
- Product Dataset  
- Calendar Table  

### 🔗 Relationships  
- Customer → Order (1:M)  
- Product → Order (1:M)  
- Calendar → Order (1:M)  

---

## 📈 DAX Measures  

```DAX
Total Sales = SUM(order[Sales])

Total Profit = SUM(order[Profit])

Total Orders = COUNT(order[Order ID])

Profit Margin = DIVIDE([Total Profit], [Total Sales])
```

---

## 📅 Time Intelligence  

```DAX
Previous Month Sales = 
CALCULATE(
    [Total Sales],
    PREVIOUSMONTH(Calendar_table[Date])
)
```

### 🔹 Growth Metrics

```DAX
 Growth % =
DIVIDE(
    [Total Sales] - [Previous Month Sales],
    [Previous Month Sales],
    0
)
```

### 🔹 Category Contribution

```DAX
Category Contribution % =
DIVIDE(
    [Total Sales],
    CALCULATE(
        [Total Sales],
        ALL(product_dataset[Category])
    ),

)
```

---

## 📷 Dashboard Preview  
![Dashboard](https://github.com/jaysharma03/Sales_Performance_maincraft_task4/blob/main/Sales_Analysis_Dashboard.JPG)

---

## 👤 Author  

**Jay Sharma**  
 
---

