# Uber Trip Analysis Dashboard (Power BI)

## Project Overview
Developed a comprehensive Power BI Dashboard to analyze Uber trip data with the goal of uncovering trends related to bookings, revenue, trip efficiency, and location-based demand, aiding data-driven decisions for stakeholders.

---

## Problem Statement (Mapped to Implementation)

### Dashboard 1: Overview Analysis

#### KPIs Implemented
- **Total Bookings:** Derived from row count of trip records; uses DAX measure aggregating TripID.  
- **Total Booking Value:** DAX sum of fare_amount, reflecting total revenue.  
- **Average Booking Value:** Average of fare_amount per trip.  
- **Total Trip Distance:** Summed trip_distance values.  
- **Average Trip Distance:** Average trip_distance across all trips.  
- **Average Trip Time:** Used DATEDIFF DAX for pickup to drop-off intervals; presented in minutes.  

#### Expected Outcomes (Verified and Expanded)
- Accurately identified both booking and revenue growth trends by date, city, vehicle, and payment type.  
- Demonstrated trip efficiency with KPIs for distance and duration; comparisons shown for multiple vehicle segments.  
- Provided time-based breakdowns (with slicers) for adaptive pricing and operational planning.  
- Generated insights to optimize surge pricing, premium vehicle deployment, and improve customer satisfaction via location hotspots and efficiency tracking.  

#### Features Delivered
- Interactive measure selector using a disconnected table, enabling users to toggle dynamically between Total Bookings, Booking Value, and Trip Distance—all charts update responsively.  
- Dynamic Chart Titles based on selected metric.  
- Slicers for time periods, city selection; advanced tooltips showing context KPIs.  
- Vehicle Type Analysis via grid/matrix view, incorporating conditional formatting, sorting/filtering, and “TopN” DAX logic to highlight segment leaders and low performers.  
- Bookings by day visualizations (area and line charts), peak/off-peak analysis including overlays for holidays/events/severe weather flagged in tooltips or comments.  

---

### Location Analysis

#### Implemented Analyses
- **Most Frequent Pickup Point:** LocationID mode and TopN logic—supports driver allocation and pricing strategies.  
- **Most Frequent Drop-off Point:** Requires DAX USERELATIONSHIP to switch from active to inactive relationship between trip and location tables for true drop-off analytics.  
- **Farthest Trip:** Identified using MAX(Distance), flagged in tooltip for outlier and fare optimization.  
- **Top 5 Locations (Bookings):** Highlighted with RANKX on locations table.  
- **Vehicle Preference by Pickup Location:** Utilized filters on both vehicle type and locationID for segmented optimization.  

#### Other Enhancements Delivered
- **Data Details bookmark:** Pop-up with glossary of KPI metrics, table descriptions, data source info.  
- **“Clear Filters” button:** For immediate slicer reset and UX enhancement.  
- **Raw Data Export button:** Leveraging Power BI native export for independent analysis.  

---

### Dashboard 2: Time Analysis

#### Global Dynamic Measure Selector
- Unified slicer updates for all time-driven charts (by hour, weekday, 10-min interval).  

#### Visualizations
- **By Pickup Time (10-min intervals):** Area chart revealing granular peak periods.  
- **By Day Name:** Line chart showing weekly variability and the impact of weekends/holidays.  
- **By Hour × Day (Heatmap):** Matrix grid visualizes demand density across days/hours, highlights commuter and event-driven spikes.  

---

### Dashboard 3: Details Tab (Drillthrough)

- **Grid Table:** Displays all trip records, enables direct drill-through from any summary chart for root-cause and granular investigations.  
- **Bookmark:** Allows toggle between filtered (drill-through) view and full trip dataset—supports transparency and deep dive analysis.  

---

## Key Insights (Extracted Directly from Analysis)
- **Booking Trends:** Growth in ride bookings during peak commuting hours (especially 8 AM – 6 PM) and weekends, with Saturday/Sunday marked for promotional focus.  
- **Revenue Generation:** Surge pricing contributed a dramatic spike to overall revenues, especially during late evening and holiday periods.  
- **Trip Efficiency:** UberXL vehicles yielded highest average trip distances; UberX cars led for booking count and trip volume.  
- **Location Hotspots:** Penn Station and Madison Square West flagged as top pickup zones; Upper East Side North emerged as most frequent drop-off.  
- **Outlier Detection:** Longest trip was over 144 miles; flagged for special fare optimization analysis.  
- **Segmented Vehicle Demand:** UberX was preferred across most zones, but Uber Black and Comfort were more prevalent in premium neighborhoods and airport routes.  
- **Payment Preferences:** Shift from cash to digital payments (Amazon Pay, Uber Pay, Google Pay) in urban zones, with night rides more likely paid in cash.  
- **Day/Night Split:** 65% of rides occurred during daytime hours, suggesting staffing and promotional efforts should align with demand cycles.  
- **Use of DAX & Modeling:** Advanced DAX (USERELATIONSHIP for switching active/inactive table joins, RANKX for leaderboards, CONCATENATEX for dynamic titles) allowed deep customization and versatility for business reporting.  
- **UX/Reporting:** Export and clear-filter features, detailed bookmarks for definitions—all implemented for user accessibility and smooth stakeholder reporting.

**Project Learning Note:**  
This project was developed using a guided dataset and problem statement for learning purposes. All implementation steps were completed independently—from importing and cleaning the dataset, to building the data model, writing DAX measures, and designing the dashboards. While the problem statement provided the overall structure, all visuals, KPIs, and interactivity in Power BI were created by me. Through this process, I gained hands-on experience with:  

- **Data Importing & Cleaning:** Handling real-world data inconsistencies and preparing datasets for analysis.  
- **Data Modeling:** Creating relationships, managing active/inactive relationships, and structuring data for efficient reporting.  
- **DAX Measures:** Writing advanced DAX formulas for dynamic calculations, aggregations, and conditional metrics.  
- **Dashboard Design & Interactivity:** Building responsive visuals, interactive slicers, dynamic chart titles, bookmarks, and drill-through functionalities.  
- **Analytical Thinking:** Translating business questions into measurable KPIs and actionable insights.  
- **Reporting Best Practices:** Designing dashboards for clear communication to stakeholders, ensuring usability and data-driven decision support.  
- **Hands-on Power BI Experience:** Practicing end-to-end dashboard development—from raw data to advanced analytics—strengthening confidence in building professional reports independently.
