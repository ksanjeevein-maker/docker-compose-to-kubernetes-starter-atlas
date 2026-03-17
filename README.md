# Docker Compose to Kubernetes Starter Atlas

A starter atlas for teams translating Docker Compose setups into Kubernetes. It covers service mapping, configuration, secrets, persistence, probes, networking, and rollout thinking.

The mistake is treating Kubernetes as if it were Compose with more YAML. This pack focuses on the conceptual shift that prevents brittle cluster configs.

## Best use

- teaching teams how a Compose service maps to Deployment plus Service
- rewriting local container setups into starter Kubernetes manifests
- reviewing readiness, secrets, and storage assumptions during a migration
- creating a shared vocabulary for platform teams and app teams

## Core topics

- service to Deployment plus Service mapping
- config files, env vars, ConfigMaps, and Secrets
- volumes and persistence
- health checks vs readiness and liveness probes
- service discovery, scaling, and rollout semantics

## Questions this pack should answer well

- What does a Compose service become in Kubernetes?
- How should `.env` values split between ConfigMaps and Secrets?
- What replaces `depends_on` once startup ordering is not enough?
- How do Compose volume assumptions change when pods can move?

## When not to use this pack

- production-grade cluster operations at enterprise scale
- Helm templating or GitOps workflow design
- service mesh or advanced ingress architecture

## Agent formats

- Codex and generic portable guide: `AGENTS.md`
- Copilot repo instructions: `.github/copilot-instructions.md`
- Copilot skill: `.github/skills/docker-compose-kubernetes-atlas/`
- Cursor rule: `.cursor/rules/docker-compose-kubernetes-atlas.mdc`
- Antigravity-style rule: `.agent/rules/docker-compose-kubernetes-atlas.md`
- Antigravity-style skill: `.agent/skills/docker-compose-kubernetes-atlas/`

## Source policy

- Prefer official framework and library docs first.
- Prefer official GitHub org repos second.
- Re-check official docs when framework behavior may have changed.
