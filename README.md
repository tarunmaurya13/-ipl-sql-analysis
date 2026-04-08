# 🏏 IPL Ball-by-Ball SQL Analysis

![SQL](https://img.shields.io/badge/SQL-MySQL-blue?style=for-the-badge&logo=mysql)
![Status](https://img.shields.io/badge/Status-Active-green?style=for-the-badge)
![Level](https://img.shields.io/badge/Level-Beginner%20to%20Advanced-orange?style=for-the-badge)
![Queries](https://img.shields.io/badge/Queries-50+-purple?style=for-the-badge)

> A complete SQL portfolio project analyzing IPL cricket data using real ball-by-ball match data. Covers Aggregations, JOINs, Subqueries, CTEs, and Window Functions — from beginner to advanced level.

---

## 📁 Project Structure

```
ipl-sql-analysis/
│
├── 📂 dataset/
│   └── schema.sql                  # Table structure
│
├── 📂 beginner/
│   ├── 01_total_runs_per_match.sql
│   ├── 02_extra_types_frequency.sql
│   ├── 03_top10_batsmen.sql
│   ├── 04_dismissal_types.sql
│   └── 05_high_strike_rate_matches.sql
│
├── 📂 intermediate/
│   ├── 01_top5_bowlers.sql
│   ├── 02_run_rate_per_over.sql
│   ├── 03_best_innings_batsmen.sql
│   ├── 04_economical_bowlers.sql
│   ├── 05_most_catches.sql
│   ├── 06_innings_comparison.sql
│   └── 07_powerplay_vs_death_overs.sql
│
├── 📂 advanced/
│   ├── 01_batting_scorecard.sql
│   ├── 02_allrounders_comparison.sql
│   ├── 03_best_worst_innings.sql
│   ├── 04_closest_finish.sql
│   ├── 05_momentum_shifts.sql
│   ├── 06_hatrick_detection.sql
│   ├── 07_player_of_match.sql
│   ├── 08_required_run_rate.sql
│   └── 09_ipl_points_table.sql
│
├── 📂 aggregates/
│   ├── 01_total_tournament_runs.sql
│   ├── 02_avg_runs_per_innings.sql
│   ├── 03_balls_bowled_per_bowler.sql
│   ├── 04_max_min_score_per_over.sql
│   ├── 05_extras_per_match.sql
│   ├── 06_bowlers_with_10_plus_wickets.sql
│   ├── 07_economy_rate_bowlers.sql
│   ├── 08_phase_wise_runs.sql
│   ├── 09_dot_ball_percentage.sql
│   └── 10_batting_average.sql
│
├── 📂 joins/
│   ├── 01_inner_join_batsman_runs.sql
│   ├── 02_left_join_all_players.sql
│   ├── 03_bowler_wickets.sql
│   ├── 04_batting_pairs.sql
│   ├── 05_fielder_catches.sql
│   ├── 06_batsman_vs_bowler.sql
│   ├── 07_country_wise_runs.sql
│   ├── 08_left_vs_right_hand.sql
│   ├── 09_bowling_skill_wickets.sql
│   └── 10_complete_player_profile.sql
│
├── 📂 subqueries/
│   ├── 01_above_average_batsmen.sql
│   ├── 02_highest_total_match.sql
│   ├── 03_bowlers_no_wickets.sql
│   ├── 04_correlated_ball_runs.sql
│   ├── 05_top_scorer_per_match.sql
│   ├── 06_extras_above_20.sql
│   ├── 07_exists_six_powerplay.sql
│   ├── 08_below_avg_economy.sql
│   ├── 09_better_in_2nd_innings.sql
│   └── 10_winner_lower_powerplay.sql
│
├── 📂 ctes/
│   ├── 01_top5_batsmen.sql
│   ├── 02_batting_bowling_combined.sql
│   ├── 03_economy_filter.sql
│   ├── 04_phase_wise_runs.sql
│   ├── 05_best_over_per_match.sql
│   ├── 06_batting_average.sql
│   ├── 07_closest_matches.sql
│   ├── 08_recursive_over_sequence.sql
│   ├── 09_player_of_match_score.sql
│   └── 10_full_scorecard_pipeline.sql
│
├── 📂 window-functions/
│   ├── 01_running_total.sql
│   ├── 02_rank_batsmen_per_match.sql
│   ├── 03_lag_previous_over.sql
│   ├── 04_lead_next_over.sql
│   ├── 05_ntile_performance_groups.sql
│   ├── 06_over_pct_contribution.sql
│   ├── 07_best_worst_innings.sql
│   ├── 08_rolling_3_over_avg.sql
│   ├── 09_wicket_fall_sequence.sql
│   └── 10_vs_career_average.sql
│
└── 📄 README.md
```

---

## 🗄️ Database Schema

### `ipl_table` — Ball by Ball Data
| Column | Type | Description |
|---|---|---|
| Match_Id | INT | Unique match identifier |
| Innings_Id | INT | 1 = First, 2 = Second innings |
| Over_Id | INT | Over number (1–20) |
| Ball_Id | INT | Ball number in over |
| Team_Batting_Id | INT | Batting team ID |
| Team_Bowling_Id | INT | Bowling team ID |
| Striker_Id | INT | Batsman on strike |
| Non_Striker_Id | INT | Batsman at non-striker end |
| Bowler_Id | INT | Bowler ID |
| Batsman_Scored | INT | Runs scored by batsman |
| Extra_Type | VARCHAR | Type of extra (wide/noball etc.) |
| Extra_Runs | INT | Extra runs conceded |
| Player_dissmial_id | INT | Dismissed player ID |
| Dissimal_Type | VARCHAR | How player got out |
| Fielder_id | INT | Fielder involved in dismissal |
| Match_Winner_Id | INT | Winning team ID |
| Strike_Rate | FLOAT | Ball-level strike rate |

### `player` — Player Details
| Column | Type | Description |
|---|---|---|
| Player_Id | INT | Unique player identifier |
| Player_Name | VARCHAR | Full name |
| DOB | DATE | Date of birth |
| Batting_Hand | VARCHAR | Left / Right hand |
| Bowling_Skill | VARCHAR | Pace / Spin / Medium |
| Country | VARCHAR | Nationality |
| Is_Umpire | BOOLEAN | Umpire flag |

---

## 📚 Topics Covered

| Topic | Queries | Key Concepts |
|---|---|---|
| 🔢 Aggregates | 10 | SUM, AVG, COUNT, HAVING, NULLIF |
| 🔗 JOINs | 10 | INNER, LEFT, SELF, CROSS, multi-alias |
| 🔍 Subqueries | 10 | Scalar, Correlated, EXISTS, NOT IN |
| 🧱 CTEs | 10 | Single, Multiple, Chained, Recursive |
| 🪟 Window Functions | 10 | RANK, LAG/LEAD, NTILE, ROWS BETWEEN |
| 🟢 Beginner | 5 | Basic filters and aggregations |
| 🟡 Intermediate | 7 | Multi-table, HAVING, CASE WHEN |
| 🔴 Advanced | 9 | Rolling windows, Self JOINs, NRR |

---

## 🔥 Highlight Queries

### 🏆 IPL Points Table with NRR
```sql
-- Calculates full standings with Net Run Rate tiebreaker
-- Uses 5 CTEs + ROW_NUMBER() window function
-- See: advanced/09_ipl_points_table.sql
```

### 🎯 Hat-Trick Detection
```sql
-- Finds 3 consecutive wicket balls by same bowler
-- Uses SELF JOIN 3 times + ROW_NUMBER()
-- See: advanced/06_hatrick_detection.sql
```

### 📊 Gaps & Islands — Consecutive Dot Balls
```sql
-- Finds longest dot ball streaks per batsman
-- Classic SQL interview pattern
-- See: advanced/05_momentum_shifts.sql
```

---

## 💡 Key SQL Concepts Cheat Sheet

```sql
-- RANK vs DENSE_RANK vs ROW_NUMBER
Runs:  100, 85, 85, 60
RANK()        → 1, 2, 2, 4   -- skips after tie
DENSE_RANK()  → 1, 2, 2, 3   -- no gaps
ROW_NUMBER()  → 1, 2, 3, 4   -- always unique

-- LAG vs LEAD
LAG(col)  → previous row value
LEAD(col) → next row value

-- ROWS BETWEEN frames
UNBOUNDED PRECEDING → CURRENT ROW  = running total
2 PRECEDING → CURRENT ROW          = rolling 3-row window
UNBOUNDED PRECEDING → UNBOUNDED FOLLOWING = full partition
```

---

## 🚀 How to Run

### 1. Clone the repository
```bash
git clone https://github.com/YOUR_USERNAME/ipl-sql-analysis.git
cd ipl-sql-analysis
```

### 2. Set up the database
```bash
mysql -u root -p < dataset/schema.sql
```

### 3. Run any query
```bash
mysql -u root -p ipl < beginner/01_total_runs_per_match.sql
```

### Or open in MySQL Workbench
- Open MySQL Workbench
- Connect to your local server
- Open any `.sql` file from the project
- Press `Ctrl + Shift + Enter` to run

---

## 📈 Skills Demonstrated

- ✅ Writing clean, readable SQL with proper formatting
- ✅ Using CTEs for modular query design
- ✅ Window functions for ranking and trend analysis
- ✅ Correlated subqueries for row-level comparisons
- ✅ Multi-table JOINs with aliasing
- ✅ Handling NULLs with COALESCE and NULLIF
- ✅ Business metric calculation (NRR, Economy, Batting Avg)
- ✅ Real-world cricket analytics use cases

---

## 🛠️ Tools Used

![MySQL](https://img.shields.io/badge/MySQL-8.0-blue?logo=mysql)
![Workbench](https://img.shields.io/badge/MySQL-Workbench-orange?logo=mysql)
![Git](https://img.shields.io/badge/Git-GitHub-black?logo=github)

---

## 👤 Author

**Your Name**
- GitHub: [Tarun_16](https://github.com/your_username)
- LinkedIn: [](https://www.linkedin.com/in/tarun-maurya-2010272a7/)

---

## ⭐ Show Your Support

If this project helped you learn SQL, please give it a ⭐ on GitHub!

---

*Made with ❤️ and lots of SQL queries*
