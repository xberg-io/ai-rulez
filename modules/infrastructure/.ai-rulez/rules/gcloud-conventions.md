---
priority: medium
---

- GCP project: xberg-io, region: europe-west1
- Services: Cloud Run (compute), Cloud Storage (artifacts), Cloud SQL/AlloyDB (Postgres), Pub/Sub (messaging), Artifact Registry (images), Secret Manager (credentials)
- Naming: xberg-{service}-{environment}, buckets: xberg-io-{purpose}-{environment}
- Auth: workload identity federation — never service account keys
- IAM: least privilege, no owner-level for service accounts
- Use gcloud CLI for all operations — no manual console changes
