# SpaceX Launch Analytics

## Project Overview
This project explores commercial spaceflight data from SpaceX through the lens of relational data modeling and SQL-based analytics. The primary objective is to analyze launch reliability, rocket utilization, and cost efficiency by combining mission-level data with rocket specifications in a structured database environment.

Rather than treating the data as flat files or in-memory objects, the project is intentionally designed around a relational database approach to reflect real-world data engineering and analytics workflows.

---

## Analytical Goal
Commercial spaceflight involves high costs and complex engineering trade-offs. By linking launch outcomes to the rockets that performed them, this project aims to answer questions such as:

- Which missions were the most expensive based on the rocket used?
- How reliable are active rockets compared to inactive ones?
- Which rocket has been used most frequently across all missions?
- What is the total financial impact of failed launches?

These questions are answered using SQL joins and aggregate functions, reinforcing database-centric analysis rather than application-level filtering.

---

## Data Source
The dataset is obtained from the public SpaceX API (version 4), which provides structured and well-documented data on SpaceX rockets and launches. Two logically distinct datasets are used:

- Rocket metadata, which changes rarely and describes the launch vehicles.
- Launch history, which records individual mission events over time.

This separation naturally lends itself to a normalized relational design.

---

## Data Modeling Approach
The project uses a normalized schema consisting of two core entities:

- **Rockets**, representing launch vehicles and their characteristics.
- **Launches**, representing individual missions and their outcomes.

Each launch references exactly one rocket through a foreign key relationship. This design minimizes redundancy, enforces data consistency, and enables efficient analytical queries using joins.

Primary keys uniquely identify records in each table, while foreign keys preserve the logical relationship between rockets and launches.

---

## ETL Concept
The project follows a classic ETL (Extract, Transform, Load) pattern:

- **Extract**: Data is fetched from the SpaceX API endpoints.
- **Transform**: Relevant attributes are selected, cleaned, and aligned with the relational schema.
- **Load**: Data is inserted into the SQLite database in the correct order to satisfy foreign key constraints.

This process mirrors production data pipelines where reference data must be loaded before dependent event data.

---

## SQL-Based Analysis
All analytical questions are answered directly in SQL using JOIN operations, GROUP BY clauses, and aggregate functions such as COUNT and SUM. This ensures that:

- Computation is pushed to the database layer.
- Results are reproducible and logically transparent.
- The analysis reflects best practices in relational analytics.

No Python-side filtering or aggregation is used for answering analytical questions.

---

## Key Skills Demonstrated
This project demonstrates competency in:

- Relational database design and normalization
- Use of primary and foreign keys
- SQL JOINs and aggregations
- Python integration with SQLite
- ETL-style data workflows
- Analytical reasoning using structured data

---

## Project Significance
By combining real-world API data with relational modeling and SQL analytics, this project bridges the gap between theoretical database concepts and practical data engineering tasks. It reflects workflows commonly used in analytics engineering, backend data systems, and technical data analysis roles.
