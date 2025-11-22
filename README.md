# sctp_module2_team3_mini_proj
Architecture Diagram:
                +-------------------+
                |   Source Files    |
                |  (CSV / Public)   |
                +---------+---------+
                          |
        (Pure Python ingestion scripts)
                          |
                          v
            +---------------------------+
            |      Raw Data Layer       |
            |    (BigQuery / Postgres)  |
            +-------------+-------------+
                          |
                (dbt / SQL transforms)
                          |
                          v
            +---------------------------+
            |  Analytics Data Warehouse |
            |       Star Schema         |
            +-------------+-------------+
                          |
                (Data Quality Checks)
          dbt tests + Great Expectations
                          |
                          v
            +---------------------------+
            |     Clean / Trusted       |
            |       Data Models         |
            +-------------+-------------+
                          |
                (Jupyter / SQL analysis)
                          |
                          v
            +---------------------------+
            |       EDA & Insights      |
            +---------------------------+


Tech stack:
| Component     | Tool                                      |
| ------------- | ----------------------------------------- |
| Ingestion     | Pure Python scripts (pandas / connectors) |
| Storage       | GCS / BigQuery OR Postgres                |
| Transform     | SQL + dbt                                 |
| Orchestration | Airflow (Docker Compose)                  |
| Data Quality  | Great Expectations + dbt tests            |
| Analysis      | Jupyter Notebooks                         |
| CI/CD         | GitHub Actions, pytest, pre-commit        |
| Presentation  | Google Slides / PowerPoint                |


# Readiness checklist
1. Local dev environment created and reproducible.
2. Run local db creation.
3. create a .env file for Credentials/secrets stored securely

# Step-by-step preparation (detailed)
## 1. Local dev environment created and reproducible.
    # create environment or resue conda bde
```bash
    conda acrivate dbe
```
## 2. Run local db creation.
    # you will see a mini_proj.db create in db/ folder
```bash
    python db/create_duckdb.py 
```
## 3. create a .env file for Credentials/secrets stored securely
```bash
   touch .env
```
```
GCP_PROJECT=my-gcp-project
GOOGLE_APPLICATION_CREDENTIALS=/path/to/service_account.json
PG_HOST=...
PG_USER=...
PG_PASSWORD=...
```
