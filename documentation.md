# ⚡ NTPC Operational Efficiency & Power Generation Analysis

> Data-driven operational performance study of NTPC thermal power stations (2017–2026)

---

## 📌 Project Overview

This project analyzes the operational efficiency of NTPC power stations using historical daily generation data.
The objective is to identify performance gaps, quantify outage impact, and recommend targeted improvements to recover lost generation and revenue.

The study transforms raw operational records into actionable business insights using KPI-based analysis and dashboard visualization.

---

## 🎯 Objectives

* Measure Daily Capacity Factor (DCF) across stations
* Identify underperforming units and regions
* Quantify outage-related generation loss
* Detect zero-generation anomalies
* Provide data-backed operational recommendations

---

## 🛠️ Tools & Technologies

| Tool                      | Purpose                                                             |
| ------------------------- | ------------------------------------------------------------------- |
| **Google Sheets**         | Data cleaning, KPI calculations, pivot analysis, dashboard creation |
| **Google Colab (Python)** | Random sampling of large dataset                                    |
| **Git**                   | Version control and structured workflow                             |

---

## 📂 Dataset Information

* **Source:** NTPC Daily Generation Reports (Government of India)
* **Records:** ~7,500
* **Columns:** 16
* **Time Period:** 2017–2026
* **Format:** Daily time-series station-level data

### Key Variables

* Monitored Capacity (MW)
* Available Capacity (MW)
* Actual Generation (MU)
* Capacity Under Outage (MW)
* Coal Stock (Days)

### Data Limitations

* 27% missing coal stock values
* Inconsistent raw date formats
* Partial 2026 data
* No detailed outage reason codes

---

## 🧹 Data Preparation

All cleaning and transformation were performed in **Google Sheets**.

### Cleaning Steps

* Standardized date formats
* Removed formatting inconsistencies
* Filled null outage values as 0
* Treated missing coal stock as 0 or Not Available
* Cleaned station names

### Feature Engineering

* **Daily Capacity Factor (DCF)**
* **Capacity Category (High / Low)**
* **Zero Generation Flag**

### Assumptions

* Blank outage implies zero outage
* Monitored capacity constant per day

---

## 📊 KPI Framework

### 1️⃣ Daily Capacity Factor (DCF)

```
DCF = (Actual Generation / (Monitored Capacity × 0.024)) × 100
```

Measures station efficiency.

---

### 2️⃣ Total Outage Impact

```
Sum of Capacity Under Outage (MW)
```

Quantifies reliability risk and generation loss.

---

### 3️⃣ Zero Generation Events

Days where Actual Generation = 0.

Identifies complete operational shutdowns.

---

### 4️⃣ Availability Factor

```
(Available Capacity / Monitored Capacity) × 100
```

Measures operational readiness.

---

## 🔍 Key Findings

### 📈 Efficiency Gap

| Segment       | Avg DCF |
| ------------- | ------- |
| High Capacity | 79.3%   |
| Low Capacity  | 67.5%   |

**Gap:** 11.8%

Performance issues are concentrated in specific assets.

---

### ⚠️ Outage Impact

* Total cumulative outage: ~607,137 MW
* Estimated generation loss: ~14,500 MU

---

### 🗺️ Regional Disparity

* Uttar Pradesh contributes ~23% of total outage volume
* Indicates regional operational inefficiency

---

### 🚨 Zero Generation Events

* 70 complete shutdown events
* Clustered in specific stations (e.g., Faridabad CCPP, Dadri CCPP)

---

### 🌦️ Seasonal Trend

* Peak: March–April
* Lowest: August (~12% lower than peak)

Suggests maintenance scheduling opportunity.

---

## 📊 Segmentation Insight

~98% of total outage volume originates from the **Low Capacity segment**.

Targeting the bottom-performing 25% of stations provides maximum improvement potential.

---

## 📈 Dashboard Overview

Interactive dashboard built in Google Sheets featuring:

* Top-line KPIs (Total Generation, Avg DCF, Total Outage MW)
* Year-over-Year trend analysis
* High vs Low capacity comparison
* State-wise outage heatmap
* Slicers (Year, Month, State, Station)

Designed for executive-level monitoring and quick decision-making.

---

## 💰 Impact Estimation

If outage volume reduces by 10%:

* Recovered Capacity ≈ 60,700 MW (daily cumulative)
* Energy Recovered ≈ 1,456 MU
* Financial Recovery ≈ ₹582 Crores (₹4 per unit)
* Fleet efficiency improvement ≈ 1–2%

---

## 🚀 Recommendations

### 1️⃣ Performance Turnaround Program

Focus on bottom 25% Low Capacity stations.

### 2️⃣ Regional Technical Audit (Uttar Pradesh)

Deploy dedicated audit team to diagnose equipment failures.

### 3️⃣ Zero-Generation Alert System

Mandatory Root Cause Analysis within 24 hours.

### 4️⃣ Optimize Maintenance Scheduling

Align major overhauls with August low-demand period.

---

## ⚠️ Limitations

* Missing coal stock data limits correlation depth
* No outage reason classification
* Assumed blank outage equals zero outage
* Partial dataset for 2026

---

## 🔮 Future Scope

* Predictive maintenance using sensor data
* Coal logistics risk modeling
* Financial KPI integration
* Real-time deployment dashboard

---

## 📌 Conclusion

Operational inefficiencies are concentrated within a specific low-capacity asset segment and regional cluster (Uttar Pradesh).
Targeted intervention can recover significant generation volume and potentially ₹500+ Crores in revenue, while improving grid reliability.

---

### 📁 Repository Structure

```
├── raw_data.csv
├── clean_data.csv
├── calculations_pivots.csv
├── dashboard.csv
└── README.md
```

---

### 👥 Team

Section-D / G-17
Newton School of Technology

---

**Project Type:** Data Analytics / Operations Optimization
**Domain:** Energy & Power Utilities