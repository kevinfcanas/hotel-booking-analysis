# Hotel Booking Analysis

## Project Background
Direct from the property management system (PMS) of this hotel conglomerate, the project contains information for city hotels in Lisbon, Portugal, and resort hotels in the Algarve Region, Portugal. Due to the identifiable nature of hotel bookings, the data has been anonymized, and the names of the customers andthe hotel conglomerate are not included. These were collected between the period of July 1st, 2015, and August 31st, 2017.

This conglomerate provides a significant amount of data on its booking durations, cancellations, marketing efforts, guest behavior, and guest make-up that have been previously underutilized in conversations about tourism behavior and hospitality. This project comprehensively analyzes and combines this data to uncover key observations that will elevate the conglomerate's guest experience and retention.

Insights and recommendations are provided in the following key areas:
1. **Total Bookings and Cancellations**
2. **Booking Volume and Country**
3. **Revenue and Average Daily Rate (ADR)**
4. **Guest Behavior and Stay Duration**

The SQL queries (per category) used to explore the data for this analysis can be found [here](https://github.com/kevinfcanas/hotel-booking-analysis).

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
Between 2015 and 2017, booking behavior was a critical contributor to revenue and cancellation outcomes. City hotels and transient guests generated the highest booking volumes but also showed the greatest volatility, with cancellation rates reaching 41.7%. Revenue patterns were strongly seasonal, peaking in the summer months and driven largely by Online Travel Agency (TA) bookings. Although resort hotels attracted fewer guests, they produced higher average booking values. Opportunities for improvement lie in encouraging short lead‑time bookings and family stays, which demonstrate lower cancellation risk and longer stay durations compared to one‑off or long lead‑time travelers.

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
- Portugal, Great Britain, France, and Spain make up the highest volume of bookings. In general, the European countries dominate the bookings for either hotel type.
- Between the period of July 2015 and August 2017, 2016 held the most non-cancelled bookings (36,370), with October 2016 holding the most non-cancelled bookings (3,689).
- May held the most non-cancelled bookings (3,551) alongside March (3,298) and July (3,329), all in 2017.
- The July through October period shows an increased number of bookings, month-to-month, in both 2015 and 2016. Notably, the July-August period is showing a decrease in bookings in 2017.
  
![Non-canceled Bookings vs  Country Name](https://github.com/user-attachments/assets/9298648a-2c5f-48ae-a9eb-78d5b9d2922d)
![Total Bookings vs  Month (2015-2017)](https://github.com/user-attachments/assets/3b962556-eef8-4a62-9dbc-322114f44df8)

### Category 3: Revenue and Average Daily Rate (ADR)
- Resort Hotels have a higher average booking cost (400.92) in comparison to city hotels (311.98), but city hotels have a larger booking count.
- Between 2015-2017, Avg. ADR is consistently higher between July and September, with a consistent dip in the winter months of November and January. However, this dip has increased in its ADR value over the past 3 years.
- Online TA produces the highest volume of bookings and segment revenue (13,714,401.42). Aviation has the lowest number of bookings, but does not have the lowest segment revenue.
- Direct and group bookings sit in the middle of the pack for segment revenue and booking volume.

![Total Bookings and ADR](https://github.com/user-attachments/assets/c451dd8e-57fc-4647-849a-6dddc6198ace)
![Market Segment Revenue](https://github.com/user-attachments/assets/28d79c9a-15c3-41d6-8ac7-a54001776cd4)
![Total Bookings Per Market Segment](https://github.com/user-attachments/assets/647593f8-d4e8-4f6d-b614-b0289dad7c7b)

### Category 4: Guest Behavior and Stay Duration
- City hotels and Resort Hotels vary in average lead time, with group customer types having the lowest lead time (57.15 days and 52.90 days, respectively).
- Resort Hotels have a lower lead  time for non-cancelled bookings except for contract customer types. 
- Stays with a duration of 3-5 days are the most numerous, with a 38.9% cancellation rate. Duration of 1-2 days, followed by a 35.8% cancellation rate.
- Stays with longer durations (10+ nights) are less frequent but hold a lower cancellation rate.
  
![Lead Time by Customer Type](https://github.com/user-attachments/assets/c5f5de6e-e51e-471c-95fa-cfc4600078dd)
![Total Bookings vs  Stay Duration](https://github.com/user-attachments/assets/73eb80d8-ff9b-4f9d-a953-93e93aadf30d)


## Recommendations

Based on the above insights and findings, I recommend that the hotel conglomerate's marketing division consider the following:
1. Long lead‑time stays cancel at 51%, the highest of any group. To protect revenue, the hotel conglomerate should implement partial deposits for long lead‑time reservations or offer incentives tied to non‑cancellation windows. Lowering cancellations in this high‑volume group will meaningfully stabilize revenue.
2. ADR and booking volume both peak between July and October. The marketing division should expand seasonal travel packages, adjust pricing to reflect demand elasticity, and prioritize high‑value segments during this period. This ensures the company fully takes advantage of its strongest revenue window.
3. Transient guests generate 89,000+ bookings but cancel at 41%. Offering personalized incentives (such as breakfast packages, late checkouts, or meal vouchers) and providing stay credits instead of full cancellations can reduce melt and protect revenue from this high‑volume but volatile segment.
4. European countries consistently dominate booking volume year‑round. Adjusting pricing during peak European travel months and offering region‑specific packages aligned with European holidays can strengthen this reliable customer base. Optimizing for these travelers creates predictable demand and a more stable revenue stream.
5. Online TA (Travel Agencies) generate the highest booking volume but create dependency on outside booking sources. Encouraging direct bookings through exclusive in‑house benefits and implementing differentiated cancellation policies by channel can diversify revenue sources and improve margin stability.

## Assumptions and Caveats

Throughout the course of this analysis, multiple assumptions were made to manage the challenges in the data. These assumptions and caveats are noted below:
1. The dataset only includes 1 full year (2016) and two partial years (2015, 2017), so a full picture is not present for year-to-year comparison.
2. The above observations are descriptive and do not account for external factors like seasonality, weather, events, or existing promotions.
3. Lead time was interpreted to be the number of days between the booking date and the arrival date.

