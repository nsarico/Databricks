---

### 2. Databricks Repository (`README.md`)

```markdown
# Databricks Data Warehouse

Lakehouse transformations, dimensional modeling, and analytical data marts built on Databricks using Delta Lake and the Medallion Architecture (`Bronze` → `Silver` → `Gold`).

## Overview

This repository houses the core warehouse logic running on Databricks:
- **Bronze:** Raw ingested tables registered from landing storage with minimal transformation and full audit metadata.
- **Silver:** Cleaned, deduplicated, conformed entities with enforced data quality rules and Slowly Changing Dimensions (SCD Type 2).
- **Gold:** Dimensional star schemas (`fct_*`, `dim_*`) and aggregated analytical marts optimized for BI and downstream analytics.

## Repository Structure

```text
├── notebooks/              # Exploratory analysis & ad-hoc validation notebooks
├── src/
│   ├── bronze/             # Auto Loader / batch ingestion into Delta tables
│   ├── silver/             # Cleansing, deduplication, and SCD Type 2 merge logic
│   ├── gold/               # Fact and dimension models + business metrics
│   └── utils/              # Shared Spark/Delta helpers, schema definitions, quality checks
├── workflows/              # Databricks Asset Bundles (DABs) / job definitions
├── tests/                  # PySpark unit tests & transformation assertions
├── databricks.yml          # Databricks Asset Bundle configuration
├── pyproject.toml          # Python dependencies & dev tools
└── README.md
