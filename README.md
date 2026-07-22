# 📱 Social Pulse: Social Media Performance Insights Dashboard

A professional end-to-end Power BI analytics project designed to analyze social media performance across multiple platforms, regions, content types, and publishing schedules. This dashboard transforms raw social media data into actionable business insights, enabling marketing teams to optimize content strategy, audience engagement, and campaign performance.

---

# Executive Summary

Social media teams generate thousands of posts across multiple platforms every month, making it difficult to identify which content performs best, where engagement is strongest, and when audiences are most active.

This project analyzes **5,600 social media posts** across **8 countries** and **5 major social media platforms** using Power BI, PostgreSQL, Power Query, SQL, and DAX.

The dashboard enables users to:

- Monitor overall social media performance
- Compare engagement across platforms and regions
- Discover high-performing content formats
- Identify optimal posting times
- Track Month-over-Month engagement growth
- Support data-driven marketing decisions

---

# Project Objectives

The primary objective of this project is to provide a centralized analytical solution for monitoring social media performance.

The dashboard helps answer business questions such as:

- Which platform generates the highest engagement?
- Which content type performs best?
- Which regions have the strongest audience engagement?
- What is the best time to publish content?
- Is engagement improving over time?
- How does Organic content compare with Sponsored content?
- Which months experienced significant growth or decline?

---

# Business Problem

Marketing teams often manage campaigns across multiple platforms, regions, and content formats.

Without a centralized reporting solution, it becomes difficult to:

- Compare platform performance
- Measure campaign effectiveness
- Identify audience behavior
- Optimize publishing schedules
- Monitor engagement trends
- Make strategic marketing decisions

This dashboard addresses these challenges by consolidating all performance metrics into a single interactive reporting solution.

---

# Dataset Overview

### Dataset Size

- Total Posts: **5,600**
- Countries: **8**
- Platforms: **5**
- Content Types: **Organic, Sponsored**
- Post Formats:
  - Video
  - Image
  - Text
  - Live Stream
  - Article

### Platforms

- Facebook
- Instagram
- YouTube
- LinkedIn
- X (Twitter)

### Regions

- USA
- Canada
- Brazil
- United Kingdom
- Germany
- India
- Japan
- Australia

### Dataset Granularity

Each row represents **one individual social media post**.

The dataset contains post-level engagement metrics including:

- Likes
- Comments
- Shares
- Views
- Impressions
- Engagement Rate
- Publish Date
- Publish Time
- Platform
- Country
- Content Type
- Engagement Level

---

# Tech Stack

## Visualization

- Power BI Desktop

## Data Preparation

- Power Query
- Microsoft Excel

## Database

- PostgreSQL

## Data Modeling

- Star Schema
- Fact & Dimension Tables

## Analytics

- DAX
- Time Intelligence
- KPI Measures
- Month-over-Month Analysis

## Version Control

- Git
- GitHub

---

# Data Cleaning & Transformation

The dataset was transformed using Power Query before loading into Power BI.

Cleaning activities included:

- Removed duplicate records
- Standardized column names
- Corrected data types
- Handled missing values
- Removed unnecessary columns
- Created Date Dimension
- Built lookup tables
- Validated relationships
- Optimized model structure

---

# Data Model

The dashboard follows a **Star Schema** design to improve performance and simplify reporting.

Tables include:

Fact Table

- fact_posts

Dimension Tables

- Dim_Date
- Dim_Location

Measure Table

- _Measures

The model enables efficient filtering, aggregation, and DAX calculations.

---

# DAX Measures

Custom DAX measures were created to support dynamic reporting and KPI calculations.

Examples include:

- Total Engagements
- Average Engagement Rate
- Total Views
- Total Likes
- Total Shares
- Total Comments
- Previous Month Engagement
- Month-over-Month Growth %
- Dynamic KPI Cards

---

# Dashboard Features

The dashboard includes:

- Interactive Slicers
- Cross-filtering
- Dynamic KPI Cards
- Drill-down Analysis
- Time Intelligence
- Regional Analysis
- Platform Comparison
- Responsive Visual Layout

---

# Dashboard Walkthrough

## Executive Summary

Provides a high-level overview of overall social media performance using KPI cards.

Key Metrics include:

- Total Posts
- Total Engagements
- Engagement Rate
- Views
- Likes
- Shares
- Comments

Visuals:

- KPI Cards
- Shares by Post Type
- Engagement by Region
- Monthly Engagement Trend
- Content Type Filter
- Engagement Level Filter

Business Value:

Allows decision-makers to quickly evaluate overall campaign performance.

---

## Temporal & Geo Performance

Analyzes engagement patterns across time and geography.

Visuals include:

- World Map
- Monthly Post Trend
- Day & Hour Engagement Heatmap

Business Value:

Helps identify:

- Best posting hours
- High-performing countries
- Seasonal engagement patterns
- Publishing trends

---

# Key Business Insights

### Video Dominates Engagement

Video posts generate significantly more shares than all other content formats combined, making video the strongest driver of audience interaction.

---

### Optimal Posting Time

Engagement is highest between **10:00 AM–12:00 PM** and **4:00 PM–6:00 PM**, suggesting these windows are ideal for publishing new content.

---

### Global Audience Distribution

Engagement is relatively balanced across multiple countries, indicating strong international audience reach rather than dependence on a single market.

---

### Publishing Trend

Posting activity declines noticeably after April, highlighting a potential change in campaign strategy, budget allocation, or content planning.

---

### Performance Monitoring

Month-over-Month analysis enables teams to quickly identify growth periods and investigate declines in campaign performance.

---

# Business Recommendations

Based on dashboard insights:

- Increase investment in video content.
- Publish during peak engagement hours.
- Prioritize high-performing regions.
- Monitor declining posting frequency.
- Compare Organic and Sponsored campaigns regularly.
- Track Month-over-Month KPIs for continuous optimization.

---

# Skills Demonstrated

This project demonstrates practical experience in:

- Data Cleaning
- ETL
- Power Query
- SQL
- PostgreSQL
- Power BI
- Data Modeling
- Star Schema
- DAX
- Time Intelligence
- Dashboard Design
- KPI Development
- Data Visualization
- Business Analysis
- Storytelling with Data

---

# Project Workflow

```
Raw Dataset
      │
      ▼
Microsoft Excel
      │
      ▼
PostgreSQL
      │
      ▼
Power Query
      │
      ▼
Data Cleaning
      │
      ▼
Star Schema Modeling
      │
      ▼
DAX Measures
      │
      ▼
Interactive Dashboard
      │
      ▼
Business Insights
```

---

# Repository Structure

```
Social-Media-Performance-Dashboard/
│
├── data/
│   ├── sample_data.csv
│   └── data_dictionary.xlsx
│
├── sql/
│   ├── database_schema.sql
│   └── analysis_queries.sql
│
├── power_query/
│   └── transformation_steps.md
│
├── screenshots/
│   ├── executive_summary.png
│   └── temporal_geo_performance.png
│
├── docs/
│   └── data_model.png
│
├── dax_measures.md
├── Social_Media_Performance.pbix
├── README.md
├── LICENSE
└── .gitignore
```

---

# Dashboard Preview

## Executive Summary

![Executive Summary](https://github.com/DilawarShafiq44/Social_media_performance_dashboard/blob/main/Social_media_dashboard_1.png)

---

## Temporal & Geo Performance

![Temporal & Geo Performance](https://github.com/DilawarShafiq44/Social_media_performance_dashboard/blob/main/Social_media_dashboard_2.png)

---

# Future Enhancements

Potential improvements include:

- Row-Level Security (RLS)
- Mobile Layout Optimization
- AI-powered Key Influencers Visual
- Forecasting with Time Series Analysis
- Automated Data Refresh
- Incremental Refresh
- Real-time Dashboard Integration

---

# Author

**Dilawar Shafiq**

**Data Analyst | Power BI | SQL | Excel | PostgreSQL**

📧 Email: mughal.dlawer@gmail.com

🔗 LinkedIn: https://www.linkedin.com/in/dilawarshafiq44/

💼 Portfolio: *Coming Soon*

---

⭐ If you found this project useful, consider giving the repository a star.
