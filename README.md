# Azure Big Data Pipeline using Data Lake & Synapse
## Video : https://drive.google.com/file/d/12ZhuBGjfocFXw1b-Jks5Aavs3rfZxp_6/view?usp=drive_link

## Overview

This project demonstrates an end-to-end Azure-based data engineering pipeline designed to analyse the relationship between nutritional quality and educational attainment across regions in the UK.

The solution uses Azure cloud services to ingest, store, query, and analyse large datasets efficiently using a serverless architecture.

## Architecture

The pipeline follows this flow:

**Data Ingestion → Storage → Querying → Transformation → Visualisation**

* Raw datasets stored in **Azure Data Lake Gen2**
* Queried using **Azure Synapse Analytics (serverless SQL)**
* Processed using **schema-on-read (OPENROWSET)**
* Transformed and joined for analysis
* Visualised within Synapse Studio

## Tech Stack

* Azure Data Lake Gen2
* Azure Synapse Analytics (Serverless SQL)
* SQL (OPENROWSET, JOIN, Aggregations)

## Datasets

* Educational Attainment Dataset (DfE)
* Nutritional Intake Dataset (DEFRA)

Combined dataset size: **15,000+ records**

## Key Features

* Serverless data processing
* Schema-on-read querying
* Multi-dataset integration
* Scalable cloud architecture
* End-to-end data pipeline design

## Example Query

```sql
SELECT COUNT(*) AS total_rows
FROM OPENROWSET(
    BULK 'https://<storage-account>.dfs.core.windows.net/<container>/education.csv',
    FORMAT = 'CSV',
    PARSER_VERSION = '2.0',
    HEADER_ROW = TRUE
) AS result;
```

## Data Transformation

* Joined datasets by region
* Calculated average higher education progression rates
* Calculated average sugar intake by region
* Applied grouping and aggregation logic

## Key Insights

* Regions with higher sugar intake showed lower progression to higher education
* London showed the highest education progression and lowest sugar intake

## Outcomes

* Built a cloud-native Azure data pipeline
* Processed and analysed **15k+ records**
* Demonstrated serverless querying with Synapse
* Generated actionable insights from combined datasets

## Future Improvements

* Add real-time ingestion
* Integrate machine learning
* Add Power BI dashboard layer

## Author

Adekola Olagunju
LinkedIn: https://www.linkedin.com/in/adekola-olagunju-04126b6b
