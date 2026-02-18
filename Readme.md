# Performance & Reliability Audit of NTPC Thermal Power Stations

## 📌 Project Overview
**Sector:** Energy & Power Utilities  
**Institute:** Newton School of Technology  
**Faculty Mentor:** Archit  

This project conducts a comprehensive operational audit of National Thermal Power Corporation (NTPC) stations using a dataset of **7,500 records** spanning **2017–2026**. The analysis reveals a critical efficiency gap where the fleet operates at an average **Daily Capacity Factor (DCF) of 65.9%**, significantly trailing top performers. 

The audit identifies a massive **607,137 MW cumulative outage volume**, translating to a potential revenue loss of over **₹580 Crores**. The project provides a 7-point KPI framework and actionable recommendations to bridge the gap between Monitored and Available Capacity.

### 👥 Team Details (Section-D/G-17)
* **Mansi Agarwal**
* **Aditya Samadhiya**
* **Kapish Rohilla**
* **Deepanshu**
* **Prashant Pandey**
* **Harshit Kudhial**

---

## 📊 KPI Framework & Scorecard
The analysis is anchored on **7 Core KPIs** developed to assess fleet health:

| Metric | Value | Description |
| :--- | :--- | :--- |
| **Total Power Generation** | **49,620.6 MU** | Total energy delivered to the grid. |
| **Avg Daily Capacity Factor** | **65.9%** | Efficiency score (Actual Generation vs. Potential). |
| **Total Outage Volume** | **607,137 MW** | Cumulative capacity lost to technical/maintenance issues. |
| **Monitored Capacity** | **3,033,314 MW** | Theoretical maximum installed capacity. |
| **Available Capacity** | **2,426,176 MW** | Actual capacity ready for generation. |
| **High Capacity Share** | **26.97%** | Fleet reliance on top-performing assets. |
| **Zero Gen Events** | **70** | Critical failure events where units produced 0 MW. |

---

## 📂 Data Dictionary
**Source:** NDAP - Government of India  
**Volume:** 7,500 rows, 16 columns  

| Column | Description |
| :--- | :--- |
| `Station_Clean` | Standardized power station name. |
| `Monitored Capacity` | Total installed capacity (MW). |
| `Available Capacity` | Capacity ready for generation (MW). |
| `Actual Generation` | Energy produced daily (Million Units - MU). |
| `Outage` | Capacity unavailable due to maintenance/faults (MW). |
| `Coal Stock` | Days of fuel inventory available. |
| `Daily_Capacity_Factor` | Calculated KPI: `(Generation / (Monitored * 0.024)) * 100`. |
| `Zero_Gen_Flag` | Categorical flag detecting complete unit failure. |

---

# Data Cleaning & Preparation
Data was cleaned and transformed in **Google Sheets**, transitioning from `RawDataset.csv` to `Cleaned.csv`.
## Key Steps
- **Missing Values**
  - Coal Stock (2,042 missing) filled with `0` or `"Not Available"`.
  - Capacity under outage (7 nulls) replaced with `0`.
- **Outlier Handling**
  - Calculated `Daily_Capacity_Factor`.
  - Flagged values >100% or ~0% using `Zero_Gen_Flag`.
- **Transformations**
  - Standardized date formats.
  - Cleaned station names into `Station_Clean`.
- **Feature Engineering**
  - Created `Daily_Capacity_Factor`, `Capacity_Category` (High/Low), and `Zero_Gen_Flag`.
The final dataset (`Cleaned.csv`) is structured and ready for analysis.

---

## 💡 Key Insights
1.  **The Efficiency Gap:** There is an **11.8%** performance difference between the "High Capacity" segment and the rest of the fleet.
2.  **Asset Reliance:** Despite their efficiency, "High Capacity" units contribute only **26.97%** of the total generation share.
3.  **Regional Bottleneck:** **Uttar Pradesh** is the primary contributor to the outage volume, showing a disproportionately large "Outage" segment in stacked bar analysis.
4.  **Seasonal Vulnerability:** Generation drops by **~12%** in August, marking the lowest demand/efficiency window.
5.  **Benchmark:** *Talcher (Old) Unit 2* sets the operational standard with a **99.4% DCF**.

---

## Dashboard Summary
A comprehensive dashboard was built in **Google Sheets** using the cleaned dataset.
## Top KPI Strip
Displays 7 key metrics:
- **High Cap Share:** 26.97%
- **Total Generation:** 49,620.6
- **Average DCF:** 65.9%
- **Outage:** 607k
- **Available Capacity:** 2.4M
- **Monitored Capacity:** 3.0M
- **Zero Generation Events:** 70
## Visualizations
- **Year-wise Trend:** Line chart showing generation growth over time.
- **Month-wise Seasonality:** Column chart highlighting seasonal dips (notably August).
- **State-wise Performance:** Stacked bar chart comparing Monitored vs. Available Capacity.
- **Capacity Category Analysis:** Donut/Pie chart showing 26.97% High Capacity share.
- **Zero Generation & Outage:** Chart analyzing 70 critical failure events.
- **Station Performance:** Bar chart/table of top and bottom performing stations.
## Interactive Filters
- Year  
- Month  
- State  
- Station Name  
- Capacity Category  
The dashboard enables dynamic performance tracking and multi-level analysis.
