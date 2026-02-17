# 📊 NTPC Operational Efficiency Analysis (2017–2026)

---

<p align="center">
  <em>A Comprehensive Performance Study of NTPC Power Stations</em>
</p>

---

## 📋 Table of Contents

- [📊 NTPC Operational Efficiency Analysis (2017–2026)](#-ntpc-operational-efficiency-analysis-20172026)
  - [📋 Table of Contents](#-table-of-contents)
  - [1. Project Overview](#1-project-overview)
    - [🎯 Focus Areas](#-focus-areas)
  - [2. Tools Used](#2-tools-used)
  - [3. Objective](#3-objective)
  - [4. Dataset Information](#4-dataset-information)
    - [📊 Key Columns](#-key-columns)
    - [⚠️ Data Issues Identified](#️-data-issues-identified)
  - [5. Data Preparation Process](#5-data-preparation-process)
    - [📋 Process Steps](#-process-steps)
  - [6. Key KPIs Created](#6-key-kpis-created)
    - [1️⃣ Capacity Utilization (%)](#1️⃣-capacity-utilization-)
    - [2️⃣ Outage Flag](#2️⃣-outage-flag)
    - [3️⃣ Low Coal Flag](#3️⃣-low-coal-flag)
    - [4️⃣ Generation Gap](#4️⃣-generation-gap)
  - [7. Analysis \& Findings](#7-analysis--findings)
    - [7.1 Overall Utilization](#71-overall-utilization)
    - [7.2 Gas-Based Plants](#72-gas-based-plants)
    - [7.3 Coal-Based Plants](#73-coal-based-plants)
    - [7.4 Impact of Outages](#74-impact-of-outages)
    - [7.5 Year-wise Trend](#75-year-wise-trend)
  - [8. Station Ranking (Inefficiency Score)](#8-station-ranking-inefficiency-score)
  - [9. Strengths of This Project](#9-strengths-of-this-project)
  - [10. Areas for Improvement](#10-areas-for-improvement)
    - [1️⃣ Root Cause Analysis](#1️⃣-root-cause-analysis)
    - [2️⃣ Financial Impact Analysis](#2️⃣-financial-impact-analysis)
    - [3️⃣ Predictive Modeling](#3️⃣-predictive-modeling)
    - [4️⃣ Dashboard Deployment](#4️⃣-dashboard-deployment)
  - [11. Limitations](#11-limitations)
  - [12. Conclusion](#12-conclusion)
  - [13. Future Scope](#13-future-scope)

---

## 1. Project Overview

This project analyzes the operational performance of NTPC power stations between **2017** and **early 2026**. The main goal was to understand why some stations perform efficiently while others struggle.

> **Methodology:** All data analysis was performed using **Google Sheets**. Because the dataset was very large, we used **Google Colab (Python)** only to randomly shorten (sample) the dataset so that it could be handled smoothly. Version control and file tracking were managed using **Git**.

### 🎯 Focus Areas

| Area | Description |
|------|-------------|
| 🔌 Capacity Utilization | Measuring how effectively installed capacity is used |
| ⚠️ Outages | Tracking downtime and its impact on performance |
| �ite Coal Stock | Monitoring fuel inventory levels |

The approach was **practical** and **operations-focused** rather than overly technical.

---

## 2. Tools Used

<div align="center">

| Tool | Purpose |
|------|---------|
| 📗 **Google Sheets** | Data cleaning, KPI calculations, pivot tables, charts and comparisons |
| 🐍 **Google Colab** | Random sampling of large dataset, exporting reduced dataset |
| 📦 **Git** | Version control, tracking file changes, maintaining organized structure |

</div>

> **Note:** No advanced machine learning tools were used. The analysis was **logic-based** and **KPI-driven**.

---

## 3. Objective

The main objectives were:

1. 🔍 **Identify** underperforming stations
2. 📈 **Understand** key performance drivers
3. ⚖️ **Compare** coal-based and gas-based plants
4. 📅 **Analyze** trends across years
5. 💡 **Provide** realistic recommendations

---

## 4. Dataset Information

The dataset contains approximately **7,500 rows** covering **41 NTPC stations** from 2017 to 2026.

### 📊 Key Columns

| Column | Description |
|--------|-------------|
| Date | Record date |
| Station Name | NTPC power station name |
| State | Location state |
| Monitored Capacity (MW) | Installed capacity |
| Available Capacity (MW) | Capacity available for generation |
| Actual Generation (MU) | Actual electricity produced |
| Planned Generation (MU) | Target generation |
| Coal Stock (Days) | Days of coal inventory |
| Capacity Under Outage (MW) | Capacity offline due to issues |

### ⚠️ Data Issues Identified

- ❌ Approximately **27%** coal stock values were missing (mostly gas plants)
- ❌ Some unrealistic values (example: coal stock = 1517 days)
- ❌ No detailed maintenance logs available
- ❌ Some generation entries appeared inconsistent

> **Approach:** We avoided guessing missing values and only corrected clearly incorrect entries.

---

## 5. Data Preparation Process

Since the dataset was large, we first used **Google Colab** to randomly sample the data so it could be analyzed efficiently in Google Sheets.

### 📋 Process Steps

| Step | Action |
|------|--------|
| 1️⃣ | Import dataset into Google Colab |
| 2️⃣ | Random sampling to reduce dataset size |
| 3️⃣ | Remove impossible values |
| 4️⃣ | Standardize date formats |
| 5️⃣ | Filter out rows with zero monitored capacity |
| 6️⃣ | Create calculated KPI columns |
| 7️⃣ | Use pivot tables to summarize results |

All calculations were done using **Google Sheets formulas**.

---

## 6. Key KPIs Created

### 1️⃣ Capacity Utilization (%)

```
Capacity Utilization = (Available Capacity / Monitored Capacity) × 100
```

> This shows how much of installed capacity is actually used.

---

### 2️⃣ Outage Flag

```
If Capacity Under Outage > 0 → Outage = 1
Else → Outage = 0
```

> Used to measure outage frequency.

---

### 3️⃣ Low Coal Flag

```
If Coal Stock < 7 days → Low Coal = 1
```

> Used to identify risky coal levels.

---

### 4️⃣ Generation Gap

```
Generation Gap = Actual Generation − Planned Generation
```

> Used to check if targets were met.

---

## 7. Analysis & Findings

### 7.1 Overall Utilization

| Metric | Value |
|--------|-------|
| Average Capacity Utilization | **~80%** |

> This indicates stable performance but with clear inefficiencies.

---

### 7.2 Gas-Based Plants

| Observation | Details |
|-------------|---------|
| Utilization | Very low |
| Main Reason | Gas supply shortages |
| Issue | Idle installed capacity |

> This is primarily a **fuel availability issue** rather than equipment efficiency.

---

### 7.3 Coal-Based Plants

| Finding | Implication |
|---------|-------------|
| Stations near coal mines had higher utilization | Supply chain location plays a major role |
| Fewer disruptions | Proximity to fuel source improves reliability |

---

### 7.4 Impact of Outages

| Relationship | Conclusion |
|--------------|------------|
| Outage Frequency ↔ Capacity Utilization | **Strong negative correlation** |
| When outages increase | Performance drops significantly |

> **Outages appear to be the biggest driver of inefficiency.**

---

### 7.5 Year-wise Trend

| Year | Performance |
|------|-------------|
| 2020 | Noticeable decline (COVID-related disruptions) |
| 2022+ | Performance improved |

---

## 8. Station Ranking (Inefficiency Score)

We created a **composite score** based on:

| Factor | Weight |
|--------|--------|
| Capacity underuse | 35% |
| Outage frequency | 35% |
| Low coal frequency | 30% |

> **Higher score = Worse performance**

This helped identify consistently underperforming stations.

---

## 9. Strengths of This Project

✅ Clear KPI-based framework  
✅ Practical business focus  
✅ Proper data cleaning steps  
✅ Logical ranking approach  
✅ Clear separation of coal and gas plants  
✅ Version control maintained using Git

---

## 10. Areas for Improvement

### 1️⃣ Root Cause Analysis

> We identified outages but did not have detailed maintenance logs to understand exact causes.

---

### 2️⃣ Financial Impact Analysis

We did not calculate:

- 💰 Revenue loss due to outages
- 💰 Cost of idle gas capacity
- 💰 Cost impact of low coal stock

> Adding financial metrics would strengthen the analysis.

---

### 3️⃣ Predictive Modeling

Future work could include:

- 🔮 Outage prediction models
- 🔮 Coal shortage forecasting

> This would make the project more advanced.

---

### 4️⃣ Dashboard Deployment

A live dashboard using **Power BI** or **Streamlit** could make this industry-ready.

---

## 11. Limitations

| Limitation | Impact |
|------------|--------|
| Missing coal stock data | Incomplete fuel analysis |
| No maintenance records | Limited root cause analysis |
| Sampled dataset | May not represent full population |
| Some inconsistent values | Potential data quality issues |

> All conclusions are based on the available sampled dataset.

---

## 12. Conclusion

| Key Finding | Details |
|-------------|---------|
| 🔴 Primary Factor | Outages are the main issue affecting plant performance |
| 🟢 Coal Plants | Perform better when near fuel sources |
| 🟡 Gas Plants | Underutilized mainly due to supply issues |

> Improving outage management and maintenance practices can significantly improve efficiency **without new infrastructure investment**.

---

## 13. Future Scope

- 📝 Integrate maintenance logs
- 💹 Add cost-based KPIs
- 🤖 Build predictive models
- 📊 Develop interactive dashboards

---

<p align="center">
  <strong>--- End of Report ---</strong>
</p>

<p align="center">
  <em>Project completed using Google Sheets, Google Colab, and Git</em>
</p>


