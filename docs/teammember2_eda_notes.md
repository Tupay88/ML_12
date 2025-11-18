# TTC Streetcar Delay – EDA & Feature Engineering Review (Aman Kaushik)

## Overview
This document summarizes the exploratory data analysis (EDA) and feature engineering performed on the consolidated TTC Streetcar Delay dataset (2014–2025).  
The objective was to identify temporal, spatial, and operational patterns in the data and prepare a modeling-ready feature set for downstream classification tasks.

All analysis was conducted using the merged dataset `TTC_Streetcar_Delays_2014_2025.csv` produced by Team Member 1.

## Data Sources Used
- **Input File:** `TTC_Streetcar_Delays_2014_2025.csv`
- **Total Records:** ~93k (after cleaning)
- **Features Available:**
  - date, time, day, month, year, hour  
  - route/line, station, vehicle, bound  
  - incident (code), min_delay, min_gap  

Additional derived variables were created during EDA.


## EDA Objectives
1. Identify high-frequency incident types and operational bottlenecks.  
2. Detect temporal patterns (hourly, daily, monthly, yearly).  
3. Find route-level and location-level hotspots.  
4. Produce visualizations to support modeling and final reporting.  
5. Highlight risks such as class imbalance and missing values.


## Key EDA Findings

### **Incident Type Distribution**
- Four incident types dominate the dataset:  
  **General Delay**, **Mechanical**, **Investigation**, **Held By**.  
- These account for **over 70%** of all incidents, confirming **significant class imbalance**.  
- Rare classes (Overhead, Collision, Security, Special Event) appear <10%.

**Implication:**  
Models may disproportionately learn majority classes → requires class rebalancing or sampling strategies.


### **Temporal Patterns**

#### **Hourly Trends**
- Strong incident spikes observed during:
  - **Morning rush:** 5–7 AM  
  - **Evening rush:** 2–4 PM  
- Low incident activity overnight (1–4 AM).

#### **Daily / Weekly Trends**
- Weekdays show substantially higher activity than weekends.
- **Monday** and **Friday** are the most incident-heavy days.

#### **Monthly Trends**
- Incident counts peak in **September, October**, and **February**.
- Winter months show disruptions likely influenced by weather.

#### **Annual Trends**
- Total delay incidents increased post-2020, possibly due to:
  - ridership recovery
  - operational adjustments
  - aging fleet impacts

---

### **Route-Level Patterns**
- Routes **501 (Queen)**, **504 (King)**, and **506 (Carlton)** consistently show the highest incident volumes.
- Repeated hotspot intersections include:
  - **Broadview**
  - **Dundas West**
  - **Bathurst**
  - **King & Parliament**

**Implication:**  
These routes are priority candidates for targeted infrastructure upgrades and operational interventions.

---

## Visualizations Created (saved under `/reports/charts/eda/`)
1. `incidents_by_hour.png` – Hourly distribution of incidents.
2. `delays_by_dayofweek.png` – Weekday vs weekend comparison.
3. `top12_incident_type.png` – Most common incident types.
4. `route_time_heatmap.png` – Incidents by route and hour.

These visualizations were used directly in the presentation (see PPT). 


## CSV Files Produced
- `Cleaned_TTC_Streetcar_Delays_2014_2025.csv`
- `TTC_Feature_Engineered_2014_2025.csv`

These files include engineered variables needed for classification modeling.

## Feature Engineering Completed

### **Time-Based Features**
- Extracted: **year**, **month**, **dayofweek**, **hour**
- Derived: **is_weekend**, **is_morning_rush**, **is_evening_rush**

### **Delay Severity Categorization**
- Created `delay_bin` → {Low, Medium, High, Severe}

### **Categorical Encoding**
- One-hot encoded: **route**, **station**, **bound**, **vehicle**, **incident_type**

### **Interaction Features**
- Created `route_time_combo` to capture route-specific rush-hour behavior.

### **Missing Value Handling**
- Numeric fields: replaced NaN with 0  
- Categorical fields: replaced NaN with `"Unknown"`


## Risks Identified & Suggested Workarounds

### **1. Class Imbalance**
- Majority classes dominate the dataset  
**Workaround:**  
SMOTE, class weights, or downsampling.

### **2. Missing or Inconsistent Station Labels**
- Some stations appear with spelling variations or partial names.  
**Workaround:**  
Normalize using fuzzy matching or standardized lookup tables.

### **3. Weather & External Factors Not Included**
- Weather, traffic, construction could improve prediction accuracy.  
**Workaround:**  
Integrate open datasets (Environment Canada, Toronto Open Data).

### **4. Potential Overfitting with Many Encoded Features**
- One-hot encoding creates high dimensionality.  
**Workaround:**  
Use feature selection or model regularization.


## Additional Contribution
- Presented the final group PowerPoint during project presentation.  
- Communicated key EDA insights, engineered features, and problem framing for the modeling team.  
- Ensured consistency between visualizations, narrative, and final report.



## Handoff for Modeling
The cleaned and feature-engineered dataset is now ready for Member 3 (Antonio) to begin model training and optimization.

