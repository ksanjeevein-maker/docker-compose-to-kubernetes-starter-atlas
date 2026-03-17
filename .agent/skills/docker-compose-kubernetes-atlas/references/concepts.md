# Docker Compose to Kubernetes Concepts

## Service mapping

- Compose habit: define one `service` that names the image, ports, env vars, and mounts.
- Kubernetes equivalent: split concerns across `Deployment`, `Service`, and related resources.
- Mental shift: runtime, networking, and rollout responsibilities are separate objects.
- Watchouts:
  - A pod is not a permanent machine.
  - Port exposure and traffic routing are separate decisions.

## Configuration and secrets

- Compose habit: put most configuration into environment blocks or `.env`.
- Kubernetes equivalent: use `ConfigMap` for non-secret configuration and `Secret` for sensitive values.
- Mental shift: config becomes a first-class deployable resource.
- Watchouts:
  - Do not dump every value into a Secret.
  - Update and rollout behavior depends on how the config is mounted or injected.

## Startup order and health

- Compose habit: rely on `depends_on` and container boot order.
- Kubernetes equivalent: use readiness probes, liveness probes, startup probes, and retry-friendly app behavior.
- Mental shift: Kubernetes cares about service health, not naive boot sequence.
- Watchouts:
  - `depends_on` does not really solve readiness even in Compose.
  - Probes should reflect useful health, not cargo-cult checks.
