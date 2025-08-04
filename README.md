# Visualizing Production & Order Trends in B2B Manufacturing | Power BI

<img src="https://github.com/user-attachments/assets/1f663de1-d2fd-4be7-95d1-6e084a1b2be7" width="100%" />


Author: Nguyễn Phương Huy

Date: May 2025

Tools Used: PowerBI

---
## 📑 Table of Contents  
[1. 📌 Background & Overview](#1--background--overview)  
[2. 📂 Dataset Description & Data Structure](#2--dataset-description--data-structure)   
[3. 🧠 Design Thinking Process](#3--design-thinking-process)  
[4. 📊 Key Insights & Visualizations](#4--key-insights--visualizations)  
[5. 🔎 Final Conclusion & Recommendations](#5--final-conclusion--recommendations)

---
## 1. 📌 Background & Overview 

**Objective:**

**📖 What is this project about?**

This project analyzes purchasing activities at **AdventureWorks** to support better operational decisions. The Power BI dashboard focuses on:

- **Manufactoring Performance**: Track production status to facilitate storage and distribution to customers. 
- **Optimization**: During the warehouse inspection process, there is a possibility that goods will be damaged, and will be rejected to ensure that only quality products are stored for sale.

**👤 Who is this project for?**

This dashboard is designed for key stakeholders involved in the manufactoring process at **AdventureWorks**, including:

 - **Manufactoring Manager**: To monitor supplier performance, order fulfillment, and spot procurement issues early.  
- **Manufactoring Executive**: To track purchasing KPIs, ensure compliance with procurement strategies, and manage day-to-day operations efficiently.  
- **Board of Directors (BOD)**: To gain high-level insights into purchasing efficiency and cost control for strategic decision-making.

**❓Business Questions:**
 - ✔️ What is the current performance of Superstore?
 - ✔️ Which markets should Superstore expand into to increase revenue and ROI?
 - ✔️ Which products should be prioritized for strategic growth?

---

## 2. 📂 Dataset Description & Data Structure 

### **📌 Data Source** 
- **Source**: Kaggle - Dataset of AdventureWorks
- **Size**: The **Production_WorkOrder** table contains **72.839** records.  
- **Format**: Pbix 

### 📊 **Data Structure & Relationships**  

#### 1️⃣ **Tables Used:** 
The dataset consists of **6 main tables** used to build the purchasing dashboard:

- 🗂️ **Dim_Product** – Product category and hierarchy.

<details>
<summary><strong>Table 1: Dim_Product</strong></summary>

| Column Name                 | Description              |
|-----------------------------|--------------------------|
| `ProductID`                 | Linked product           |
| `Name`                      | Product characteristics  |
| `Category`                  | Product category name    |
| `Subcategory`               | Product subcategory name |
| `ListPrice`, `StandardCost` | Price and cost info      |

</details>

- 🏷️ **Product_Inventory** – Current inventory levels.

<details>
<summary><strong>Table 2: Product_Inventory</strong></summary>

| Column Name            | Description                                   |
|------------------------|-----------------------------------------------|
| `Quantity`             | Current inventory quantity                    |
| `Below Reorder Flag`   | Indicates if inventory is below reorder level |
| `BelowSafetyStock`     | Indicates stock is below safety threshold     |
| `OutOfStockProducts`   | Out of stock status                           |
| `ProductID`            | Foreign key to product                        |

</details>

- 🧾 **Production_ScrapReason** – The Reason of Scrap Product.

<details>
<summary><strong>Table 3: Production_ScrapReason</strong></summary>

| Column Name     | Description                   |
|-----------------|-------------------------------|
| `ScrapReasonID` | Unique ScrapReason identifier |
| `Name`          | ScrapReason characteristics   |

</details>

- 📄 **Production_Location** – Order-level metadata.

<details>
<summary><strong>Table 4: Production_Location</strong></summary>

| Column Name                 | Description      |
|-----------------------------|------------------|
| `LocationID`                | Location ID      |
| `Name`                      | Location Name    |
| `CostRate`,  `Availability` | Location info    |

</details>

#### 2️⃣ Data Relationships: 
<img width="1394" height="634" alt="image" src="https://github.com/user-attachments/assets/a9a1383e-34e6-4c65-aa6d-536c674fbb98" />

| **From Table**                  | **To Table**                     | **Join Key**                | **Relationship Type**                                      |
|--------------------------------|----------------------------------|-----------------------------|------------------------------------------------------------|
| `Fact_Purchasing_OrderDetail`  | `Dim_Purchasing_OrderHeader`     | `PurchaseOrderID`           | Many-to-One (many order lines per order header)            |
| `Fact_Purchasing_OrderDetail`  | `Dim_Product_Product`            | `ProductID`                 | Many-to-One (many order lines for one product)             |
| `Fact_Purchasing_OrderDetail`  | `Dim_Order_Date`                 | `DueDate` / `ModifiedDate`  | Many-to-One (orders map to one date)                       |
| `Dim_Purchasing_OrderHeader`   | `Dim_Purchasing_Vendor`          | `VendorID`                  | Many-to-One (multiple orders per vendor)                   |
| `Dim_Purchasing_ProductVendor` | `Dim_Purchasing_Vendor`          | `VendorID`                  | Many-to-One (vendor supplies many products)                |
| `Dim_Purchasing_ProductVendor` | `Dim_Product_Product`            | `ProductID`                 | Many-to-One (vendor offers multiple products)              |
| `Dim_Product_Product`          | `Dim_Product_ProductTaxonomy`    | `ProductSubcategoryID`      | Many-to-One (each product belongs to one subcategory)      |
| `Fact_Product_Inventory`       | `Dim_Product_Product`            | `ProductID`                 | Many-to-One (each inventory record linked to a product)    |

---

## 3. 🧠 Design Thinking Process 

*A human-centered approach for actionable insights*  

### 1️⃣ Empathize

### 2️⃣ Define point of view 

### 3️⃣ Ideate

### 4️⃣ Prototype and review

This part is in the dashboard

---

## 4. 📊 Key Insights & Visualizations 
### 🔍 Dashboard Preview 
#### 1️⃣ Page 1: Manufacturing Overview Dashboard  
<img width="2767" height="1600" alt="Visualizing Production   Order Trends in B2B Manufacturing-1" src="https://github.com/user-attachments/assets/4b762c0b-857a-4be9-8973-9729a6542ae7" />


### 📌 Key Findings:
- **Observation:**  
  - Plant-wide OEE at **78.46%** with significant location variance (19%-49%)  
  - 12-month trend shows July dip (aligns with maintenance period)  
  - Road products outperform Mountain lines by **12-18% OEE**  

- **Recommendation:**  
  - Investigate best practices at top-performing location (49%)  
  - Schedule preventive maintenance during low season  
  - Cross-train teams between Road/Mountain lines  

#### 2️⃣ Page 2: Quality & Performance Dashboard  
 <img width="2767" height="1600" alt="Visualizing Production   Order Trends in B2B Manufacturing-2" src="https://github.com/user-attachments/assets/e422f33b-6e41-4720-b0f2-080fa2b85598" />

### 📌 Key Findings: 
- **Observation:**  
  - Paint process failures account for **32%** of total scrap  
  - HL Mountain Frame has highest downtime (**129,168h**)  
  - Strong correlation: 57.8% scrap rate → 1,440h downtime  

- **Recommendation:**  
  - Implement paint process audit for HL Mountain line  
  - Redesign drill size QC checks (top scrap reason)  
  - Prioritize maintenance for high-downtime assemblies

 #### 3️⃣ Page 3: Product Analysis Dashboard Preview 
 <img width="2767" height="1600" alt="Visualizing Production   Order Trends in B2B Manufacturing-3" src="https://github.com/user-attachments/assets/5a6ef9c0-9302-4bd6-82dc-875583cd10db" />

### 📌 Key Findings:

---
## 🔎 Final Conclusion & Recommendations  

👉🏻 Based on the OEE and quality analysis, we recommend the **Production Leadership Team** to prioritize these actions:  

📌 **Key Takeaways:**  
✔️ **Immediate Quality Intervention**  
- Address paint process failures (32% of scrap) through equipment calibration and operator retraining  
- Implement mandatory drill size checks for HL Mountain Frame line (57.8% defect correlation)  

✔️ **OEE Improvement Plan**  
- Replicate Road-150 production methods (90.17% OEE) to underperforming lines  
- Focus on location with 19% OEE through cross-training and process benchmarking  

✔️ **Downtime Reduction**  
- Schedule preventive maintenance during low season (July trend dip)  
- Optimize HL Mountain Frame assembly (129,168h downtime) using Lean methodologies  

> 🚀 **Next Steps:** Establish a 30-60-90 day action plan with weekly OEE tracking and scrap rate alerts
