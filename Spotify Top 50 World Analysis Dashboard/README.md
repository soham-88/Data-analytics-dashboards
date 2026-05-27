# 🎵 Spotify Top 50 World Dashboard | Power BI Project

![Power BI](https://img.shields.io/badge/Tool-Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/Language-DAX-blue?style=for-the-badge)
![Power Query](https://img.shields.io/badge/ETL-Power%20Query-0078D4?style=for-the-badge)
![Spotify](https://img.shields.io/badge/Dataset-Spotify%20Top%2050%20World-1DB954?style=for-the-badge&logo=spotify&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

An **interactive Power BI music analytics dashboard** built using the Spotify Top 50 World dataset to explore song popularity, artist performance, album trends, and content patterns — designed to support playlist managers, music analysts, and marketing teams with data-driven insights.

---

## 📋 Table of Contents

- [About the Project](#about-the-project)
- [Dashboard Overview](#dashboard-overview)
- [Key Metrics](#key-metrics)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [DAX Measures Used](#dax-measures-used)
- [Data Cleaning & Transformation](#data-cleaning--transformation)
- [Business Insights](#business-insights)
- [Setup & Usage](#setup--usage)
- [Developer](#developer)

---

## 📌 About the Project

The **Spotify Top 50 World Dashboard** is a music intelligence project built in Power BI to analyse chart performance data from Spotify's global Top 50 playlist.

The dashboard was designed for music analysts, playlist managers, and marketing teams to understand what makes a song chart-worthy — exploring popularity scores, artist dominance, album type distribution, content ratings, and duration trends across the dataset.

This project was built as part of my **Data Analytics Internship at Oasis Infobyte** and my academic work at **Bhavan's College, Mumbai**.

---

## 🖥️ Dashboard Overview

The dashboard is structured into the following visual sections:

- **Top KPI Cards** — Total Songs, Distinct Songs, Distinct Artists, Avg Popularity, Avg Duration
- **Popularity Trend** — Monthly and yearly popularity tracking across charting songs
- **Explicit vs Non-Explicit** — Content type comparison by count and popularity
- **Album Type Breakdown** — Single vs Album vs Compilation analysis
- **Top Songs Ranking** — Ranked table of highest popularity songs
- **Top Artists Ranking** — Artist-level performance analysis
- **Song-Level Detail Table** — Full drill-down table with all metrics
- **Advanced DAX Measures** — Custom calculations for rankings, averages, and trend analysis

---

## 📊 Key Metrics

| Metric | Description |
|--------|-------------|
| Total Songs | Total number of song entries in the dataset |
| Distinct Songs | Unique songs across all chart appearances |
| Distinct Artists | Number of unique artists in the Top 50 |
| Avg Popularity | Average Spotify popularity score (0–100) |
| Avg Duration | Average track duration across charting songs |
| Explicit Content % | Share of explicit vs clean songs in the chart |

---

## ✅ Features

### 1. 🎯 KPI Summary Cards
- Total Songs, Distinct Songs, Distinct Artists, Average Popularity Score, Average Duration
- Instant summary of the chart's overall composition and performance

---

### 2. 📈 Popularity Trend (Monthly & Yearly)
- Line/area chart tracking average popularity score over time
- Identifies rising trends, seasonal peaks, and performance drops
- Filter by year to compare chart dynamics across periods

---

### 3. 🔞 Explicit vs Non-Explicit Content Analysis
- Bar/pie chart comparing explicit and non-explicit song counts
- Shows whether explicit content correlates with higher popularity scores
- Useful for playlist curation and content policy decisions

---

### 4. 💿 Album Type Distribution
- Breakdown of charting songs by album type: Single, Album, Compilation
- Reveals whether standalone singles dominate the chart vs album tracks
- Supports A&R and release strategy decisions

---

### 5. 🏆 Top Songs Ranking
- Ranked visual of highest-popularity songs in the dataset
- Shows song name, artist, popularity score, and duration
- Filters dynamically with other slicers

---

### 6. 🎤 Top Artists Ranking
- Artist-level performance table showing total chart appearances and average popularity
- Identifies which artists dominate the Spotify Top 50 most consistently
- Supports artist performance tracking and sponsorship targeting

---

### 7. 🗂️ Song-Level Detail Table
- Full drill-down table with all attributes: Song Name, Artist, Album, Type, Popularity, Duration, Explicit flag
- Allows granular analysis of any specific song or artist
- Sortable by any column

---

### 8. 🔽 Dynamic Slicers
- Filter the entire dashboard by:
  - Artist Name
  - Album Type (Single / Album / Compilation)
  - Explicit Content (Yes / No)
  - Year / Month
- All visuals update simultaneously when a filter is applied

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| BI Tool | Microsoft Power BI Desktop |
| Data Transformation | Power Query (M Language) |
| Calculations | DAX (Data Analysis Expressions) |
| Visualisations | Bar, Line, Pie, Donut, Table, Card, Slicer |
| Data Source | CSV (Spotify Top 50 World dataset) |

---

## 📐 DAX Measures Used

```dax
-- Total Songs
Total Songs = COUNTROWS(Spotify)

-- Distinct Songs
Distinct Songs = DISTINCTCOUNT(Spotify[track_name])

-- Distinct Artists
Distinct Artists = DISTINCTCOUNT(Spotify[artists])

-- Average Popularity
Avg Popularity = AVERAGE(Spotify[popularity])

-- Average Duration (in minutes)
Avg Duration (min) = AVERAGE(Spotify[duration_ms]) / 60000

-- Explicit Song Count
Explicit Count = CALCULATE(COUNTROWS(Spotify), Spotify[explicit] = TRUE())

-- Non-Explicit Song Count
Non-Explicit Count = CALCULATE(COUNTROWS(Spotify), Spotify[explicit] = FALSE())

-- Top Artist by Appearances
Top Artist =
TOPN(1, VALUES(Spotify[artists]),
     CALCULATE(COUNTROWS(Spotify)), DESC)

-- Popularity Rank
Popularity Rank =
RANKX(ALL(Spotify[track_name]),
      CALCULATE(AVERAGE(Spotify[popularity])),, DESC, DENSE)
```

---

## 🔧 Data Cleaning & Transformation

All data cleaning was performed in **Power Query** before loading into the data model:

- Removed duplicate track entries
- Standardised column data types (text, decimal, boolean, date)
- Converted `duration_ms` from milliseconds to minutes using a calculated column
- Cleaned artist name formatting (trimmed whitespace, fixed encoding issues)
- Created a `Date` table for time intelligence and trend analysis
- Extracted Year and Month from release date fields
- Replaced null values in optional fields with appropriate defaults
- Created a categorical column for Popularity Tier (Low / Medium / High / Viral)

---

## 💡 Business Insights

Key findings from the dashboard analysis:

- **Singles Dominate** — The majority of Top 50 charting songs are released as standalone singles rather than album tracks
- **Explicit Content Trends** — Explicit songs appear frequently in the Top 50 and tend to have comparable or higher popularity scores than clean tracks
- **Artist Concentration** — A small group of artists account for a large share of chart appearances (high repeat dominance)
- **Popularity Distribution** — Most charting songs cluster in the 70–90 popularity range; sub-60 entries are rare
- **Duration Patterns** — Chart-topping songs typically fall in the 2.5–3.5 minute range, consistent with streaming listener behaviour
- **Seasonal Trends** — Certain months show higher average popularity, suggesting seasonal listening spikes

---

## ⚙️ Setup & Usage

### Prerequisites
- Microsoft Power BI Desktop installed ([Download here](https://powerbi.microsoft.com/desktop/))

### Steps

**1. Clone the repository**
```bash
git clone https://github.com/soham-88/Data-analytics-dashboards.git
```

**2. Navigate to the project folder**
```
cd "Data-analytics-dashboards/Spotify Top 50 World Analysis Dashboard"
```

**3. Open the dashboard**
- Open Power BI Desktop
- Click **File → Open**
- Select the `.pbix` file from the folder

**4. Explore the dashboard**
- Use the slicers to filter by Artist, Album Type, Explicit Content, or Year
- Hover over any visual for detailed tooltips
- Click any bar or segment to cross-filter all visuals on the page
- Use the song detail table for granular track-level analysis

---

## 👨‍💻 Developer

**Soham Gopal Pawar**  
B.Sc. Computer Science (SYCS) — Bhavan's College, Mumbai  
Data Analytics Intern — Oasis Infobyte

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/soham-pawar-984b32319/)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-black?style=for-the-badge&logo=github)](https://github.com/soham-88)

---

> ⭐ If you found this project useful, consider giving the repository a star!
