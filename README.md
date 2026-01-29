# Kestra Flows
  
The flows cover local development with Postgres, working with NYC Taxi data, and orchestrating end‑to‑end pipelines on Google Cloud (GCS + BigQuery).

## Flows overview

- `01_hello_world.yaml`  
  Simple “hello world” flow to validate the Kestra setup, execution, and UI.

- `02_python.yaml`  
  Runs a basic Python task to demonstrate how to execute Python code from Kestra.

- `03_getting_started_data_pipeline.yaml`  
  First end‑to‑end data pipeline: downloads data, processes it, and writes the result using Kestra tasks.

- `04_postgres_taxi.yaml`  
  Ingests NYC Taxi data into a local Postgres database using Dockerized Postgres.

- `05_postgres_taxi_scheduled.yaml`  
  Scheduled version of the Postgres taxi pipeline, showing how to use triggers (cron‑like scheduling) in Kestra.

- `06_gcp_kv.yaml`  
  Sets up key–value configuration for GCP (project id, dataset, bucket name, location) inside Kestra’s KV Store.

- `07_gcp_setup.yaml`  
  Uses the GCP configuration to:
  - create a GCS bucket  
  - create a BigQuery dataset

- `08_gcp_taxi.yaml`  
  Parameterized pipeline that:
  - downloads NYC Taxi CSV data from the Zoomcamp GitHub releases  
  - uploads the file to GCS  
  - creates external and internal BigQuery tables  
  - merges data into partitioned fact tables for yellow/green trips

- `09_gcp_taxi_scheduled.yaml`  
  Scheduled version of the GCP taxi pipeline, useful for regularly loading new monthly data.

## Prerequisites

- Kestra running via Docker / Docker Compose  
- Local Postgres (for the earlier modules)  
- A GCP project with:
  - a service account JSON key
  - permissions for GCS and BigQuery
- `GOOGLE_APPLICATION_CREDENTIALS` configured in the Kestra container so all GCP plugin tasks can authenticate.

## How to use

1. Import the YAML files into Kestra (or mount them in the Kestra storage directory).
2. Update the KV Store values:
   - `GCP_PROJECT_ID`
   - `GCP_DATASET`
   - `GCP_BUCKET_NAME`
   - `GCP_LOCATION`
3. Run the setup flows:
   - `06_gcp_kv`
   - `07_gcp_setup`
4. Use `08_gcp_taxi` (and optionally `09_gcp_taxi_scheduled`) to process NYC Taxi data end‑to‑end on GCP.
