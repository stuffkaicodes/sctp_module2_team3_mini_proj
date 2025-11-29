# sctp_module2_team3_mini_proj
Architecture Diagram:
                 ┌──────────┐
Source CSVs  →   │ DuckDB   │  (local landing + validation)
                 └────┬─────┘
                      │
                      ▼
                ┌────────────┐
                │  Meltano   │  (ELT orchestration + Singer taps)
                └────┬───────┘
                     │
                     ▼
                ┌────────────┐
                │ BigQuery   │  (cloud warehouse, curated + serving)
                └────┬───────┘
                     │
          ┌──────────┴───────────┐
          ▼                      ▼
     ┌────────┐             ┌──────────┐
     │  dbt   │             │ Dagster  │
     │models  │             │pipelines │
     └────────┘             └──────────┘
          │                       │
          └───────────┬───────────┘
                      ▼
               ┌───────────┐
               │  Jupyter  │ (analysis, ML, notebooks)
               └───────────┘


Tech stack:
| Component     | Tool                                      |
| ------------- | ----------------------------------------- |
| Ingestion     | Pure Python scripts (pandas / connectors) |
| Local Storage | DuckDB                                    |
| Data Warehouse| BigQuery                                  |
| Transform     | dbt                                       |
| Orchestration | Dagster                                   |
| Analysis      | Jupyter Notebooks                         |
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
