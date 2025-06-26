# 🏏 IPL Datasets Analysis using SQL

This project was developed as the final capstone for the **"SQL for Data Analysis"** course. 
It focuses on exploring and analyzing Indian Premier League (IPL) match and ball-by-ball datasets using SQL to gain meaningful insights into team performances, player statistics, venues, and match outcomes.

---

## 📁 Dataset Details

- **`IPL_matches.csv`**: Contains match-level information like date, venue, toss decision, winner, etc.
- **`IPL_Ball.csv`**: Contains detailed ball-by-ball data including batsman, bowler, runs scored, and dismissals.

---

## 🛠️ Tools & Technologies Used

- PostgreSQL (SQL queries and analysis)
- CSV File Import (`COPY` command)
- SQL concepts: Joins, Aggregations, Window Functions, Subqueries

---

## 📌 Key Objectives and Tasks

### 🔨 Data Engineering & Cleaning
- Created `ipl_matches` and `ipl_ball` tables with proper data types.
- Imported CSV files using `COPY` after handling errors like string truncation.
- Updated column sizes for real-world data fields (umpire names, venues).
- Standardized team names (e.g., "Rising Pune Supergiants" → "Rising Pune Supergiant").

### 🧠 Data Transformation
- Added `ball_result` column using `CASE` to classify deliveries as:
  - `boundary`, `dot`, or `other`
- Created `ball_id` column combining match ID, over, and ball (e.g., `12345-1-5-3`).
- Used `ROW_NUMBER()` window function to detect duplicate deliveries.

### 📊 Analytical Queries Performed
- Total boundaries and dot balls overall and per team.
- Total dot balls bowled by each team.
- Dismissals by type (`caught`, `bowled`, `run out`, etc.).
- Top venues by total runs scored.
- Year-wise run distribution at Eden Gardens.
- Top bowlers conceding highest extra runs.
- Duplicate delivery entries using `r_num` and subqueries.

---

## 📂 Output Tables Created

| Table Name         | Description                                      |
|--------------------|--------------------------------------------------|
| `ipl_matches`      | Original match-level data                        |
| `ipl_ball`         | Original delivery-level data                     |
| `deliveries_v02`   | Added column `ball_result`                       |
| `deliveries_v03`   | Joined match info (venue, date)                  |
| `deliveries_v04`   | Added unique `ball_id`                           |
| `deliveries_v05`   | Added row numbers using window function          |
| `matches_corrected`| Corrected inconsistent team names                |

---

## 📈 Insights Sample

- **Total Boundaries:** 31,468  
- **Total Dot Balls:** 67,841  
- **Cities Hosting Matches:** 33  
- **Duplicate Ball IDs Found:** 10  
- **Top Run-Scoring Venue:** Eden Gardens  

---

Author

Uma Sankar Rao Bellamkonda
SQL Learner
