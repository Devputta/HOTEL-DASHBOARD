🏨 Hotel Performance Analytics Dashboard

This Power BI dashboard provides insights into hotel operations including booking behavior, revenue trends, cancellation patterns, room rate analysis, loyalty segmentation, and booking channel performance. It is designed to help management understand guest patterns and improve hotel operations.

https://github.com/user-attachments/assets/d4a6384a-03be-47f0-b0d5-716271f50988

📊 Key Metrics Tracked

Booking Count

Cancellation Percentage

Total Revenue

Total Room Nights

Average Room Rate

Loyalty Customer Distribution

Booking Lead Time

Room Occupancy Behavior

🧾 Dataset Fields (as used in the model)
Field Name	Description
Booking ID	Unique booking identifier
Booking Date	Date of reservation
Status	Booking status (Completed / Cancelled)
Day Name	Weekday of booking
Day of Week	Numeric weekday
Booking Channel	Channel through which booking was made
Loyalty Level	Guest loyalty tier
Loyal Customer?	Loyalty classification flag
Not Loyal Customer	Count of non-loyal guests
Multi-night booking	Nights > 1 flag
Single-night booking	Nights = 1 flag
Number of nights	Duration of booking
Revenue	Total value of booking
Room Rate	Rev per night
How far away?	Days between booking date and stay date
Cancellation Count	Cancelled bookings
Cancellation Pct	Cancellation percentage
Avg. Room Rate	Measure: average room rate
🧠 Core DAX Measures
Booking Count = COUNTROWS(bookings)

Total Revenue = SUM(bookings[Revenue])

Avg. Room Rate = AVERAGE(bookings[Room Rate])

Cancellation Count = CALCULATE([Booking Count], bookings[Status] = "Cancelled")

Cancellation Pct = DIVIDE([Cancellation Count], [Booking Count])

Number of nights = DATEDIFF(bookings[Booking Date], bookings[Stay Date], DAY)

How far away? = DATEDIFF(bookings[Booking Date], bookings[Stay Date], DAY)

Loyal Customer? = IF(bookings[Loyalty Level] <> "Non-member", 1, 0)

Not Loyal Customer = IF(bookings[Loyalty Level] = "Non-member", 1, 0)


✅ You can paste your full measure list if you'd like — I can format it too.

🎯 Key Insights Provided

Daily guest arrival patterns

Weekend vs weekday demand trends

Loyalty tier customer contribution

Booking lead-time behavior

Booking channel performance

Single-night vs multi-night stay behavior

Revenue and occupancy drivers

🛠️ Visualization Highlights

KPI Cards

Line Chart (Daily stays)

Bar Chart (Weekdays vs Weekends)

Bar Chart (Lead time buckets)

Heatmap (Loyalty × Booking channel)

Category bar chart (Guest type segmentation)

Date range slicer

Navigation buttons UI

🚀 How to Use

Open .pbix file in Power BI Desktop

Use date slicer to analyze trends

Explore navigation buttons to switch report views

Hover on visuals for tooltips

👤 Author

Mahadevu M P

⭐ Support

If you like this project, please ⭐ the repo and share!
