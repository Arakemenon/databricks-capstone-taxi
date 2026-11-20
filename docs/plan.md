# NYC Yellow Taxi Data Pipeline – Project Plan

## 1. Project Overview

This project is a learning project designed to build an end-to-end data engineering pipeline using Databricks.

The project uses NYC Yellow Taxi trip data for January, February, and March 2026.

The pipeline will implement the Medallion Architecture (Bronze, Silver, and Gold) to ingest, clean, transform, and analyse the taxi trip data.

## 2. Project Objectives

The main objectives are:

- Build a batch data ingestion pipeline using Databricks.
- Implement Bronze, Silver, and Gold layers.
- Use both SQL and Python (PySpark) for data transformations.
- Apply data quality checks and validation.
- Use Unity Catalog to organise and manage data.
- Develop analytical tables to support operational business questions.
- Document the pipeline and its design decisions.

## 3. Data Sources

| Dataset | Description |
|---|---|
| NYC Yellow Taxi Trip Data – January 2026 | Monthly taxi trip records |
| NYC Yellow Taxi Trip Data – February 2026 | Monthly taxi trip records |
| NYC Yellow Taxi Trip Data – March 2026 | Monthly taxi trip records |
| Taxi Zone Lookup | Lookup table containing taxi location zones |

Source: NYC Taxi and Limousine Commission (TLC).

## 4. Technology Stack

| Technology | Purpose |
|---|---|
| Databricks Free | Data engineering platform |
| Unity Catalog | Data governance and organisation |
| Delta Lake | Data storage |
| SQL | Data transformations and analysis |
| Python / PySpark | Data processing |
| GitHub | Version control and project documentation |

## 5. Data Architecture

The project follows the Medallion Architecture.

### Bronze Layer
- Ingest raw Yellow Taxi CSV files.
- Preserve source data.
- Store data in Delta format.
- Maintain ingestion metadata.

### Silver Layer
- Clean and standardise data.
- Handle missing and invalid values.
- Apply data quality checks.
- Join taxi trip data with zone lookup information.

### Gold Layer
- Create analytical tables.
- Aggregate trip and revenue information.
- Support operational reporting and analysis.

## 6. Business Questions and Readers

The primary audience is operations teams interested in understanding taxi activity and operational performance.

| Business Question | Who Asks It? | How Often? | Gold Table |
|---|---|---|---|
| How many taxi trips occur each day? | Operations team | Daily | gold_daily_trips |
| Which pickup zones have the highest trip volumes? | Operations team | Daily | gold_zone_demand |
| What are the busiest hours for taxi trips? | Operations team | Daily | gold_hourly_demand |
| What is the average trip distance and duration? | Operations team | Weekly | gold_trip_metrics |
| How much revenue is generated from taxi trips? | Operations team | Monthly | gold_monthly_revenue |

## 7. Data Ingestion Strategy

The project will use batch ingestion.

Monthly Yellow Taxi CSV files will be loaded into Databricks using Unity Catalog Volumes.

The initial project scope covers January, February, and March 2026.

## 8. Access Strategy

The project will use a simple access model.

- Use the workspace catalog for project data.
- Organise data into Bronze, Silver, and Gold schemas.
- Use the available workspace permissions.
- Keep the project simple for the learning environment.

## 9. Project Deliverables

- GitHub repository with project documentation.
- Databricks setup notebook.
- Bronze ingestion pipeline.
- Silver transformation pipeline.
- Gold analytical tables.
- Data quality checks.
- Project README with architecture and implementation details.

## 10. Success Criteria

The project will be considered successful when:

- All three monthly datasets are ingested successfully.
- Data is stored in the Bronze, Silver, and Gold layers.
- Data quality checks are implemented.
- Gold tables answer the defined business questions.
- Both SQL and PySpark are used.
- The complete pipeline is documented and reproducible.
