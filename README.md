# Power BI for B2B Manufacturing: Visualizing Production & Order Trends
Author: Nguyễn Phương Huy

Date: 2000-15-08

Tools Used: PowerBI

---
## 📑 Table of Contents  
1. [📌 Background & Overview](#-background--overview)  
2. [📂 Dataset Description & Data Structure](#-dataset-description--data-structure)  
3. [🧠 Design Thinking Process](#-design-thinking-process)  
4. [📊 Key Insights & Visualizations](#-key-insights--visualizations)  
5. [🔎 Final Conclusion & Recommendations](#-final-conclusion--recommendations)

---
## 📌 Background & Overview  

### 🎯 Objective  
Develop an **Operations Dashboard** that enables the Production Director to:  
- Monitor end-to-end manufacturing workflow from material receipt to finished goods  
- Identify bottlenecks in production timelines  
- Track quality control metrics in real-time

### 🏭 Business Context  
**Current Process Flow:**  
1. **Planning Phase:** Receive production requests from Company's Planning Dept  
2. **Procurement:** Materials ordered and received by Purchasing Team  
3. **Production:** Manufacturing begins after materials inspection  
4. **Storage:** Finished goods distributed across multiple warehouse locations  
5. **Quality Check:** Defective items removed before customer distribution

**Key Challenges:**  
- Production delays vs. planned schedules  
- Quality defects during warehouse inspection  
- Lack of real-time visibility across dispersed storage locations 
 _Example:_
 
 This project analyzes sales trends and inventory control using SQL and Power BI. The objective is
 - optimize stock levels & improve demand forecasting
 - reduce costs.  

### 👤 Who is this project for?  

Mention who might benefit from this project 

 _Example:_

✔️ Data analysts & business analysts  
✔️ Supply chain managers & inventory controllers  
✔️ Decision-makers & stakeholders  

###  ❓Business Questions:  
Clearly outline what the business questions project will solve.  

 _Example:_

✔️ Identify high-demand products and sales trends.  
✔️ Optimize inventory levels to prevent overstocking or stockouts.  
✔️ Provide actionable insights through Power BI dashboards.  

### 🎯Project Outcome:  
Summarize key findings and insights/ trends/ themes in a concise, bullet-point 
format.  

 _Example:_

✔️ Sales Trends: The top X% of products generate Y% of revenue.  
✔️ Inventory Optimization: Certain products are frequently out-of-stock, causing revenue loss.  
✔️ Customer Behavior: Returning customers spend Z% more per transaction than new customers.  

---

## 📂 Dataset Description & Data Structure  

### 📌 Data Source  
- Source: (Mention where the dataset is obtained from—Kaggle, company database, government sources, etc.)  
- Size: (Mention the number of rows & columns)  
- Format: (.csv, .sql, .xlsx, etc.)  

### 📊 Data Structure & Relationships  

#### 1️⃣ Tables Used:  
Mention how many tables are in the dataset.  

#### 2️⃣ Table Schema & Data Snapshot  

Table 1: Products Table  

👉🏻 Insert a screenshot of table schema 

 _Example:_

| Column Name | Data Type | Description |  
|-------------|----------|-------------|  
| Product_ID  | INT      | Unique identifier for each product |  
| Name        | TEXT     | Product name |  
| Category    | TEXT     | Product category |  
| Price       | FLOAT    | Price per unit |  



Table 2: Sales Transactions  

👉🏻 Insert a screenshot of table schema 


 _Example:_

| Column Name    | Data Type | Description |  
|---------------|----------|-------------|  
| Transaction_ID | INT      | Unique identifier for each sale |  
| Product_ID     | INT      | Foreign key linking to Products table |  
| Quantity       | INT      | Number of items sold |  
| Sale_Date      | DATE     | Date of transaction |  


📌If the table is too big, only capture a part of it that contains key metrics you used in the projects or put the table in toggle

#### 3️⃣ Data Relationships:  
Describe the connections between tables—e.g., one-to-many, many-to-many.  

👉🏻 Include a screenshot of Data Modeling to visualize relationships.  

---

## 🧠 Design Thinking Process  

**A 5-stage human-centered approach to build actionable dashboards:**  

### 1️⃣ Empathize - Understand User Needs 
**Đối tượng chính:** Production Director & Operations Team
**Key Pain Points:**  
 - No real-time overview of production performance
 - Fragmented data from multiple sources (ERP, Excel, IoT)
 - Inability to quickly identify bottlenecks/defects

**Empathy Map:**  
| Aspect | Insights |  
|--------|----------|  
| **Needs** | Real-time dashboard with auto-alerts + drill-down from overview to machine/process level|  
| **Frequent Questions** | "Which machine caused defects?", "Actual vs Target comparison?", "3-month KPI trends?"|  

### 2️⃣ Define - Frame the Problem 
**Northstar Metric:**  
📊 **OEE (Overall Equipment Effectiveness)** - Measures production efficiency through:
- **Availability** (Uptime vs Planned Production Time)  
- **Performance** (Actual vs Maximum Speed)  
- **Quality** (Defect-Free Products)

**Growth Formula:**  OEE = Availability (%) × Performance (%) × Quality (%)


### 3️⃣ Ideate - Dashboard Framework
**Information Architecture:**  
| Layer | Scope | Visualization Examples  |  
|-------|-------|------------------------ |  
| **Layer 0** | Executive Summary	 | OEE Scorecard, Defect Rate, Downtime|  
| **Layer 1** | Machine/Process Level| Downtime Hours, Scrap Rate by Station |  

**Dashboard Structure:**
1. **Overview Page:** Key OEE metrics (78.46%) with KPI alerts
2. **Analytics Page:** Granular performance breakdown by product line/machine

### 4️⃣ Prototype (Design Iterations)
Key Features Implemented:
- ✅ Dynamic OEE Breakdown Wheel
- ✅ Machine Status Traffic Light System
- ✅ Interactive Downtime Pareto Chart
- ✅ Shift Comparison Matrix  

### 5️⃣ Validate (User Testing)
**Feedback Implementation:**  
- Improved color contrast for color-blind users 
- Added export functionality for reports
- Simplified navigation between hierarchy levels
  
💡 Iterative Improvement: Conducted 3 sprint cycles with stakeholder reviews to refine the final solution

---

## ⚒️ Main Process

1️⃣ Data Cleaning & Preprocessing  
2️⃣ Exploratory Data Analysis (EDA)  
3️⃣ SQL/ Python Analysis 

- In each step, show your Code

- Include query/ code execution screenshots or result samples

- Explain its purpose and its findings


4️⃣ Power BI Visualization  (applicable for PBI Projects)

---

## 📊 Key Insights & Visualizations  

### 🔍 Dashboard Preview  

#### 1️⃣ Dashboard 1 Preview  
👉🏻 Insert Power BI dashboard screenshots here  

📌 Analysis 1:  
- Observation: _Describe trends, key metrics, and patterns._  
- Recommendation: _Suggest actions based on insights._  

#### 2️⃣ Dashboard 2 Preview  
👉🏻 Insert Power BI dashboard screenshots here

📌 Analysis 2:   
- Observation: _Describe trends, key metrics, and patterns._  
- Recommendation: _Suggest actions based on insights._  

#### 3️⃣ Dashboard 3 Preview  
👉🏻 Insert Power BI dashboard screenshots here  

📌 Analysis 3:  
- Observation: _Describe trends, key metrics, and patterns._  
- Recommendation: _Suggest actions based on insights._  

---

## 🔎 Final Conclusion & Recommendations  

👉🏻 Based on the insights and findings above, we would recommend the [stakeholder team] to consider the following:  

📌 Key Takeaways:  
✔️ Recommendation 1  
✔️ Recommendation 2  
✔️ Recommendation 3
