# Compose to Kubernetes Atlas Codex and Agent Guide

Use this repository when a task involves:

- teaching teams how a Compose service maps to Deployment plus Service
- rewriting local container setups into starter Kubernetes manifests
- reviewing readiness, secrets, and storage assumptions during a migration
- creating a shared vocabulary for platform teams and app teams

## Preferred workflow

1. Identify the source habit, framework concept, or failure mode first.
2. Translate the mental model before jumping to code.
3. Use the local skill references instead of inventing mappings from memory.
4. Prefer native target-platform patterns over transliteration.
5. Add official links when the user wants citations or deeper study.

## Primary local references

- Skill entrypoint: `.github/skills/docker-compose-kubernetes-atlas/SKILL.md`
- Antigravity-style skill entrypoint: `.agent/skills/docker-compose-kubernetes-atlas/SKILL.md`
- Concept mappings: `.github/skills/docker-compose-kubernetes-atlas/references/concepts.md`
- Rewrite patterns: `.github/skills/docker-compose-kubernetes-atlas/references/patterns.md`
- Official links: `.github/skills/docker-compose-kubernetes-atlas/references/official-links.md`
- Human reference pack: `official-references.md`

## Output shape

- Start with the target-side equivalent in one sentence.
- Explain the mental shift in plain language.
- Show a concise mapping, pattern, or checklist.
- Call out 1-3 practical watchouts.
- Add official links only when useful.

## Guardrails

- Do not treat Kubernetes as a one-file local orchestrator.
- Model readiness and liveness explicitly instead of relying on container startup order.
- Separate non-secret configuration from secrets.
- Treat persistence and networking as cluster-level concerns, not local Docker defaults.

## Source preference

1. Official docs
2. Official organization repos
3. Local reference files in this repository
