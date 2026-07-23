# 📱 Social Pulse: Social Media Performance Insights Dashboard

An end-to-end, AI-augmented Power BI analytics project analyzing **5,600+ social media posts** across **8 countries** and **5 platforms** — combining traditional BI tooling with Claude AI automation (via MCP server integration) to accelerate data modeling, DAX development, and dashboard delivery.

🔗 **[Interactive Dashboard](#)** &nbsp;|&nbsp; 📁 **[Download .pbix](Social_Media_Performance.pbix)**

---

## 🎯 Purpose

The **Social Media Performance Dashboard** helps social media managers, digital marketing analysts, and brand strategists track and compare engagement performance across platforms, regions, and content types. It answers critical business questions — *what content works, where, and when* — through an interactive, KPI-driven Power BI report, while showcasing a modern, AI-assisted analytics workflow.

---

## 🛠️ Tech Stack

- 📊 **Power BI Desktop** – Core visualization and report-building platform
- 📂 **Power Query Editor** – Data transformation, cleaning, and shaping (ETL layer)
- 📈 **Microsoft Excel** – Initial data collection and exploratory cleaning
- 🧠 **DAX (Data Analysis Expressions)** – Calculated measures and KPI logic ([see all measures →](dax_measures.md))
- 🤖 **Claude AI (via MCP Server Integration)** – Automated the data modeling and DAX development workflow

---

## 🤖 AI-Augmented Workflow (Claude + Power BI via MCP)

A key differentiator of this project is the use of **Claude AI, connected directly to Power BI Desktop through an MCP (Model Context Protocol) server**, to automate and accelerate parts of the data modeling process that are traditionally manual and repetitive.

**What Claude was used for:**
- **Live Model Connection:** Established a direct, real-time connection between Claude and the live Power BI semantic model — enabling programmatic inspection and modification of tables, columns, and measures.
- **Automated DAX Measure Creation:** All core DAX measures (Total Engagements, Total Likes, Total Comments, Total Shares, Total Views, Total Impressions, Avg Engagement, Engagement Previous Month, Engagement MoM % Change) were generated and deployed directly into the model via Claude — with formulas reviewed and refined (e.g., choosing `DATEADD` over `PREVIOUSMONTH` for more flexible period-over-period comparisons).
- **Calendar (Date) Table Governance:** Used Claude to audit the model and discover **9 redundant, hidden auto-generated date tables** created by Power BI's default Auto Date/Time setting. Claude removed all duplicates and helped standardize the model around a single, clean `Dim_Date` calendar table — improving model performance and consistency.
- **Model Auditing:** Used Claude to inspect table/column metadata directly (including hidden objects not visible in the standard Power BI UI) to validate data structure before building visuals.

**Why this matters:** This reflects a forward-looking, efficient analytics workflow — using AI tooling to reduce manual, repetitive modeling work while maintaining full control and review over every change, rather than relying on AI as a black box.

---

## 📂 Data Source

Post-level performance data covering **5,600 posts** across **8 regions** (USA, Japan, Brazil, UK, Canada, Australia, India, Germany) and **5 platforms** (Facebook, Instagram, YouTube, LinkedIn, X/Twitter). Fields include post type (Video, Image, Live Stream, Text, Article), content type (Organic/Sponsored), engagement level (High/Medium/Low), publish date/time, and core engagement metrics (Likes, Comments, Shares, Views, Impressions).

---

## 🧩 Business Problem & Solutions

| Business Problem | Solution Implemented | Estimated Impact |
|---|---|---|
| Marketing teams couldn't quickly identify which content format drives the most engagement | Built a **Total Shares by Post Type** visual, revealing Video content as the dominant driver (202M shares) | Reallocating budget toward video could meaningfully lift overall share volume |
| No visibility into optimal posting times, leading to inconsistent reach | Built a **Time of Day vs. Engagement heatmap** to pinpoint exact peak engagement windows (10AM–12PM, 4PM–6PM) | Aligning publish schedules to peak windows can improve reach without increasing post volume |
| No way to track whether engagement was growing or declining over time | Built **Engagement Previous Month** and **Engagement MoM % Change** DAX measures | Gives stakeholders real-time visibility into growth/decline trends instead of month-end manual reporting |
| Stakeholders needed both a high-level executive view and a detailed operational view | Designed a **two-page report structure**: Executive Summary + Temporal & Geo Performance | Serves both leadership (quick KPIs) and analysts (deep-dive) without building separate reports |

📸 *See full Business Problem & Solutions dashboard page in Screenshots section below.*

---

## 🔍 Key Visuals

**Executive Summary Page**
- KPI Cards: Total Posts (5,600), Total Engagements (646.5M), Avg Engagement Rate (15.28%), Total Views (4,806.28M), Total Likes (844M), Total Shares (267M), Total Comments (193M)
- Total Shares by Post Type (Donut Chart)
- Total Engagements by Region (Bar Chart)
- Engagement Level & Content Type Filters (High/Medium/Low, Organic/Sponsored)
- Total Engagements & MoM % Change Trend Chart

**Temporal & Geo Performance Page**
- Global Engagement Map (regional pie-chart bubbles by continent)
- Total Posts by Month and Region (Area Chart)
- Time of Day vs. Engagement Heatmap Table (by day and hour)

**Business Problem & Solutions Page**
- Dedicated report page mapping each business problem to its solution and estimated business impact — built directly as an in-dashboard page for stakeholder presentation

---

## 💡 Data Insights (Elaborated)

- **Video Content Dominance:** Video posts generated **202M shares** — more than 10x the next-highest format (Image, 20M). This strongly suggests video is the single most effective format for driving reach and should be prioritized in future content planning and budget allocation.

- **Time-of-Day Engagement Patterns:** Engagement is not evenly distributed throughout the day — clear peaks occur between **10 AM–12 PM** and again **4 PM–6 PM**, while early morning (8–9 AM) and early afternoon (1–2 PM) show significantly lower activity. Posting schedules should be aligned to these peak windows.

- **Balanced Global Reach:** Engagement across regions is relatively even — USA leads at 91M, followed closely by Japan and Brazil (83M each), the UK (82M), Canada (80M), Australia (79M), India (77M), and Germany (71M). No single region dominates, indicating genuinely international appeal.

- **Post-April Volume Decline:** Monthly post volume dropped sharply after April — from a range of ~600–700 posts/month (Jan–Apr) down to a stable ~200–300 posts/month for the remainder of the year, flagging a strategic shift worth investigating.

- **Engagement Volatility Over Growth Stability:** The MoM % Change trend shows frequent spikes and dips rather than smooth, compounding growth — suggesting engagement is largely event/campaign-driven.

- **Underutilized Formats:** Article (11M) and Text (12M) posts contribute the least to overall shares, indicating these formats may be better suited for niche, informational, or SEO-driven purposes rather than reach-focused campaigns.

---

## 🗂️ Data Modeling

The semantic model follows a clean **star schema** design with four core tables:

- **`fact_posts`** — central fact table holding all transactional post-level metrics (Clicks, Comments, Engagement, Engagement_Rate, Impressions, Likes, Live_Stream_Views, Content_Category, Content_Type, Engagement_Level, Main_Hashtag, Latitude, Longitude)
- **`Dim_Date`** — governed calendar table (audited and consolidated via Claude AI) with Date, DateKey, Day, Day Name, Day of Week Number
- **`dim_location`** — region dimension (Latitude, Longitude, Region), related to `fact_posts` via a 1-to-many relationship
- **`dim_platform`** — platform dimension (Platform, Image URL), related to `fact_posts` via a 1-to-many relationship

**Model Efficiency:** Removed 9 redundant, hidden auto-generated date tables during model audit, reducing unnecessary complexity while preserving full time-intelligence functionality through a single governed `Dim_Date` table.

![Data Model](https://github.com/DilawarShafiq44/Social_media_performance_dashboard/blob/main/Data_modling.PNG)

---

## 📂 Repository Structure

```
Social_media_performance_dashboard/
│
├── Social_media_dashboard_1.png     # Executive Summary page
├── Social_media_dashboard_2.png     # Temporal & Geo Performance page
├── Social_media_dashboard_3.png     # Business Problem & Solutions page
├── Data_modling.PNG                 # Data model / relationships view
├── dax_measures.md                  # All DAX measures with descriptions
├── Social_Media_Performance.pbix    # Power BI project file
└── README.md
```

---

## 📸 Dashboard Preview

![Executive Summary](https://github.com/DilawarShafiq44/Social_media_performance_dashboard/blob/main/Social_media_dashboard_1.png)
![Temporal & Geo Performance](https://github.com/DilawarShafiq44/Social_media_performance_dashboard/blob/main/Social_media_dashboard_2.png)
![Business Problem & Solutions](https://github.com/DilawarShafiq44/Social_media_performance_dashboard/blob/main/Social_media_dashboard_3.png)

---

## 👤 Author

**Dilawer Shafiq**
Data Analyst | Power BI • Excel • AI-Augmented Analytics
📧 [mughal.dlawer@gmail.com](mailto:mughal.dlawer@gmail.com) | 🔗 [LinkedIn](https://www.linkedin.com/in/dilawarshafiq44/)

---
⭐ *If you found this project helpful, consider giving the repository a star!*






































