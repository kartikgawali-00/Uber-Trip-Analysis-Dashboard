# 🚖 Uber Trip Analysis Dashboard

<p align="center">
  <img src="https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?logo=powerbi&logoColor=black">
  <img src="https://img.shields.io/badge/SQL-Data%20Analysis-blue">
  <img src="https://img.shields.io/badge/Excel-Data%20Preparation-green">
  <img src="https://img.shields.io/badge/Project-Interactive%20Dashboard-orange">
</p>

---

# 📌 Project Overview

The **Uber Trip Analysis Dashboard** is an end-to-end Business Intelligence project developed using **Power BI, SQL, and Excel** to analyze ride booking patterns, trip performance, revenue generation, vehicle utilization, and location-based demand.

The dashboard transforms raw trip data into meaningful business insights, helping stakeholders understand customer behavior, optimize fleet allocation, and improve operational efficiency.

---

# 📂 Dataset Used

📊 **Dataset Link**

<a href="https://github.com/kartikgawali-00/Uber-Trip-Analysis-Dashboard/tree/main/Dataset">View Dataset</a>

---

# 🎯 Project Objective

The objective of this project is to analyze Uber trip data and provide actionable insights into:

✅ Booking Trends

✅ Revenue Performance

✅ Vehicle Utilization

✅ Trip Distance & Duration

✅ Pickup & Drop-off Patterns

✅ Customer Travel Behavior

✅ Peak Booking Hours

✅ Location Demand Analysis

The dashboard enables data-driven decision-making and supports business growth through operational optimization.

---

# 🛠️ Tools & Technologies Used

| Technology     | Purpose                     |
| -------------- | --------------------------- |
| 📊 Power BI    | Dashboard Development       |
| 🗄️ SQL        | Data Analysis               |
| 📑 Excel       | Data Cleaning & Preparation |
| ⚡ DAX          | KPI & Measure Creation      |
| 🔄 Power Query | Data Transformation         |

---

# 📂 Dataset Information

The dataset contains Uber trip booking information including:

* Trip ID
* Booking Date
* Pickup Time
* Drop-off Time
* Pickup Location
* Drop-off Location
* City
* Vehicle Type
* Payment Type
* Booking Value
* Trip Distance
* Trip Duration

---

# 📊 Dashboard Pages

## 1️⃣ Overview Analysis

### 📈 Key KPIs

| KPI                    | Value      |
| ---------------------- | ---------- |
| 🚕 Total Bookings      | 103.7K     |
| 💰 Total Booking Value | $1.6M      |
| 📊 Avg Booking Value   | $15        |
| 📍 Total Trip Distance | 349K Miles |
| 🛣️ Avg Trip Distance  | 3 Miles    |
| ⏱️ Avg Trip Time       | 16 Minutes |

### ❓ Business Questions

* Which payment method is preferred by customers?
* What is the total booking value generated?
* What is the day vs night trip distribution?
* Which locations generate maximum bookings?
* Which vehicle type receives the most bookings?

### 💡 Key Insights

✅ Uber Pay contributes the highest number of bookings.

✅ Day Trips account for approximately 65% of total rides.

✅ UberX is the most preferred vehicle category.

✅ Penn Station/Madison Square West is the most frequent pickup location.

✅ Upper East Side North is the most frequent drop-off location.

### 📷 Dashboard Preview

<img src="https://github.com/kartikgawali-00/Uber-Trip-Analysis-Dashboard/blob/main/Dashboard%20Images/Screenshot%202026-06-01%20181850.png?raw=true">

---

## 2️⃣ Time Analysis

### ❓ Business Questions

* What are the peak booking hours?
* Which days generate the highest demand?
* How are bookings distributed throughout the day?
* What is the relationship between booking volume and time?

### 💡 Key Insights

✅ Ride demand starts increasing after 6 AM.

✅ Peak bookings occur between 12 PM and 6 PM.

✅ Weekend bookings are significantly higher.

✅ Saturday and Sunday generate maximum trip demand.

✅ Afternoon hours contribute the largest share of bookings.

### 📊 Visualizations Used

* Booking Trend by Pickup Time
* Booking Trend by Day Name
* Hour-Day Heatmap Analysis
* Peak Hour Identification

### 📷 Dashboard Preview

<img src="https://github.com/kartikgawali-00/Uber-Trip-Analysis-Dashboard/blob/main/Dashboard%20Images/Screenshot%202026-06-01%20181910.png?raw=true">

---

## 3️⃣ Details Analysis

### ❓ Business Questions

* Which vehicle type generates maximum bookings?
* Which vehicle category contributes the highest revenue?
* Which pickup locations drive the most demand?
* What are the top-performing drop-off zones?
* How does trip performance vary across vehicle categories?

### 📊 Analysis Included

✅ Vehicle-wise Bookings

✅ Vehicle-wise Revenue

✅ Trip Distance Analysis

✅ Pickup Location Analysis

✅ Drop-off Location Analysis

✅ Vehicle Performance Comparison

### 💡 Expected Insights

✅ UberX contributes the highest booking volume.

✅ Premium vehicles generate higher average booking values.

✅ Major city hotspots contribute most ride demand.

✅ Vehicle preferences vary by pickup location.

### 📷 Dashboard Preview

<img src="[YOUR_THIRD_IMAGE_LINK](https://github.com/kartikgawali-00/Uber-Trip-Analysis-Dashboard/blob/main/Dashboard%20Images/Screenshot%202026-06-01%20181930.png)?raw=true">

---

# 🔍 SQL Analysis

### Total Bookings

```sql
SELECT COUNT(*) AS Total_Bookings
FROM Uber_Trips;
```

### Total Revenue

```sql
SELECT SUM(Booking_Value) AS Total_Revenue
FROM Uber_Trips;
```

### Revenue by Vehicle Type

```sql
SELECT Vehicle_Type,
       SUM(Booking_Value) Revenue
FROM Uber_Trips
GROUP BY Vehicle_Type;
```

### Pickup Location Analysis

```sql
SELECT Pickup_Location,
       COUNT(*) Total_Trips
FROM Uber_Trips
GROUP BY Pickup_Location
ORDER BY Total_Trips DESC;
```

### Peak Hour Analysis

```sql
SELECT DATEPART(HOUR, Pickup_Time) AS Hour,
       COUNT(*) AS Total_Bookings
FROM Uber_Trips
GROUP BY DATEPART(HOUR, Pickup_Time)
ORDER BY Hour;
```

---

# 📈 DAX Measures

### Total Bookings

```DAX
Total Bookings =
COUNT(Uber[Trip_ID])
```

### Total Revenue

```DAX
Total Revenue =
SUM(Uber[Booking_Value])
```

### Average Booking Value

```DAX
Avg Booking Value =
DIVIDE(
    [Total Revenue],
    [Total Bookings]
)
```

### Average Trip Distance

```DAX
Avg Distance =
AVERAGE(Uber[Trip_Distance])
```

### Average Trip Duration

```DAX
Avg Duration =
AVERAGE(Uber[Trip_Duration])
```

---

# 💡 Project Insights

## 🚕 Customer Behavior

* UberX is the most preferred ride category.
* Customers primarily travel during daytime hours.
* Weekend demand is considerably higher than weekdays.

## 💰 Revenue Insights

* Total booking value exceeded **$1.6 Million**.
* Average booking value remains stable around **$15**.
* High-demand locations contribute significantly to revenue.

## 📍 Location Insights

* Penn Station/Madison Square West records the highest pickups.
* Upper East Side North receives the highest drop-offs.
* Urban hotspots drive the majority of bookings.

## ⏰ Time-Based Insights

* Booking demand peaks during afternoon and evening hours.
* Morning demand begins increasing after 6 AM.
* Saturday and Sunday show maximum ride activity.

---

# 🚀 Business Recommendations

### 🚗 Optimize Fleet Allocation

Deploy more drivers in high-demand zones during peak hours.

### 📈 Dynamic Pricing

Leverage demand patterns for surge pricing opportunities.

### 📍 Location-Based Expansion

Increase driver availability around major transportation hubs.

### ⭐ Promote Premium Services

Target Uber Comfort and Uber Black in high-value locations.

### 🎯 Improve Customer Experience

Reduce wait times in peak-demand areas to increase customer satisfaction.

---

# 🏆 Skills Demonstrated

### 📊 Power BI

* Interactive Dashboard Development
* Data Modeling
* DAX Measures
* Power Query
* Drill-Down Analysis
* Heatmap Visualization
* KPI Design

### 🗄️ SQL

* Aggregations
* Group By
* Date Functions
* Revenue Analysis
* Location Analysis

### 📑 Excel

* Data Cleaning
* Data Validation
* Data Preparation

---

# 📌 Final Conclusion

The Uber Trip Analysis Dashboard provides a comprehensive view of trip demand, booking trends, revenue generation, location performance, and customer travel behavior.

The analysis highlights strong demand concentration around key urban locations, significant ride activity during daytime hours, and opportunities for improving fleet utilization. These insights can help Uber optimize operations, improve customer satisfaction, and maximize revenue growth.

---

# 👨‍💻 Author

## Kartik Gawali

📊 Data Analyst | Power BI | SQL | Excel

⭐ If you found this project useful, don't forget to star the repository.
