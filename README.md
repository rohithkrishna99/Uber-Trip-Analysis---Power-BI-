# 🚖 Uber Trip Analysis – Power BI Project

## 🔹 Project Overview
This project is a **real-time Uber Trip Analysis** built in **Power BI** to provide **business intelligence insights** for stakeholders.  

- **Dataset**: 103,000+ trips from New York City (June 2024)  
- **Objective**: Monitor trip demand, revenue performance, trip efficiency, and high-demand locations  
- **Deliverables**: Three interactive dashboards  
  1. **Overview Analysis** – Business-level KPIs & high-level summaries  
  2. **Time Analysis** – Demand fluctuations across hours, days, and weeks  
  3. **Details Tab** – Record-level insights with drill-through and export capabilities  

---

## 🔹 Data Preparation & Modeling
**Data Sources Used**
- **Trip Details Table** (103,728 rows, 11 columns): Pickup Time, Drop-off Time, Passenger Count, Distance, Fare, Surge Fee, Vehicle Type, Payment Type.  
- **Locations Table**: Pickup & drop-off zone mappings.  

**Modeling Approach**
- Designed a **star schema** with Trip Details as fact table and Locations as dimension.  
- Managed both active (pickup) and inactive (drop-off) relationships.  
- Used `USERELATIONSHIP()` in DAX for drop-off analysis.  
- Built a **Calendar table** for time-based slicing & filtering.  

**Key Transformations & Enrichments**
- Calculated columns for **Day/Night classification**, **Trip Duration**, and **Weekday/Weekend segmentation**.  
- Implemented a **Measure Selector (Disconnected Table)** for dynamic KPIs.  
- Applied **Dynamic Titles** for context-aware chart headers.  

---

## 🔹 Dashboard 1: Overview Analysis

### KPIs Implemented
- Total Bookings  
- Total Booking Value (Fare + Surge Fee)  
- Average Booking Value  
- Total Trip Dis
