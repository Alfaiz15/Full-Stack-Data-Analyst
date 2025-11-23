# 📦 Data-Driven Logistics: Warehouse Automation & Analysis (SQL Focused)

## 📌 Project Overview

This project demonstrates **Data Analyst** capabilities in designing a logistics database structure and implementing **Operational Automation** using **Advanced SQL**. The goal is to ensure accurate inventory data and provide reliable warehouse profitability metrics for management decision-making.

---

## 🛠️ Tools & Data

* **Primary Tool:** SQL (MySQL/MariaDB)  
* **Outputs:** Stored Procedures, Views, and Performance Analysis Queries  
* **Operational Focus:** Inventory Management, Supply Chain Efficiency, and Profitability Analysis  

---

## ⚙️ Workflow & SQL Implementation

The project is structured into three main pillars, showcasing expertise in **data modeling** and **data engineering** in SQL.

### 1. Data Structure Design (Schema & Integrity)

* **Task:** Design the database schema (`warehouse_db`) with main tables: `warehouses`, `products`, `inventory`, `shipments`  
* **SQL Expertise:** Used `CREATE TABLE` and **Foreign Keys** to enforce **data integrity** and prevent **redundancy**, ensuring consistent relationships between tables  

---

### 2. Analytical Engine (Advanced Querying)

Built an analytical engine to calculate complex KPIs for **Operations** and **Finance** teams.

| Key Metric | SQL Technique | Business Value |
| :--- | :--- | :--- |
| **Warehouse Net Profit** | **CTEs** to separate calculations of `total revenue` and `total expense` before computing the difference | Identifies true **Profit Centers** and **Cost Centers** across warehouses |
| **Supplier Performance** | `JOIN` + `GROUP BY` to analyze average **lead time** per supplier | Identifies the most efficient suppliers, optimizing the supply chain |

---

### 3. Business Automation (Procedures & Views)

Implemented automation solutions to reduce manual intervention in **inventory management**.

| SQL Solution | Technical Description | Operational Impact |
| :--- | :--- | :--- |
| **Low Stock View (`vw_low_stock`)** | Created a **VIEW** automatically showing products below critical threshold (`< 100`) | Acts as an **Early Warning System**, speeding up restocking and preventing **stock-outs** |
| **Stored Procedure (`sp_update_stock`)** | Developed a **Stored Procedure** to automatically adjust inventory based on transaction input | Ensures **real-time data accuracy**, maintains consistent stock, and reduces human errors |

---

## 💡 Impact & Conclusion

This project demonstrates the ability to **translate operational needs into structured data solutions**. Using **Advanced SQL** (CTEs, Views, Stored Procedures) directly improves inventory accuracy, enables rapid profitability analysis, and supports overall **Supply Chain Efficiency**.
