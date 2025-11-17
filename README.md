# DataModeling_Building_Slowly_Changing_Dimensions-SCDs-
This project provides a complete Slowly Changing Dimension (SCD) implementation for NBA player data using PostgreSQL. It is designed to track how player attributes—such as scoring_class and is_active—change over different seasons, and to maintain historical records in a structured SCD Type 2 format.

## 📌 Overview

The project includes two main pieces of logic:

1. **Initial SCD build**:  
   Build the `players_scd` table from historical data up to a given season (e.g. 2021).

2. **Incremental SCD update**:  
   Extend the SCD table for the next season (e.g. 2022) by comparing the current season data (`players`) with last season’s SCD snapshot (`players_scd`).

---

## 📂 Tables & Types

### `players_scd` table (SCD dimension)

```sql
-- CREATE TABLE players_scd (
-- 	player_name   	  TEXT,
-- 	scoring_class 	  scoring_class,
-- 	is_active 	   BOOLEAN,
-- 	start_season   INTEGER,
-- 	end_season     INTEGER,
-- 	current_season INTEGER,
-- 	PRIMARY KEY(player_name, start_season)
-- )
