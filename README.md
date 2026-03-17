# Docker Compose to Kubernetes Starter Atlas

A starter atlas for teams translating Docker Compose setups into Kubernetes.

The value is in making the conceptual split between local orchestration convenience and cluster-oriented resources, rollout behavior, and health semantics.

## What makes this repo more useful now

- A stronger learning path for self-study and onboarding
- A worked example that shows the migration or debugging move end to end
- A mental-model diagram for fast orientation
- A review checklist for code review or design review
- Portable agent files for Codex, Copilot, Cursor, and Antigravity

## Learning path

- Start with the basic mapping from Compose service to Deployment plus Service.
- Then learn ConfigMaps, Secrets, and why `.env` is not the whole story anymore.
- Move into persistence, probes, and service discovery.
- Finish with rollout and scaling behavior so teams stop treating pods like fixed machines.

## High-signal traps

- Treating Kubernetes as Compose with more YAML.
- Using startup ordering as a substitute for readiness and retry-safe apps.
- Stuffing all configuration into secrets or env vars without a clear split.
- Assuming host-path volume behavior in a cluster where pods can move.

## Read this next

- Main portable guide: `AGENTS.md`
- Decision guide: `docs/decision-guide.md`
- Worked example: `examples/worked-example.md`
- Mental-model diagram: `docs/mental-model-map.md`
- Review checklist: `docs/review-checklist.md`
- Official references: `official-references.md`

## Agent formats

- Codex and generic portable guide: `AGENTS.md`
- Copilot repo instructions: `.github/copilot-instructions.md`
- Copilot skill: `.github/skills/docker-compose-kubernetes-atlas/`
- Cursor rule: `.cursor/rules/docker-compose-kubernetes-atlas.mdc`
- Antigravity-style rule: `.agent/rules/docker-compose-kubernetes-atlas.md`
- Antigravity-style skill: `.agent/skills/docker-compose-kubernetes-atlas/`
