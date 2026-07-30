<<<<<<< HEAD
# ledger-api

Payments microservice for tokenising PANs and serving transaction metadata.
Deployed on Kubernetes in the `payments` namespace.

## Endpoints

| Method | Path            | Description                          |
|--------|-----------------|--------------------------------------|
| GET    | `/health`       | Liveness check                       |
| POST   | `/tokenize`     | `{"pan": "..."}` → opaque token      |
| GET    | `/transactions` | Recent transaction records           |
| POST   | `/import`       | Import a YAML configuration blob     |
| GET    | `/fetch?url=`   | Fetch a remote resource by URL       |
=======
# dodo-payments-assignment
Tassk - 1 assignment
>>>>>>> 2856eda78b5d59985d9235157793bbb328a7981a
