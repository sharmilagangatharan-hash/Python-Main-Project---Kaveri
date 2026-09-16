# Project Title
Cauvery Hydrological Data Analytics: Water Level, Flow & Reservoir Performance

# Water Level, River Flow, Reservoir & Agriculture Demand
* An end-to-end Data Analytics project that analyses hydrological and agricultural data from the Cauvery River Basin to understand water availability, reservoir performance, irrigation water deficits, and groundwater dependence.
* The project uses Python (Google Colab) for data cleaning, transformation and exploratory data analysis, and Power BI for data modelling, DAX calculations and interactive dashboard development.

# 📌 Project Overview
* The Cauvery River Basin experiences seasonal variations in water availability that can affect agricultural irrigation, particularly in downstream delta districts of Tamil Nadu.
* This project combines multiple datasets related to:
   - 💧 Water levels
   - 🌊 River discharge
   - 🏞️ Reservoir inflow, outflow and storage
   - 🌾 Agricultural water demand and supply
   - 🚰 Canal water supply
   - 💦 Groundwater extraction
* The analysis compares upstream Karnataka and downstream Tamil Nadu water availability and examines how water availability is connected with agricultural water stress.

# 🎯 Objective (Problem Statement)
The main objectives of this project are:
* To perform Exploratory Data Analysis (EDA) to identify flow patterns and storage trends across the two-state datasets.
* To clean, align dates, and transform hourly telemetry, daily discharge, and agricultural demand datasets for integrated analysis.
* To evaluate seasonal irrigation demand, water supply shortages, and groundwater reliance across Cauvery delta districts.
* To build time-series charts and comparison visualizations to analyse reservoir levels, discharge rates, and agricultural water supply deficits.
* To compare upper-basin reservoir storage in Karnataka with downstream water availability in Tamil Nadu.
* To analyse reservoir release schedules and identify opportunities to mitigate agricultural crop water deficits.

# 📊 Data Sources
The project uses data from the following sources:
* India Water Resources Information System (India-WRIS)
* Central Water Commission (CWC)
* National Water Data Portal (NWDP)
* Tamil Nadu agricultural data portals
## Data Period
* 2021–2026
## Domain
* Hydrology / Water Resource Management & Agriculture Analytics

# 📁 Datasets
The project combines four major datasets:
## 1. 💧 Water Level Data
* Contains information about water levels recorded at monitoring stations.
* Important columns include:
   - Station Name
   - State
   - District
   - Year
   - Water_Level_Meters
   - Latitude
   - Longitude

## 2. 🌊 River Discharge Data
* Contains information about daily river discharge.
* Important columns include:
   - Station
   - State
   - District
   - Date
   - Daily Discharge (m³/s)
   - Discharge Category
## 3. 🏞️ Reservoir Data
* Contains reservoir inflow, outflow and storage information.
* Important columns include:
   - Reservoir Name
   - State
   - Year
   - Inflow
   - Outflow
   - Storage_Percentage
## 4. 🌾 Agricultural Water Demand Data
* Contains agricultural water demand and supply information.
* Important columns include:
   - District
   - Season
   - Water_Demand_MCFT
   - Water_Supplied_MCFT
   - Water_Deficit_MCFT
   - Deficit_Percentage
   - Canal_Water_Supplied_MCFT
   - Groundwater_Extracted_MCFT

# 🛠️ Tools & Technologies
## Python (Google Colab):
* Data cleaning, transformation, exploratory data analysis (EDA), and preprocessing.
## Power BI:
* Data modelling, DAX measures, interactive dashboard creation, and data visualization.
## Excel:
* Initial data inspection and basic data transformation.

# 🔄 Data Preprocessing
* The datasets were cleaned and prepared before analysis.
* Main preprocessing steps:
    - Removed null values and handled missing data in key columns.
    - Standardized date formats.
    - Extracted Year, Month and Season.
    - Treated outliers in Inflow, Outflow and Discharge using a capping method.
    - Created additional analytical columns.
    - Created Season classification.
    - Created Basin Zone classification such as Upstream and Downstream.
    - Created Net Flow.
    - Created log transformations where required.
    - Merged and cleaned the four major datasets.
    - Created calculated classifications such as Storage Status and Discharge Category.

# 🧮 Data Modelling & DAX
* The Power BI data model uses dimension tables and fact tables to support analysis.
## Dimension Tables
     * Dim State
     * Dim Year
## Fact Tables
     * Water Level
     * River Discharge
     * Reservoirs
     * Agriculture
* Relationships were established between the fact tables and dimension tables using common fields such as State and Year.
## Key DAX Measures
* The project includes measures such as:
    - Average Storage %
    - Average Discharge
    - Average Water Level
    - Karnataka Retention %
    - Tamil Nadu Retention %
    - Upstream Storage %
    - Downstream Storage %
    - Total Water Deficit
    - Average Deficit %
    - Average Canal %
    - Average Groundwater %

# 📈 Power BI Dashboard
## Dashboard 1 – Cauvery Basin Water Status
* This dashboard focuses on the supply side of the Cauvery Basin.
### KPIs
    - Average Storage %
    - Average Discharge
    - Average Water Level
    - Retention %
### Visualizations
    - 📈 Water Level Trend by Year
    - 📊 Year-wise Average Discharge
    - 🔵 Inflow vs Outflow Scatter Chart
    - 🗺️ Cauvery River Flow Map
    - 🎛️ Year, State, Season and Basin Zone slicers
<img width="964" height="378" alt="image" src="https://github.com/user-attachments/assets/143c4f1a-8b00-487f-a7d4-26657d13b15c" />

### Interpretation
* **Storage & retention:** Karnataka retains water more consistently (0.64 vs 0.51 TN retention), showing upstream reservoirs hold back a larger share of inflow.
* **Water level:** Karnataka/Kerala stay flat and high (~683–711m) across all years, while Tamil Nadu stays far lower (155–227m) and dips sharply in 2023 — the clearest sign of the imbalance.
* **Discharge:** Basin discharge is falling and volatile (144→33→87 m³/s), directly limiting how much water can reach the delta.
* **Inflow-outflow & map:** Karnataka's reservoirs operate at higher volumes and sit upstream, confirming TN's supply is structurally dependent on upstream release timing, not local storage. The map represents the Cauvery River flow from Talacauvery towards Poompuhar.

## Dashboard 2 – Agricultural Water Stress & Deficit
* This dashboard focuses on the demand side of water management.
### KPIs
    - Total Water Deficit
    - Average Deficit %
    - Canal %
    - Groundwater %
### Visualizations
    - 🍩 Deficit Contribution by District
    - 🌳 Deficit by District and Season
    - 📊 Demand vs Supplied vs Groundwater
    - 🎯 Average Deficit %
    - 🎛️ Year, District, Season and Crop slicers
<img width="859" height="518" alt="image" src="https://github.com/user-attachments/assets/260bcb30-e6e7-4028-a655-d979a11b04bb" />

### Interpretation
* **Deficit by district:** Thanjavur (24.81%) and Nagapattinam (22.43%) carry the largest share of total water deficit, with Thiruvarur close behind — confirming the delta districts as the hardest-hit.
* **Deficit by season:** Samba shows by far the highest deficit percentage (~4.9%) across all districts, followed by Kuruvai — the two critical cropping seasons your project flagged as most stressed.
* **Demand vs supply trend:** Water demand consistently outpaces canal supply and groundwater extraction across 2022–2026, with the gap between demand and supply widening rather than closing.
* **Canal & groundwater reliance:** Avg Canal % (71.50%) still exceeds groundwater reliance (24.44%), but groundwater extraction by season (notably in Samba) shows it's filling in where canal supply falls short — the dependency your findings highlighted.

# 🔍 Key Insights
## 💧 Upstream vs Downstream
* Karnataka, which represents the upstream region, generally maintains higher reservoir storage compared with downstream Tamil Nadu.
## 🌾 Agricultural Water Deficit
* Significant water deficits are observed in Cauvery delta districts, particularly during important agricultural seasons such as Samba and Kuruvai.
## 💦 Groundwater Dependence
* Groundwater dependence has increased over the years to compensate for insufficient canal water supply.
## 📍 Affected Districts
* Thanjavur, Thiruvarur and Nagapattinam are among the districts identified as being more affected by water stress.

# 💡 Recommendations
* Based on the analysis, the project suggests:
   - Better timing of reservoir releases.
   - Improved coordination between upstream and downstream water management.
   - Monitoring seasonal agricultural water demand.
   - Reducing excessive dependence on groundwater.
   - Using data-driven reservoir release planning to help reduce downstream irrigation stress.

# 🧠 Analytical Approach
* The project follows four levels of analytics:
## 1. Descriptive Analytics
* Understand overall patterns in:
   - Storage
   - Discharge
   - Water levels
   - Agricultural deficits
## 2. Diagnostic Analytics
* Examine how upstream water retention may contribute to downstream irrigation stress.
## 3. Predictive Perspective
* Identify the potential long-term sustainability concerns associated with continued groundwater dependence.
## 4. Prescriptive Perspective
* Explore how better-timed reservoir releases could help reduce agricultural water stress.

# 🏁 Conclusion
* The analysis of Cauvery basin hydrological and agricultural data reveals a clear upstream-downstream imbalance.
* Karnataka generally maintains higher reservoir storage, while Tamil Nadu’s delta districts face recurring irrigation deficits, especially during critical cropping seasons.
* Increasing dependence on groundwater highlights the need for better-timed and coordinated reservoir releases to improve agricultural water security in the downstream region.

# ⭐ Project Highlights
* **Domain:** Hydrology & Agriculture Analytics
* **Data Period:** 2021–2026
* **Tools:** Python | Google Colab | Excel | Power BI
* **Focus:** Water Availability | Reservoir Performance | Agricultural Deficit | Groundwater Dependence in TamilNadu
