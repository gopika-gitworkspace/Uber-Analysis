# Uber-Analysis

BUSINESS REQUIREMENT

UBER TRIP ANALYSIS

DAHBOARD 1: OVERVIEW ANALYSIS

Analyse Uber trip data using Power BI to gain insights into booking trends, revenue, and trip efficiency, helping stakeholders make data-driven decisions.

KPI’s

Total Bookings – How many trips were booked over a given period?

Total Booking Value – What is the total revenue generated from all bookings?

Average Booking Value – What is the average revenue per booking?

Total Trip Distance – What is the total distance covered by all trips?

Average Trip Distance – How far are customers traveling on average per trip?

Average Trip Time – What is the average duration of trips?

Expected Outcomes:

✔ Identify trends in ride bookings and revenue generation.

✔ Analyse trip efficiency in terms of distance and duration.

✔ Compare booking values and trip patterns across different time periods.

✔ Provide insights to optimize pricing models and improve customer satisfaction.




CHART’s

Create a Measure Selector using a Disconnected Table with the following values:

Total Bookings

Total Booking Value

Total Trip Distance

Then, use a measure to dynamically update the visualizations based on user selection.

By Payment Type (Card, Cash, Wallet, etc.)

By Trip Type (Day/Night)


Additional Enhancements:

Dynamic Title – Update the chart title based on the selected measure.

Slicers – Add filters for Date, City, and other interactive filters for deeper analysis.

Tooltips – Show additional details like Average Booking Value or Trip Distance.

Vehicle Type Analysis - Grid View in Power BI

Create a grid table (matrix or table visual) to analyse key performance indicators like Total Bookings, Total Booking Value, Avg Booking Value, Total Trip Distance across different Vehicle Types in Uber trips.

Power BI Implementation:

Use a Table or Matrix Visual to display Vehicle Type with the KPIs.

Apply Conditional Formatting to highlight high and low values.

Enable Sorting & Filtering for user interaction.

Total Bookings by Day

Detecting trends and fluctuations in daily trip volumes.

Identifying peak and off-peak booking days.

Understanding the impact of external factors (holidays, events, weather) on ride demand.

Supporting strategic planning for resource allocation and pricing adjustments.


Location Analysis

Understanding trip locations is crucial for optimizing ride distribution, demand forecasting, and operational efficiency. This analysis focuses on:

Most Frequent Pickup Point

Identify the most common starting locations for trips.

Helps in optimizing driver availability and dynamic pricing strategies.

Most Frequent Drop-off Point

Find the most common drop-off locations.

Requires activating an inactive relationship in Power BI between Pickup Location and Drop-off Location in the data model.

Farthest Trip

Determine the longest trip based on distance travelled.

Useful for analysing outlier trips, long-distance demand, and fare optimization.

Total Bookings by Location (Top 5)

Identify the top 5 locations with the highest trip bookings.

Helps in demand forecasting and optimizing driver availability in high-traffic areas.

Most Preferred Vehicle for Location Pickup

Determine the most frequently booked vehicle type at each pickup location.

Supports strategic vehicle distribution based on customer preferences and location demand.





Other Implementation Enhancements for Uber Trip Analysis Dashboard

Bookmark for Data Details 

Add a "Data Details" bookmark to display a pop-up or side panel explaining:

Meaning of key metrics (Total Bookings, Total Trip Distance, etc.).

Description of tables used in the analysis.

Data source and refresh frequency.

Clear Slicer Button 

Add a "Clear Filters" button using a blank button with a Reset Slicers action to reset all selections in one click.

Improves user experience for quick dashboard resets.

Download Raw Data Button 

Add a button to export raw data in CSV or Excel format.

Use Power Automate or built-in Power BI Export functionality.

Enables users to analyse raw data outside Power BI if needed.





DAHBOARD 2: TIME ANALYSIS

To understand trip patterns based on time, Uber needs to analyse ride demand and trends across different time intervals. This dashboard will help in optimizing operations, pricing, and driver availability.

Global Dynamic Measure (Filters All Charts)

A measure selector will be created for:

✔ Total Bookings

✔ Total Booking Value

✔ Total Trip Distance

This dynamic measure will update all visuals based on user selection.

Visualizations:

By Pickup Time (10-Minute Intervals) - Area Chart

Groups trip bookings into 10-minute intervals throughout the day.

Helps in identifying peak and off-peak demand periods.

By Day Name - Line Chart

Shows booking trends across Monday to Sunday.

Useful for analysing weekday vs. weekend demand.

By Hour and Time - Heatmap (Matrix Grid)

Rows: Hours of the Day (0–23)

Columns: Days of the Week (Mon-Sun)

Values: Selected Dynamic Measure (e.g., Total Bookings)

Highlights peak booking hours across different days.




DAHBOARD 3: DETAILS TAB

To provide in-depth insights and allow users to explore granular data, a Grid Tab will be created. This tab will enable drill-through functionality, allowing users to access detailed records based on selections made in other dashboards.

Features of the Grid Tab:

Grid Table with Key Fields:

Displays essential trip details

Drill-Through Functionality:

Users can right-click on a data point from other visuals (e.g., charts, heatmaps) and drill through to this Grid Tab.

Displays detailed records related to the selected data point.




Table descriptions

Trip Details Table

The Trip Details Table captures individual Uber trip records and provides detailed information about each ride, including trip timing, distance, fare, pickup/drop-off data, and more. This table enables deep analysis of ride patterns, demand fluctuations, vehicle usage, and passenger behaviors.



Trip ID: Unique identifier for each trip, used for tracking and referencing individual rides.


Pickup Time / Drop Off Time: Timestamp values recording when a ride started and ended. These help compute total ride duration, support time-based analysis (e.g., peak hours), and distinguish between day and night trips.


Pickup Date: Extracted from the Pickup Time. Useful for daily trip trend analysis.


Trip type (Day/Night): Categorizes each trip based on pickup time into “Day Trip” or “Night Trip.” Useful for identifying temporal patterns in ride demand.


Pickup Hour (HH MM SS) & Pickup Hour (bins): Represent the exact and binned pickup time for hourly grouping. Useful in hourly trip demand visualization.


Passenger Count: Number of passengers in the vehicle for each trip. Supports studies on ride-sharing behavior and vehicle utilization.


Trip Distance: Distance traveled (in miles), used for fare estimation, operational efficiency analysis, and mapping ride lengths.


PULocationID / DOLocationID: Numerical IDs representing pickup and drop-off locations. These IDs link to the Location Table for mapping to actual geographic areas.


Dropoff Location: Derived from DOLocationID; provides the neighborhood name of the trip’s destination.


Fare Amount: The base fare charged, excluding surge and additional fees. Key metric for revenue analysis.


Surge Fee: Additional charge during high-demand periods. Helps in surge pricing and peak-demand pattern recognition.


Vehicle: Indicates the Uber service type (e.g., UberX). Useful in market segmentation and customer preference studies.


Payment Type: Method of payment (e.g., Cash), useful for financial reporting and user behavior analysis.


Location Table



The Location Table contains geographical information that links numerical location IDs to actual named areas or neighborhoods, specifically within the borough of Queens in this dataset. Each entry in the table includes a unique LocationID, the corresponding Location (neighborhood or area name), and the City (which is consistently "Queens" for all rows shown).



LocationID: A unique numeric identifier for each pickup or drop-off location. It is used as a key to link location data with trip records from the Trip Details table.


Location: The name of the neighborhood or area in Queens where pickups and drop-offs occur (e.g., Jamaica Bay, Astoria, Bayside).


City: The borough name—"Queens" for every entry shown—which supports further geographical analysis.

