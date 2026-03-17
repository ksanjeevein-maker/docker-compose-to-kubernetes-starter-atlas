# Docker Compose to Kubernetes Patterns

## One web service

Compose:

```yaml
services:
  api:
    image: my-api:latest
    ports:
      - "8080:8080"
```

Kubernetes:

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
          ports:
            - containerPort: 8080
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

## Secret injection

Kubernetes:

```yaml
env:
  - name: DATABASE_URL
    valueFrom:
      secretKeyRef:
        name: api-secrets
        key: database-url
```

## Readiness probe

Kubernetes:

```yaml
readinessProbe:
  httpGet:
    path: /health
    port: 8080
  initialDelaySeconds: 5
  periodSeconds: 10
```
