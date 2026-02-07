# Hotel Booking Analysis

## Project Background
Direct from the property management system (PMS) of this hotel conglomerate, the project contains information for city hotels in Lisbon, Portugal, and resort hotels in the Algarve Region, Portugal. Due to the identifiable nature of hotel bookings, the data has been anonymized, and the names of the customers andthe hotel conglomerate are not included. These were collected between the period of July 1st, 2015, and August 31st, 2017.

This conglomerate provides a significant amount of data on its booking durations, cancellations, marketing efforts, guest behavior, and guest make-up that have been previously underutilized in conversations about tourism behavior and hospitality. This project comprehensively analyzes and combines this data to uncover key observations that will elevate the conglomerate's guest experience and retention.

Insights and recommendations are provided in the following key areas:
1. **Total Bookings and Cancellations:**
2. **Booking Volume and Country:**
3. **Revenue and Average Daily Rate (ADR):**
4. **Guest Behavior and Stay Duration:**

The SQL queries (per category) used to explore the data for this analysis can be found [here](https://github.com/kevinfcanas/hotel-booking-analysis)

## Data Structure & Initial Checks
The database structure, as seen below, utilizes a star schema and consists of 5 dimensional tables and 1 core or fact table: hotels, stay_details, bookings, segments, guests, and countries, with a total row count of 119,390 records. A description of each table is as follows:

1. **hotels:** Categorizes the property into a city hotel or a resort hotel.
2. **stay_details:** Contains information about each stay: arrival year, month, week, and duration.
3. **bookings:** The fact table holding all the customer bookings and contains metrics on reservation status, financials, and customer behavior.
4. **segments:** Notes the type of booking that was made and the distribution channel for each.
5. **guests:** Tracks the composition of each guest (adults, children, babies) and if they are new or returning.
6. **countries**: A lookup table for each guest's country of origin.

![Entity Relationship Diagram (ERD)](https://github.com/user-attachments/assets/7d882f6b-4e33-4303-8be0-0cdd65239187)

The dataset contains 40,060 observations for Resort Hotels in the Algarve and 79,330 observations for City Hotels in Lisbon.

## Executive Summary

### Overview of Findings
Across 2015-2017, city hotels and transient hotel segments held the largest booking volumes, but also had significant volatility, with cancellation rates at 41.7%. Revenue remains seasonal, peaking in the summer months and among Online Travel Agency (TA) segments. Resort hotel revenue had a larger average booking cost despite having a lower booking volume. An opportunity lies in incentivizing short lead-time bookings and family stays, which show higher stability and longer durations compared to travelers with "one-off" stays with high cancellation rates. 

## Insights Deep Dive

### Category 1: Total Bookings and Cancellations
- City Hotels have a higher cancellation rate (41.7%) than Resort Hotels (27.8%).
- Family bookings have a slightly higher cancellation rate in comparison to solo bookings, though both remain relatively low and below 40%.
- Family bookings have a higher average stay duration.
- Those with a short lead time to booking have the lowest cancellation rate (18%), with long lead time bookings having a cancellation rate of 51%. Notably, the largest set of bookings has a long lead time, followed by short lead times.
- Transient customer types have not only the highest volume (89,613) of bookings but also the highest cancellation rate (41%), while contract customers have a lower cancellation rate (31%).

![Bookings by Lead Time](https://github.com/user-attachments/assets/63b721e6-4e70-4f37-abda-2ed9d0b78c38)
![Total Bookings by Market Segment](https://github.com/user-attachments/assets/83f22994-803e-4d9b-a4c8-735f905de288)

### Category 2: Booking Volume and Country
- Portugal, Great Britain, France, and Spain make up the highest volume of bookings.
- In 2017, May held the most bookings (3,551) alongside March (3,298) and July (3,329). Overall, summer months hold a higher booking volume than the winter months.

### Category 3: Revenue and Average Daily Rate (ADR)
- Resort Hotels have a higher average booking cost (400.92) in comparison to city hotels (311.98), but city hotels have a larger booking count.
- Online TA produces the highest volume of bookings and segment revenue (13,714,401.42). Aviation has the lowest number of bookings, but does not have the lowest segment revenue.
- Direct and group bookings sit in the middle of the pack for segment revenue and booking volume.
- Between 2015-2017, Avg. ADR is consistently higher between July and September, with a consistent dip in the winter months of November and January. Though this dip has increased in its ADR value over the past 3 years.

### Category 4: Guest Behavior and Stay Duration
- Stays with a duration of 3-5 days are the most numerous, with a 38.9% cancellation rate. Duration of 1-2 days follow with a 35.8% cancellation rate.
- Stays with longer durations (10+ nights) are less frequent but hold a lower cancellation rate.

## Recommendations

Based on the above insights and findings, 
