# SnowflakeRealTimeUseCase

# Overview


•	Challenges Faced by PacificRetail: The company deals with data silos, processing delays, scalability issues, data quality problems, and limitations in advanced analytics.
•	Goals for the Snowflake Solution: PacificRetail aims to create a centralized data source, reduce data processing time, improve data quality, and enable advanced analytics and machine learning.
•	Data Sources: Customer data (CSV files), product catalog (JSON files), and transactional logs (Parquet files) are the main data sources.
•	Expected Outcomes: Reduction in data processing time from 24 hours to 1 hour, 99% accuracy in cross-channel sales reporting, scalability to handle five times the current data volume, and enabling self-service analytics and ML models.


# Data lake to Snowflake: High-level solution


•	Data Sources and Storage: Data from various systems (CRM, inventory management, e-commerce) is stored in Azure Data Lake Storage (ADLS) before being ingested into Snowflake.
•	Three-Layer Architecture: The data is processed through three layers in Snowflake:

•	Bronze Layer: Raw data is stored without any transformations.
•	Silver Layer: Data is cleaned and transformed, with incremental merges for updates.
•	Gold Layer: Business-level aggregates and data marts are created for analytics.

•	Key Features of Snowflake: The architecture leverages Snowflake's features like external stages, COPY command, tasks, streams, time travel, and zero-copy cloning for efficient data processing and management.
 

# Snowflake project architecture diagram


•	Data Flow: Data from external systems (CRM, inventory, transactions) is stored in Azure Data Lake Storage (ADLS) and then moved to Snowflake.
•	Three-Layer Schema: A single Snowflake database contains three schemas: Bronze (raw data), Silver (cleaned and transformed data), and Gold (analytics-ready data).
•	Key Components: The architecture includes creating external stages, multiple schemas, tables, tasks for data movement, streams for incremental data, and views in the Gold layer for reporting.



Step1 : Create External Storage Integration. Follow the ExternalStorageIntegrationCreation notebook.
The result of describe query is as follows:
![image](https://github.com/user-attachments/assets/47d68615-c2ee-4313-a67d-2d11f2c95709)

You have to click on consent link and have to provide consent that i a'm allowing access to this integration. After that you need to copy the multitenant app name and by going into azure portal you have to create one iam role for with read and write access i.e. storage blob data contributor and click next where you need to add members to whom need to provide access. Here provide the name of the multitenant app.


# Customer data transformation
![image](https://github.com/user-attachments/assets/b2a3ccd9-b3fd-4faa-a460-b7365d7a57f9)


# Product data transformation
![image](https://github.com/user-attachments/assets/00adf4d1-e6e4-4859-8e5f-37a176338072)










