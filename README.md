# Netflix-Dashboard-Power-BI-Project-
This project presents an interactive Netflix Data Analysis Dashboard built using Power BI. It focuses on analyzing content trends, distribution, and key insights across Movies and TV Shows.
The dashboard is designed with a Netflix-inspired dark theme and includes interactive filters for better user experience.

Objectives
Analyze Netflix content distribution
Compare Movies vs TV Shows
Identify top contributing directors
Understand content trends over time
Explore duration and genre patterns

Dataset
Source: Netflix Shows Dataset (Kaggle)
Dataset Link: https://www.kaggle.com/datasets/shivamb/netflix-shows
Dataset Features

The dataset includes the following columns:

Show ID
Title
Type (Movie / TV Show)
Director
Country
Date Added
Release Year
Rating
Duration
Genre (listed_in)
 Data Cleaning & Transformation (Power Query)

The following transformations were performed:

Data Type Fixes
Converted date_added column to Date format

Feature Engineering
Extracted Year from date_added
Created Country_Main by splitting the country column
Extracted Main_Genre from listed_in

Handling Missing Values
Replaced null values:
Director → "Unknown"
Country → "Unknown"

 Duration Cleaning
Extracted numeric values from the duration column
Created Duration_Value for analysis

 Data Modeling & DAX
 Calculated Columns
Month = FORMAT(netflix_titles[date_added], "MMMM")

Month_No = MONTH(netflix_titles[date_added])
 Measures (KPIs)
Total Titles = COUNT(netflix_titles[show_id])

Total Movies = 
CALCULATE(
    COUNT(netflix_titles[show_id]),
    netflix_titles[type] = "Movie"
)

Total TV Shows = 
CALCULATE(
    COUNT(netflix_titles[show_id]),
    netflix_titles[type] = "TV Show"
)

Average Duration = AVERAGE(netflix_titles[Duration_Value])

Dashboard Structure
Page 1: Overview Dashboard
 KPI Cards
Total Titles
Total Movies
Total TV Shows
Average Duration

 Visualizations
Donut Chart → Movies vs TV Shows
Bar Chart → Genre Distribution
Line Chart → Content Added Over Years

 Slicers (Interactive Filters)
Type
Country
Year
🔹 Page 2: Advanced Analysis

Visualizations
Top Directors (Top 10 using Top N filter)
Content Added Per Month (sorted using Month_No)
Average Duration Per Year
Duration Distribution (using binning technique)

 Dashboard Design
Theme: Netflix Style
Background: Black
Primary Color: Red
Text Color: White

Key Insights
Movies dominate the platform compared to TV Shows
Content addition increased significantly in recent years
A few directors contribute a large portion of content
Most content falls within common duration ranges
Genre distribution highlights audience preferences
 Skills Demonstrated
Data Cleaning using Power Query
Data Transformation & Feature Engineering
DAX Calculations & Measures
Data Visualization Best Practices
Interactive Dashboard Design
Business Insight Extraction


<img width="630" height="427" alt="image" src="https://github.com/user-attachments/assets/73289784-2eb5-4c7a-840b-c93dbfc5f5d6" />


 Tools & Technologies
Power BI
DAX (Data Analysis Expressions)
Power Query
CSV Dataset
 Future Enhancements
Add Drill-through functionality
Add custom tooltips
Implement dynamic titles
Integrate real-time data
Publish to Power BI Service
Author: Bhavitha Vari

Feel free to connect for feedback, suggestions, or collaboration!

 If you found this project useful, consider giving it a star!
