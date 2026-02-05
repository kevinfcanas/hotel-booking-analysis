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

## Executive Summary
### Overview of Findings

Portugal; Resort Hotels in Algarve (40,060 observations) and City Hotels (79,330 observations) in Lisbon
