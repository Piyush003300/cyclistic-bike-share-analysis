# Cyclistic Bike-Share Analysis

## Overview

Cyclistic is a fictional bike-share company operating in Chicago (based on the real-world Divvy bike-share system). This project analyzes 12 months of historical trip data to understand how annual members and casual riders use Cyclistic bikes differently — insight the marketing team can use to design a campaign converting casual riders into annual members.

**Screenshort** [screenshot.jpg]

## Business Task

Cyclistic's marketing director, Lily Moreno, believes the company's future growth depends on maximizing annual memberships, since members are more profitable than casual riders. This project answers the first of three guiding questions for the upcoming marketing campaign:

> **How do annual members and casual riders use Cyclistic bikes differently?**

## Data Source

12 months of trip data (July 2025 – June 2026) from Divvy's public trip data, made available by Motivate International Inc. Data is anonymized — no personally identifiable rider information is included.

## Tools Used

- **Python (pandas)** — data cleaning, combining 12 monthly CSVs (~5.9M rows), calculated fields
- **Power BI** — data visualization and interactive dashboard

## Process

### 1. Prepare
Downloaded 12 months of trip data as separate CSV files, one per month. Verified column structure was consistent across all files before combining.

### 2. Process (Cleaning)
- Combined 12 monthly files into a single dataset (~5.93M rows)
- Converted `started_at`/`ended_at` to proper datetime format
- Calculated `ride_length` (in minutes) for every trip
- Removed rides with negative duration (data errors, 29 rows)
- Removed rides longer than 24 hours (5,539 rows), consistent with Divvy's own policy that bikes not returned within 24 hours are considered lost or stolen
- Added derived fields: day of week, month, season, hour of day
- Final cleaned dataset: **5,926,781 rides**

### 3. Analyze
Compared member vs. casual riders across five dimensions: ride volume, ride length, day of week, seasonality, and bike type preference.

### 4. Share
Built an interactive dashboard with KPI summaries, a day-of-week comparison, a monthly/seasonal trend, an hour-of-day trend, and a bike-type breakdown, with a slicer to filter by rider type.

## Key Findings

| Metric | Casual Riders | Members |
|---|---|---|
| Total rides | 2,112,111 (35.64%) | 3,814,670 (64.36%) |
| Avg. ride length | 	18.57 min | 12.07 min |
| Busiest day | Saturday | Tuesday |
| Busiest month | August | June |
| Peak hour | 5 PM | 5 PM |

**The story:** Members use Cyclistic bikes like a commuting tool — frequent, short, weekday rides with a clear evening peak. Casual riders use it more like a recreational activity — longer rides, concentrated on weekends, with usage swinging dramatically by season (as much as 13x higher in summer than winter, compared to a milder 4x swing for members). Bike type preference is broadly similar between the two groups and isn't a meaningful differentiator.

## Recommendation

Members commute — quick weekday rides. Casual riders explore — longer trips, mostly summer weekends. The clearest opportunity is converting casual weekend riders into members by promoting the weekday value of a membership (unlimited short commuter trips), since that's the usage pattern casual riders aren't yet taking advantage of.
