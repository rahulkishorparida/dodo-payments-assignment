# Dodo Payments Security Assessment

Payments microservice for tokenising PANs and serving transaction metadata.

## Endpoints

| Method | Path | Description |
|--------|------|-------------|
| GET | `/health` | Liveness check |
| POST | `/tokenize` | `{"pan": "..."}` → opaque token |
| GET | `/transactions` | Recent transaction records |
| POST | `/import` | Import a YAML configuration blob |
| GET | `/fetch?url=` | Fetch a remote resource by URL |

---

## Repository Structure

- **app/** – Application source code and Dockerfile
- **deploy/** – Kubernetes manifests
- **gatekeeper/** – OPA Gatekeeper policies
- **istio/** – Istio configuration
- **sealedsecret.yaml** – Bitnami Sealed Secret
- **kind-config.yaml** – Kind cluster configuration

---

## Repositories

- **Application Repository:** https://github.com/<your-user>/ledger-api-assignment
- **GitOps Repository:** https://github.com/<your-user>/dodo-payments-gitops

---

## Task 1 – Secure CI/CD

- GitHub Actions
- Semgrep
- Gitleaks
- Trivy
- Cosign
- SLSA Provenance

---

## Task 2 – Kubernetes Security

- ServiceAccount & RBAC
- SecurityContext
- Gatekeeper
- Sealed Secrets
- A separate GitOps repository (`dodo-payments-gitops`) is configured as the source of truth for Kubernetes  manifests.

ArgoCD is configured with:

- Automated Sync
- Self Heal

---

## Task 3 – Service Mesh & Zero Trust

- Istio
- STRICT mTLS
- AuthorizationPolicy
- Kubernetes NetworkPolicy

Verified:

- Authorized workload → HTTP 200
- Unauthorized workload → HTTP 403

