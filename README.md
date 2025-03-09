# Partition Gap Finder in BigQuery

## Overview
This Google Colab notebook helps identify missing partitions in BigQuery tables using metadata from `INFORMATION_SCHEMA.PARTITIONS`. The process is divided into three steps:
1. **Setup & Authentication** – Import necessary libraries, authenticate, and configure parameters.
2. **Select Tables** – Retrieve partitioned tables and enable user selection.
3. **Find Missing Partitions** – Analyze partitions and output missing ranges to a Google Sheet.

## Prerequisites
- Access to Google Cloud with **BigQuery permissions**.
- A valid Google account to authenticate with **Google Sheets API**.
- The dataset being analyzed must have **partitioned tables**.

## Usage
### Step 1: Setup & Authentication
- The notebook starts by importing required libraries and authenticating the user for Google services.
- Parameters such as project, dataset, execution project, and partition granularity are configured.
- Parsing and date difference functions are set dynamically based on the selected granularity.
- Ensure the **execution project has the necessary permissions** to query metadata.

### Step 2: Select Tables
- A SQL query retrieves distinct partitioned tables from the dataset.
- The tables are displayed using an interactive widget, allowing the user to select relevant tables for analysis.
- If no partitioned tables match the selected criteria, an appropriate message is displayed.

### Step 3: Find Missing Partitions
- The user specifies whether to create a new Google Sheet and provides the sheet name for output.
- A BigQuery SQL query identifies missing partitions dynamically based on the selected granularity.
- If missing partitions are found, results are uploaded to Google Sheets and a link is provided; otherwise, a message confirms that no gaps exist.

## Output
- A table listing missing partition details, including table name, last known partition, next available partition, and the number of missing partitions based on granularity.
- If no missing partitions are found, the script informs the user.