# Docker-Based-Data-Warehouse-with-Mage-AI-API To PostgreSQL
deploying a Docker-based data warehouse using Mage AI, PostgreSQL (as source), and DuckDB (as destination) — perfect for analytics, KPIs, and scalable pipelines.
🚀 Automated Data Integration Pipeline with Mage + PostgreSQL 🌍📊
I recently built an end-to-end data pipeline that pulls country-level data from an open API, transforms it, and loads it into a PostgreSQL database using Mage, an open-source modern data orchestration tool. Here's a quick overview of the steps:
🔧 Pipeline Overview
1.	API Source:
Used the REST Countries API to fetch detailed information about every country.
2.	Data Loading Block (@data_loader):
Parsed the JSON response into a pandas DataFrame, handling nested fields safely (e.g., country names, capital, population).
3.	Transformation Block (@transformer):
o	Extracted relevant fields (name, region, area, population).
o	Created new columns like:
	is_in_asia – Boolean flag for Asian countries.
	area_density – People per square kilometer.
	population_millions – Converted raw population to millions for easier analysis.
4.	Export Block (@data_exporter):
Loaded the final dataset into a PostgreSQL database using Mage’s built-in integration.
o	Schema: public
o	Table: countries_data
5.	Database Setup:
Manually created or altered the target table in pgAdmin to match the transformed schema, including population_millions.
6.	Mage Pipeline Execution:
o	Ensured the environment was ready (Python, Mage, DB).
o	Fixed key errors: missing decorators, incorrect paths, and config issues.
o	Successfully ran and validated the pipeline end-to-end.
________________________________________
🔄 What I Learned:
•	Debugging and configuring Mage blocks.
•	Data transformation best practices with edge case handling.
•	PostgreSQL data loading using both to_sql() and Mage's Postgres IO block.
