---
name: docker-compose-kubernetes-atlas
description: A starter atlas for teams translating Docker Compose setups into Kubernetes. It covers service mapping, configuration, secrets, persistence, probes, networking, and rollout thinking. Use when an agent needs a concise reference, migration guide, or side-by-side pattern library for this topic.
---

# Compose to Kubernetes Atlas

Use this skill to answer the practical question, "what is the target-platform way to do the thing I already know?"

## Quick Start

- Read `references/concepts.md` for conceptual mapping and mindset shifts.
- Read `references/patterns.md` for concrete rewrite or debugging patterns.
- Read `references/official-links.md` when official docs or source repos are needed.

## Workflow

1. Identify the source-side habit or failure mode.
2. Translate the mental model before changing code.
3. Prefer native target-platform patterns.
4. Show a small example or checklist instead of a giant transliteration.
5. Call out the main watchouts clearly.

## Output

- Start with the target-side equivalent in one sentence.
- Explain the mental shift in plain language.
- Show a concise mapping, snippet, or checklist.
- Mention 1-3 watchouts.
- Add official links only when useful.

## Guardrails

- Do not treat Kubernetes as a one-file local orchestrator.
- Model readiness and liveness explicitly instead of relying on container startup order.
- Separate non-secret configuration from secrets.
- Treat persistence and networking as cluster-level concerns, not local Docker defaults.
