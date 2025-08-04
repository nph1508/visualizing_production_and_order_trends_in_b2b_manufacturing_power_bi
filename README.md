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

#### **1. Total Orders & Scrap Rate**
- The total production volume reached **4.5 million units**, with only **11K units scrapped**, accounting for just **0.24%**, indicating excellent production efficiency.
- The **highest scrap rate** occurred in **2013** at **0.29%**, which coincided with the **peak in order volume (1.91M)**—suggesting a potential correlation between high volume and increased quality risk.

#### **2. Delivery Performancer**
- On-time deliveries increased significantly from **2011** to **2013**, peaking at **1.9M on-time orders** in 2013.
- However, in 2014, both total orders and on-time deliveries dropped sharply to **0.9M**, hinting at either declining demand or reduced production capacity.

#### **3. Manufacturing Time & Cost**
- The **most expensive stages** in the process are **Frame Forming ($92.25)** and **Frame Welding ($87.5)**, representing the largest cost centers in production.
- **Debur and Polish** is the **least costly stage ($14)**, yet it experienced a notable **increase in working hours from 6K to 20K** between 2011 and 2014.

#### **4. Total Working Hours by Production Stage**
- **2013** marked the peak in labor demand, with **Frame Forming (37K)** and **Frame Welding (31K)** recording the highest working hours.
- Stages such as **Specialized Paint** and **Subassembly** showed minimal to no activity across the years, possibly indicating process optimization or phase-outs.

#### **5. Top 5 Most Manufactured Products**
- BB Ball Bearing led production with **0.91M units**, nearly **double** the second-most produced item (**Seat Stays – 0.47M**).
- Remaining products **like Blade**, **Fork End**, and **Chain Stays** each stayed below **0.25M units**, suggesting a strong production focus on a few key items.

#### 2️⃣ Page 2: Scrap Products 
 <img width="2767" height="1600" alt="Visualizing Production   Order Trends in B2B Manufacturing-2" src="https://github.com/user-attachments/assets/e422f33b-6e41-4720-b0f2-080fa2b85598" />

### 📌 Key Findings:

#### **1. Scrap Rate Trends Over Time**
- Scrap rate rose steadily from **0.13%** (**2011**) to a peak of **0.29%** (**2013**), before dropping to **0.19%** in **2014**, indicating an improvement in quality control efforts.
- Compared to the previous year, 2014 shows a clear downward trend, suggesting corrective actions were likely effective.

#### **2. Top Scrap Reasons**
- The most common cause of scrap is “**Seat assembly not as ordered**”, with the highest scrap rate at **3.14%**.
- Other significant reasons include “**Drill size too large**” (**2.92%**), “**Paint process failed**” (**2.90%**), and “**Trim length too long**” (**2.88%**) — all pointing to assembly and process precision issues.

#### **3. Scrap Rate by Product**
- **ML Road Frame** has the highest scrap rate at **0.75%**, followed by **Mountain Frame (0.63%)** and **HL Touring Frame (0.61%)**.
- This suggests a need to revisit design tolerances or process consistency for larger frame-type products.

#### **4. Scrap Cost Analysis**
- The total scrap cost reached **$360K**, with the top reasons being:
 - **Color incorrect** ($36.23K)
 - **Trim length too long** ($34.91K)
 - **Thermoform temperature too high** ($33.21K)
- This indicates that** material quality control and finishing processes** are areas with high cost impact.

#### **5. Scrap Cost by Products**
- The product with the highest scrap cost is **ML Crankset**, totaling **$26K**, significantly ahead of others.
- Other products like **Touring Rear Wheel**, **ML Mountain Front Wheel**, and **LL Fork** follow with scrap costs around **$9K each**, indicating moderate but consistent quality challenges across multiple product lines.

#### **6. Product & Reason Cross-analysis**
- **BB Ball Bearing**, despite being the most produced item, has **multiple reasons for scrap**, such as:
  - **Handling damage (36)**
  - **Brake assembly not as ordered (35)**
  - **Drill size too small (30)**
- Although the scrap quantity for each issue is low, the diversity of causes suggests potential for process tightening.

 #### 3️⃣ Page 3: Manufactoring Time
 <img width="2767" height="1600" alt="Visualizing Production   Order Trends in B2B Manufacturing-3" src="https://github.com/user-attachments/assets/5a6ef9c0-9302-4bd6-82dc-875583cd10db" />

### 📌 Key Findings:

#### **1. Overall Manufacturing Time Performance**
- The **average actual manufacturing time** is **12 days**, slightly longer than the **scheduled 11 days**, showing mild delays across operations.
- Similarly, **average manufacturing hours** stand at **297 hours**, reflecting a consistent workload across production.

#### **2. Delivery Timeliness**
- The overall **late delivery ratio** is high at **58%**, with **27.9K orders delivered late** out of **73K total work orders**.
- While more than half of the orders were on time, the high late ratio suggests systemic bottlenecks or planning inefficiencies.

#### **3. Manufacturing Delay by Product**
- Several products show **consistently high actual manufacturing days** (**16 days**) — including:
 - **ML Mountain Frame - Black**
 - **ML Mountain Handlebars**
 - **ML Mountain Seat Assembly**
- These items may be more complex or resource-intensive, driving longer production cycles.

#### **4. Stage-Level Delays**
- Every production stage exceeds the planned 11 days, with **Specialized Paint** and **Debur and Polish** taking **13 days**, representing the largest overruns.
- The smallest delay gap is in **Subassembly**, **Frame Forming**, and **Frame Welding** (12 actual vs 11 scheduled).

#### **5. Late Delivery Ratio by Stage Over Time**
- The **worst-performing stages** in 2011 were **Debur and Polish** (**77%**) and **Final Assembly** (**76%**) late ratios.
- By 2014, improvements were evident, but **most stages still had 58–61% late deliveries**, showing gradual but incomplete progress in on-time performance.

#### **6. Products with Most Overdue Days**
- The top delayed product is **Mountain-500 Black**, with an average of **10.8 overdue days**, followed closely by **Road-750 Black** (**10.7 days**) and **Mountain-400-W** (**10.5 days**).
- All **top 10 delayed products** exceed **10 days overdue on average**, highlighting recurring issues in specific SKUs.

---
## 5. 🔎 Final Conclusion & Recommendations

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
