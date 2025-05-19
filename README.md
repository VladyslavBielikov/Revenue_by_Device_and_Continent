# SQL Analysis: Revenue, Accounts, and Sessions by Continent

This project contains a BigQuery SQL query designed to analyze key performance metrics across **continents**. It aggregates session events, revenue, and account data to provide a detailed breakdown by geographic region.

## Dataset Overview

The query utilizes the following tables from the `data-analytics-mate.DA` dataset:

- `session_params`: Contains information about session
- `order`: Represents informayion about customer purchases
- `product`: Contains product information
- `account`: User account information
- `account_session`: Maps accounts to sessions

## Query Structure

The SQL logic is organized using Common Table Expressions (CTEs) to compute insights step by step:

### 1. `session_events`
Counts the total number of **events** grouped by `continent`.

### 2. `revenue_cnt`
Calculates:
- Total **revenue** by continent 
- Revenue from **mobile** and **desktop** devices separately 
- Helps compare device performance geographically

### 3. `account_cnt`
Calculates:
- Total number of **unique accounts** by continent 
- Number of **verified accounts** (summing the `is_verified` flag)

### 4. `session_cnt`
Calculates the total number of **unique sessions** by continent.

### 5. Final SELECT
Joins all aggregated data into one **summary table**, including:
- Revenue (total, by device)
- Share of each continent’s revenue relative to the **global total**
- Account and session counts

## Output Metrics

The final output provides the following columns for each continent:

- `revenue`: Total revenue
- `Revenue_from_Mobile`: Revenue generated from mobile devices
- `Revenue_from_Desktop`: Revenue generated from desktop devices
- `perc_Revenue_from_Total`: Revenue share from this continent (as % of total)
- `account_count`: Number of unique accounts
- `verified_account`: Number of verified accounts
- `session_count`: Number of distinct sessions

