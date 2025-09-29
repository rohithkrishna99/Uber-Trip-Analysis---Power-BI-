# 🚖 Uber Trip Analysis – Power BI Project  

## 🔹 Project Overview  

This project is a real-time Uber Trip Analysis built in Power BI to provide business intelligence insights for stakeholders. The dataset covers 103,000+ trips from New York City (June 2024) and was modeled, transformed, and visualized using Power BI best practices.  

The project simulates a real-world scenario where Uber operations teams need to monitor:  

- Trip demand patterns,  
- Revenue performance,  
- Trip efficiency (time & distance), and  
- High-demand locations.  

The deliverable includes three dashboards:  

- **Overview Analysis** – Business-level KPIs & high-level summaries.  
- **Time Analysis** – Demand fluctuations across hours, days, and weeks.  
- **Details Tab** – Record-level insights with drill-through and export capabilities.  

---

## 🔹 Data Preparation & Modeling  

**Data Sources Used:**  
- **Trip Details Table** (103,728 rows, 11 columns) containing fields like Pickup Time, Drop-off Time, Passenger Count, Distance, Fare, Surge Fee, Vehicle Type, Payment Type.  
- **Locations Table** with pickup & drop-off zone mappings (used for relationships).  

**Modeling Approach:**  
- Designed a star schema with Trip Details as fact table and Locations as dimension.  
- Managed both active (pickup) and inactive (drop-off) relationships.  
- Used `USERELATIONSHIP()` in DAX to activate drop-off relationships only when needed.  
- Built a Calendar table for time-based slicing & filtering.  

**Key Transformations & Enrichments:**  
- Created calculated columns for Day/Night classification, Trip Duration, Weekday/Weekend segmentation.  
- Implemented a Measure Selector (Disconnected Table) for dynamic KPIs across dashboards.  
- Applied Dynamic Titles for auto-contextual chart headers.  

---

## 🔹 Dashboard 1: Overview Analysis  

### KPIs Implemented  
- Total Bookings – Count of all trips.  
- Total Booking Value – Sum of Fare + Surge Fee.  
- Average Booking Value – Revenue per ride.  
- Total Trip Distance – Aggregate miles traveled.  
- Average Trip Distance – Avg. ride length per booking.  
- Average Trip Time – Avg. ride duration in minutes.  

### Visualizations & Features  
- **Payment Type Analysis** – Donut chart (Cash vs Card vs Wallet).  
- **Trip Type (Day/Night) Analysis** – DAX-driven classification based on pickup time.  
- **Vehicle Type Analysis** – Matrix view comparing KPIs across UberX, UberXL, Uber Green, Comfort, Black. Conditional formatting highlighted top/bottom performing vehicle types.  
- **Bookings by Day** – Area chart tracking daily demand & fluctuations.  

**Location Insights:**  
- Most Frequent Pickup: Penn Station (Madison Square)  
- Most Frequent Drop-off: Upper East Side North  
- Farthest Trip: Lower Side → Crown Heights North (144 miles)  
- Top 5 Pickup Locations by bookings.  
- Most Preferred Vehicle at Pickup Points.  

### Enhancements  
- Dynamic KPIs & Titles – Switch measures & update visuals instantly.  
- Interactive Slicers – By Date, City, and Vehicle Type.  
- Clear Filters Button – Reset dashboard in one click.  
- Bookmarks – Open Data Dictionary view explaining tables & metrics.  

### Business Value  
- Identified Penn Station as the busiest hub – opportunity to station drivers nearby.  
- Discovered that UberX dominates demand, but premium vehicles (Black/Comfort) generate higher average fares → supports tiered pricing strategies.  
- Day/Night split analysis showed night trips contribute ~30%, reinforcing need for late-night driver incentives.  
- Farthest trips (long-distance outliers) help refine surge pricing models and fuel/maintenance cost analysis.  

---

## 🔹 Dashboard 2: Time Analysis  

### Dynamic Measures (Global Selector)  
- Total Bookings  
- Total Booking Value  
- Total Trip Distance  

### Visualizations  
- **Pickup Time (10-minute intervals)** – Area chart across 24 hours. Identified peak demand during 7–9 AM and 5–8 PM commute hours.  
- **Day of Week Analysis** – Line chart showing weekends (Saturday/Sunday) as highest demand.  
- **Heatmap (Hour × Day)** – Matrix grid highlighting:  
  - Weekday rush hours (commuting patterns).  
  - Weekend late-night spikes (leisure trips).  

### Business Value  
- Helps align driver shifts with peak intervals.  
- Identifies weekend premium windows for higher fares.  
- Time insights support dynamic pricing models → higher fares during high demand hours.  
- Provides Uber operations with evidence for surge fee justification.  

---

## 🔹 Dashboard 3: Details Tab  

### Features  
- Grid View – Shows complete trip-level records.  
- Drill-through – From Overview/Time dashboards to details for deeper insights.  
- Full Data Bookmark – Switch between filtered drill-through & full dataset.  
- Export Options – Allows CSV/Excel downloads for further offline analysis.  

### Business Value  
- Builds transparency with stakeholders.  
- Supports ad-hoc investigations (e.g., verifying high surge trips or long-duration rides).  
- Makes dashboards audit-friendly by showing raw trip records.  

---

## 🔹 Key Insights from Uber Trip Analysis  

### Demand Concentration & Location Hotspots  
- Penn Station emerged as the busiest pickup point, confirming it as a high-frequency hub for both commuters and tourists.  
- The Upper East Side North dominated as the top drop-off point, overlapping with frequent pickup activity.  
- Two-way demand corridors (Penn Station ↔ Upper East Side) were detected, which minimize driver idle time and support efficient fleet positioning.  

### Day vs. Night Split  
- 70% of trips occur during the day, aligning with office commutes and mid-day errands.  
- 30% of trips happen at night, which, although smaller in volume, show higher average fares due to surge pricing and longer ride distances.  
- **Business Implication** → Strong case for late-night driver incentives and safety-focused features.  

### Outlier Detection  
- The farthest trip logged was 144 miles (Lower Side → Crown Heights North), far above the average trip length.  
- A small cluster of extreme long-distance rides significantly increases revenue but distorts average KPIs.  
- **Recommendation** → Segment reporting into short-haul (0–10 mi), mid-haul (10–30 mi), long-haul (30+ mi) for clearer performance tracking.  

### Payment Preferences  
- Card payments dominate, but cash transactions still account for a sizable share.  
- Digital wallets (Uber Pay, Amazon Pay) show adoption, but penetration remains lower.  
- **Business Implication** → Uber can incentivize digital payments (discounts, reward points) to reduce cash handling risks and improve transaction speed.  

### Trip Efficiency  
- Average trip distance: ~6–7 miles.  
- Average trip time: ~18–22 minutes.  
- Efficiency metrics help establish baselines for driver performance monitoring and customer experience benchmarking.  

### Revenue Optimization by Vehicle Type  
- UberX contributes the highest booking volume but yields the lowest average revenue per trip.  
- Uber Black & Comfort serve fewer trips but generate 2–3x higher booking value per ride.  
- **Business Implication** → Supply-demand balance between budget vs. premium vehicles is crucial for maximizing profit margins.  

### Time-Based Demand Patterns  
- Peak Hours: 7–9 AM & 5–8 PM (commute).  
- Weekend Peaks: Higher demand late nights (Fri–Sun).  
- **Recommendation** → Use time-based dynamic pricing and driver shift alignment to maximize availability and minimize unfulfilled ride requests.  

### Booking Trends Over the Month  
- Daily bookings showed a gradual upward trend throughout June 2024, reflecting increased adoption.  
- A few mid-week dips indicate lower business activity vs. weekend spikes.  
- **Insight** → Helps Uber anticipate seasonality and weekday-weekend demand shifts.  

### Customer Behavior & Preferences  
- Higher multi-passenger trips on weekends point to leisure/social rides.  
- Weekday trips mostly single-passenger commutes.  
- **Suggestion** → Uber could bundle promotions for group trips during weekends to maximize utilization.  

## Project Learning & Takeaways
This project was developed using a guided dataset and problem statement for learning purposes. All implementation steps were completed independently—from importing and cleaning the dataset, to building the data model, writing DAX measures, and designing the dashboards. While the problem statement provided the overall structure, all visuals, KPIs, and interactivity in Power BI were created by me. Through this process, I gained hands-on experience with:  

- **Data Importing & Cleaning:** Handling real-world data inconsistencies and preparing datasets for analysis.  
- **Data Modeling:** Creating relationships, managing active/inactive relationships, and structuring data for efficient reporting.  
- **DAX Measures:** Writing advanced DAX formulas for dynamic calculations, aggregations, and conditional metrics.  
- **Dashboard Design & Interactivity:** Building responsive visuals, interactive slicers, dynamic chart titles, bookmarks, and drill-through functionalities.  
- **Analytical Thinking:** Translating business questions into measurable KPIs and actionable insights.  
- **Reporting Best Practices:** Designing dashboards for clear communication to stakeholders, ensuring usability and data-driven decision support.  
- **Hands-on Power BI Experience:** Practicing end-to-end dashboard development—from raw data to advanced analytics—strengthening confidence in building professional reports independently.
