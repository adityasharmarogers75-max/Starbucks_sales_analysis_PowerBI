# Starbucks Sales Analysis (Power BI)

📊 **Interactive Power BI Dashboard analyzing Starbucks sales data**

This project showcases an end-to-end sales analysis dashboard for **Starbucks**, built in Power BI.  
It highlights key KPIs, product performance, and customer transaction trends for actionable business insights.

---

## 🔑 Key Features
- **KPIs:** Total Sales ($58.87M), Total Quantity (214K), Total Orders  
- **Product Analysis:** Coffee, Tea, Bakery, Branded items  
- **Time-based Trends:** Sales by hour of the day, daily/weekly performance  
- **Interactive Visuals:** Bar charts, line charts, and pie charts for easy exploration  

---

## 📂 Dataset
- Orders data (`Orders_Table`)
- Product details (`Products_Table`)  
- Measures & calculations created in Power BI using **DAX**  

---

## 🧮 DAX Measures Used
### Orders Table
```DAX
Total Orders = COUNTROWS(Orders_Table)
Total Quantity = SUM(Orders_Table[transaction_qty])
Total Sales = SUM(Orders_Table[Line Sales])
Avg Quantity per Order = DIVIDE([Total Quantity], [Total Orders], 0)
Avg Sale per Order = DIVIDE([Total Sales], [Total Orders], 0)
HOUR = HOUR(Orders_Table[transaction_time])
Line Sales = Orders_Table[transaction_qty] * RELATED('Products_Table (3)'[unit_price])
