# 📊 Procurement Spend & Supplier Performance Analysis | Retail Import/Distribution | Power BI (Power Query + DAX)
- **Business questions** :
  +  How does purchasing spend change over time, and what drives it by supplier/SKU?
  +  Where are the price gaps vs best price, and how much potential savings can we capture?
  +  Which suppliers deliver the best balance of cost vs delivery performance (received/on-time rate)?
    
- **Domain** : Procurement / Purchasing Analytics for a retail import & distribution company (Wide World Importers – WWI), focusing on spend control, supplier evaluation, and delivery reliability.
  
📌 **Goal** : Build a Power BI dashboard to monitor purchasing cost, ordering trends, supplier effectiveness, and provide actionable insights & recommendations to optimize procurement operations.

Author: Lê Trường Quyết

Date: 2025-09-07

Tools Used: Power BI (Power Query, DAX)

## 📑 Table of Contents  
1. [📌 Background & Overview](#-background--overview)
2. [📂 Dataset Description & Data Structure](#-dataset-description--data-structure)
3. [🧠 Design Thinking Process](#-design-thinking-process)
4. [📊 Key Insights & Visualizations](#-key-insights--visualizations)
5. [🔎 Final Conclusion & Recommendations](#-final-conclusion--recommendations)

## 📌 Background & Overview  

### Objective:
### 📖 What is this project about? 

- This project analyzes purchasing data from Wide World Importers (WWI) in Power BI to help the business understand where money is spent, what items drive cost, and which suppliers perform best :
  
    ✔️ Analyze WWI purchasing data in Power BI to understand spend trends and the main drivers by supplier and SKU.
  
    ✔️ Identify price gaps vs best price and estimate potential savings to support negotiation and cost control.
  
    ✔️ Evaluate supplier performance (cost + delivery/received rate) and turn insights into actionable procurement recommendations.

  👤 Who is this project for?

    ✔️ Procurement / Purchasing managers
    ✔️ Supply chain & warehouse teams
    ✔️ Finance / management stakeholders
  
## 📂 Dataset Description & Data Structure 

### 📌 Data Source
   
  - Source: Wide World Importers (WWI) – a sample data warehouse dataset 
  - Size : 
    + Tables (sheets): 13 tables
    + Total rows: ~915,249 rows across all tables 
    + Columns: varies by table (6 → 21 columns)
  - Format : .xlsx
### 📊 Data Structure & Relationships  

#### 1️⃣ Tables Used:  
  The dataset consists of 6 main tables used to build the WWI Purchasingdashboard:
  - 🧾 Fact_Transaction – Transaction-level purchasing spend (Total Incl/Excl Tax, PO ID…).
  - 📦 Fact_Movement – Order/receipt movements to calculate Ordered/Received Qty & Received Rate.
  - 🏭 Dim_Supplier – Supplier master data (supplier name, category, payment terms…).
  - 🏷️ Dim_StockItem – SKU master data (unit price, lead time days, quantity per outer…).
  - 📅 Dim_Date – Calendar table for month/quarter/year analysis & time intelligence.
  - 🔁 Dim_TransactionType – Classifies movement/transaction types (used for ordered vs received logic).
#### 2️⃣  Data Relationships:  
  <img width="948" height="762" alt="image" src="https://github.com/user-attachments/assets/95e706a0-df95-48a1-9507-1ef0857f13a6" />

## 🧠 Design Thinking Process  
### 1️⃣ Empathize
  <img width="1629" height="906" alt="image" src="https://github.com/user-attachments/assets/0fe39b85-6e32-4e59-a0db-f483a917dd7f" />

  <img width="1630" height="893" alt="image" src="https://github.com/user-attachments/assets/fc4c0f30-8c1c-493b-81c1-aaeee248c0ac" />

  <img width="1601" height="766" alt="image" src="https://github.com/user-attachments/assets/60476aab-d7d7-4d42-a5d9-e2d38ffb0cab" />

### 2️⃣ Define point of view 
   <img width="1593" height="873" alt="image" src="https://github.com/user-attachments/assets/9c83ece4-4036-4173-af2a-c4cd91c88d8f" />

  <img width="1100" height="616" alt="image" src="https://github.com/user-attachments/assets/a8d231db-bb52-4201-ba48-030ab9caddf0" />



### 3️⃣ Ideate  

  <img width="1103" height="617" alt="image" src="https://github.com/user-attachments/assets/aea84edb-03d6-4513-a4ff-0596a93b1216" />

  <img width="1579" height="873" alt="image" src="https://github.com/user-attachments/assets/ad847046-a535-42fe-8454-2ab7c92c29dc" />


### 4️⃣ Prototype and review  
This part is in the dashboard

## 📊 Key Insights & Visualizations  

### 🔍 Dashboard Preview  

### 1️⃣ Spend Overview

<img width="1247" height="689" alt="image" src="https://github.com/user-attachments/assets/527e7dc8-b95c-4db9-9d0b-c3a0e6a1e274" />

### 📌 Key Findings : 

**1. Total Spend Growth (2013–2015)**

- Total purchasing spend increased sharply year over year: **2013 ~$145.6M → 2014 ~$519.7M → 2015 ~$966.6M.**
- Approx. growth rates: **+~257% (2014 vs 2013) and +~86% (2015 vs 2014).**

-> **Procurement scale-up is significant**, so tighter spend governance (pricing policy + supplier control) becomes critical.

**2. Supplier Concentration Risk**

- Spend is heavily concentrated in **two key suppliers:**
  + Fabrikam, Inc. dominates (2015: **~$713M** out of **~$966.6M).**
  + Litware, Inc. is the second largest (2015: **~$253.6M)**.
- Other suppliers contribute marginally.

-> **High dependency risk** (reduced negotiation leverage + higher disruption exposure).


**3. Monthly Spend Trend (Seasonality / Volatility)**

- The monthly trend shows **mid-year uplift**, followed by **a sharp drop**, then **stabilization / slight rebound** toward later months (depending on filters).
- The gap between **Total Spend** and **Spend PM** suggests periods where spending momentum changes noticeably.

-> **Clear seasonality** and volatility; planning and negotiations should be aligned ahead of peak months.

**4. Top SKUs Drive a Large Share of Spend**

- The bar chart and treemap show spend concentrated in **a small set of top stock items** (some items reach **~$0.30–0.38bn).**
- The remaining SKUs form a long tail with much smaller contributions.

-> **Managing top SKUs** (benchmarking best price, price caps, supplier allocation) will deliver the biggest impact.

**5. Purchasing Pattern: Ordered Quantity vs PO Count**

- KPIs indicate **Ordered Qty ~140M** and **PO Count ~2K**, implying roughly **~70K units per PO** (rough estimate).

-> This suggests batch ****purchasing / fewer** but larger POs**, which can reduce ordering overhead but increases the importance of inventory timing and risk control.

**6. Metric / Data Quality Check (Spend PM = 0.00)**

- The KPI card shows **Spend PM = 0.00**  (likely “previous month spend”).
- This often indicates **a DAX logic issue**, incorrect filter context, or missing handling for BLANK/0.

-> **Fix the PM measure** (time intelligence + BLANK/0 handling) to ensure the dashboard is decision-ready.

### 2️⃣ Units Price Basics

<img width="1236" height="701" alt="image" src="https://github.com/user-attachments/assets/a915f65f-ad10-4e0e-b56c-ff36f02d3028" />

### 📌 Key Findings : 
**1. Average Unit Price Level (Baseline)**

- The dashboard shows an overall **Avg Unit Price ~15.55** (top KPI).
- This provides a baseline to benchmark suppliers/SKUs and identify overpay areas.

-> **Pricing baseline is stable**, enabling consistent supplier/SKU comparisons.

**2. Ordered Quantity vs Average Price (Demand vs Price Behavior)**

- The combo chart indicates **ordered quantity trends upward over time**, while **average** unit price stays **relatively flat/slightly declining** across the period.
- This suggests volume growth without proportional price inflation.

-> **Volume increased while pricing stayed controlled**, which may reflect improved purchasing leverage or stable market pricing.

**3. Month-over-Month Price Change (Volatility & Spikes)**

- **The MoM** chart highlights clear price fluctuations, including **a major positive spike (~+27.9%)** in one month, followed by multiple negative months.
- Several consecutive decreases later in the year suggest a correction after the spike.

-> **Prices are generally stable but can spike sharply**, so exception monitoring is necessary.

**4. Price Gap / Best Price Benchmarking (Overpay Signal)**

- The presence of **a Price Gap** KPI and the table comparing **Avg Unit Price vs Best Unit Price (by SKU)** indicates systematic benchmarking.
- Rows where Avg > Best imply **potential overpay**, especially if they occur on high-volume SKUs.

-> **Overpay opportunities exist at SKU level**, and prioritization should be volume-weighted.

**5. Potential Savings Concentration (Supplier Focus)**

- The “Potential Savings by Supplier” treemap shows savings heavily concentrated in the **top suppliers (notably Fabrikam and Litware).**

-> **Negotiation impact is concentrated**: focusing on 1–2 major suppliers can unlock most savings.

**6. Data Quality / Measure Watch-outs (Best Unit Price = 0)**

- In the detail table, some suppliers show **Best Unit Price (by SKU) = 0**, which likely means missing data, unhandled blanks, or a measure logic issue.
- If not fixed, savings and price gap calculations can be distorted.

-> **Fix BLANK/0 handling for Best Price** to make savings estimates reliable.

### 3️⃣ Supplier Scorecard

<img width="1245" height="688" alt="image" src="https://github.com/user-attachments/assets/89d9a6ea-2ab7-450a-9f56-d8f26ccdd65e" />

### 📌 Key Findings : 

**1. Supplier Coverage and Overall Performance Snapshot**

- The scorecard covers **28 suppliers**, with total spend around **$2.17B** and overall **Avg Unit Price ~15.55.**
- The overall **Received / On-time rate** is **~99.7%**, indicating strong delivery reliability at the portfolio level.

-> At a high level, **supplier delivery performance is excellent**, so the biggest value likely comes from **cost/pricing optimization** rather than service recovery.

**2. Spend Concentration Across Suppliers**

- The donut chart and the supplier table show spend is highly concentrated in the top suppliers **(notably Fabrikam, Inc. and Litware, Inc.).**
- A small number of suppliers drive the majority of total spend.

-> **Supplier concentration remains a key risk and leverage point**—negotiations and governance should focus on the top spend suppliers first.

**3. Price Index (Best) and Price Gap by Supplier (Cost Competitiveness)**

- The “Supplier Price Index (Best)” bar chart benchmarks each supplier against **the best available price.**
- Suppliers with weaker indices (further from “best”) represent higher overpay potential, especially if they also carry large spend.

-> **Not all high-spend suppliers are cost-efficient**; combine **Spend × Price Index** to prioritize negotiation targets.

**4. Value Map: Price vs Service Trade-off**

- The value map positions suppliers by **Received Rate (service)** vs **Supplier Price Index (cost)**, with bubble size reflecting impact (spend).
- Suppliers in the “high service + good price” zone are strategic partners; those with “high service but poor price” are prime negotiation candidates.

-> This chart is a strong executive tool to **balance cost and reliability**, not just chase the lowest price.

**5. Supplier-Level Comparison Table (Decision-Ready Drill)**

- The table consolidates **Total Spend, Avg Unit Price, Best Spend, and Received Rate** per supplier.
- This enables fast triage: identify suppliers with **high spend + high avg price + low best spend share.**

-> The report is **actionable**, because it links benchmarking metrics to each supplier in one place.

**6. Metric Definition / Data Quality Watch-outs**

- Ensure “On-time % / Received Rate” is clearly defined (e.g., **Received Qty / Ordered Qty** or an on-time receipt flag).
- Also validate “Best Spend” and “Price Index (Best)” logic (BLANK/0 handling), since these directly affect prioritization.

-> **Clear metric definitions are critical**—these KPIs drive negotiation and vendor strategy decisions.

### 4️⃣ Lead Time & Delivery

<img width="1218" height="688" alt="image" src="https://github.com/user-attachments/assets/79aa9398-20f5-4fbe-9208-1972082eb5c1" />

### 📌 Key Findings : 

**1. Overall Delivery Reliability (Received Rate)**

- The headline KPI shows **Received Rate ~99.7%**, indicating strong fulfillment performance overall.
- This suggests the procurement operation is generally meeting service expectations.

-> **Service level is consistently high**, so the main opportunity is to maintain reliability while optimizing cost and supplier mix.

**2. Ordered vs Received Quantity (Scale)**

- KPIs show Ordered Qty **~10M** and **Received Qty ~10M**, implying minimal loss between ordered and received volumes.
- **PO Count ~2K** provides context for workload and operational throughput.

-> The process appears **highly controlled operationally**, with near-complete fulfillment against ordered volume.

**3. Yearly Trend: Volume Growth + Service Dip Signal**

- The yearly chart shows ordered volume rising from **~0.7M (2013)** to **~2.4M (2014)** and peaking around **~4.6M (2015)**, then dropping to **~2.6M (2016)**.
- Received Rate stays at/near 100% for earlier years, but **drops to ~99.0% in 2016.**

-> **2016 is a delivery risk signal** (even a ~1% drop can be material at high volume); it’s worth investigating supplier-level drivers.

**4. Quarterly Pattern: Q3 Weakness**

- The quarter chart shows a clear dip in **Q3** (both ordered and received quantities), followed by a rebound in **Q4**.
- This suggests either seasonal demand patterns or operational constraints mid-year.

-> **Q3 is the “stress point”**; align capacity planning and supplier readiness before Q3 to prevent service slippage.

**5. Supplier Comparison: Who Drives the Received Rate?**

- The treemap and table break down received rate by supplier across years.
- Most suppliers are around 100%, but small deviations (e.g., **Fabrikam ~99.76%, Litware ~99.71%)** matter more because they typically carry large volume/spend.

-> Focus improvement on **high-volume suppliers**, not just the lowest-performing ones, to maximize impact.

**6. Data / Definition Check (Delivery vs “On-time”)**

- This page uses **Received Rate** (likely Received Qty / Ordered Qty). If you also track “On-time %”, clarify the definition and whether it’s separate from received rate.

-> **Define delivery KPIs explicitly** (Received vs On-time) to avoid misinterpretation in exec reviews.


## 🔎 Final Conclusion & Recommendations  

| Aspect | Insight | Recommendation |
|---|---|---|
| **Spend Concentration & Supplier Dependency** | Total purchasing spend scaled up to **~$2.17B**, but most spend is concentrated in top suppliers (notably **Fabrikam & Litware**), increasing dependency and negotiation risk. | Set supplier concentration targets/caps, qualify backup suppliers for critical SKUs, and run quarterly sourcing reviews to reduce single-supplier exposure. |
| **Unit Price Control & Savings Opportunity** | Overall **Avg Unit Price ~15.55** is stable, but SKU-level **price gaps vs Best Unit Price** create meaningful **potential savings**, largely driven by major suppliers. | Apply a price governance rule (e.g., cap at **Best + 5%**), prioritize negotiation on **top spend + high price-gap SKUs**, and track savings monthly. |
| **Delivery Reliability & Emerging Risk Signa**l | Delivery performance is strong (**~99.7% received rate**), but there is a dip in the latest year and a visible **Q3 weakness**, suggesting seasonal/capacity strain. | Set exception alerts (e.g., Received/On-time < 99%), investigate Q3 drivers, and align PO planning + supplier capacity ahead of peak periods. |
| **Data Quality & Metric Reliability** | Some measures show potential issues (e.g., **PM metric = 0**, **Best Unit Price = 0/blank**), which can distort price-gap and savings conclusions. | Fix DAX logic and BLANK/0 handling, standardize KPI definitions (Received vs On-time), and add a data quality checklist/page for KPI trust. |









