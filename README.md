# Olist Modern ELT Warehouse (Azure Blob → Snowflake → dbt → Tableau)

End-to-end batch ELT project using the Olist Brazilian e-commerce dataset:
- Land raw CSVs in Azure Blob Storage (bronze)
- Load into Snowflake (RAW)
- Transform with dbt (STG → MART) with tests + docs
- Visualize KPIs in Tableau

## Architecture
Azure Blob Storage → Snowflake (RAW/STG/MART) → dbt models/tests/docs → Tableau dashboards

## Tech Stack
Azure Blob Storage, Snowflake, dbt (dbt-snowflake), SQL, Tableau

## Project Structure
- `dbt/olist_dbt/` — dbt project (models, tests, macros)
- `docs/` — proof artifacts + screenshots (Phase 0+)
- `dashboards/` — Tableau workbook/screenshots (later)
- `infra/` — infra notes/scripts (later)

## Setup (local)
### dbt
- dbt profile is kept locally at `~/.dbt/profiles.yml` (not committed)
- Password stored via env var: `DBT_SNOWFLAKE_PASSWORD`

Validate connection:
```bash
cd dbt/olist_dbt
dbt debug
Run models:

dbt run
dbt test
Phase 0 Proof
See docs/phase0-proof.md for:

Azure storage container screenshot

Snowflake warehouse/db/schemas screenshot

dbt debug output (sanitized)
