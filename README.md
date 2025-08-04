# Visualizing Production & Order Trends in B2B Manufacturing | Power BI
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

### 👤 Who is this project for?  

Mention who might benefit from this project 

 _Example:_

✔️ Data analysts & business analysts  
✔️ Supply chain managers & inventory controllers  
✔️ Decision-makers & stakeholders  

###  ❓Business Questions:  
1. Schedule Adherence
  - What percentage of orders meet planned completion dates?
  - Which production lines consistently delay?
2. Quality Control
  - What are the top 3 defect types found during inspection?
  - How does defect rate correlate with production shifts?
3. Inventory Optimization
  - Which warehouse locations have:
    - Highest storage turnover?
    - Most quality incidents?

### 🎯Project Outcome:  
| Metric                | Current State | Target Improvement | 
|---------------------- |---------------|--------------------| 
| On-Time Completion    | 72%           | +15%               |
| Defect Rate           | 23.6%         | -8%                |
| Warehouse Utilization | 68%           | +12%               |

**💡 Innovation Opportunity:** Implement machine learning to predict defect risks based on material batch + operator variables

---

## 📂 Dataset Description & Data Structure  

### 📌 Data Source  
- Source: 
- Size:  
- Format:  

### 📊 Data Structure & Relationships  

#### 1️⃣ Tables Used:  

#### 2️⃣ Table Schema & Data Snapshot    

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

<img width="1394" height="634" alt="image" src="https://github.com/user-attachments/assets/a9a1383e-34e6-4c65-aa6d-536c674fbb98" />


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
  
> Iterative Improvement: Conducted 3 sprint cycles with stakeholder reviews to refine the final solution

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
#### 1️⃣ Page 1: Manufacturing Overview Dashboard  
 ![Project3_NgPhuongHuy_page-0001](https://github.com/user-attachments/assets/9be82d5c-56c8-41bf-9b59-79ddb48f5a24)

📌 **Analysis:**  
- **Observation:**  
  - Plant-wide OEE at **78.46%** with significant location variance (19%-49%)  
  - 12-month trend shows July dip (aligns with maintenance period)  
  - Road products outperform Mountain lines by **12-18% OEE**  

- **Recommendation:**  
  - Investigate best practices at top-performing location (49%)  
  - Schedule preventive maintenance during low season  
  - Cross-train teams between Road/Mountain lines  

#### 2️⃣ Page 2: Quality & Performance Dashboard  
 ![Project3_NgPhuongHuy_page-0002](https://github.com/user-attachments/assets/e3007d2d-b108-4ac3-a698-24a5a724dbc6)
 
📌 **Analysis:**  
- **Observation:**  
  - Paint process failures account for **32%** of total scrap  
  - HL Mountain Frame has highest downtime (**129,168h**)  
  - Strong correlation: 57.8% scrap rate → 1,440h downtime  

- **Recommendation:**  
  - Implement paint process audit for HL Mountain line  
  - Redesign drill size QC checks (top scrap reason)  
  - Prioritize maintenance for high-downtime assemblies
 
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
