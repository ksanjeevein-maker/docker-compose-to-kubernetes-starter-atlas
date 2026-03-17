# Worked example: API plus database migration starter

This example maps a small two-service Compose setup into starter Kubernetes resources with configuration, secrets, and probes.

## Docker Compose

```yaml
services:
  api:
    image: my-api:latest
    ports:
      - "8080:8080"
    depends_on:
      - db
  db:
    image: postgres:16
```

## Kubernetes

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: api
spec:
  template:
    spec:
      containers:
        - name: api
          image: my-api:latest
          readinessProbe:
            httpGet:
              path: /health
              port: 8080
---
apiVersion: v1
kind: Service
metadata:
  name: api
spec:
  ports:
    - port: 8080
      targetPort: 8080
```

## What to notice

- Service exposure, rollout, and health become separate concerns.
- The database dependency needs readiness-aware design, not just startup ordering.
- This starter layout gives teams a safer baseline for real manifests.
