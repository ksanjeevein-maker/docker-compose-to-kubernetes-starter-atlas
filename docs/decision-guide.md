# Docker Compose to Kubernetes Starter Atlas Decision Guide

Use this when you need to choose the next move instead of reading every reference front to back.

## When to use this guide

- Use it when the user is blocked by one of these traps: Treating Kubernetes as Compose with more YAML., Using startup ordering as a substitute for readiness and retry-safe apps..
- Use it when you need to decide the order of migration work, not just the target syntax.
- Use it when you need a short review path before shipping or approving code.

## Recommended sequence

### Step 1: Orient

- Focus: Start with the basic mapping from Compose service to Deployment plus Service.
- Exit check: Did each Compose concern get mapped to the right Kubernetes object?

### Step 2: Translate

- Focus: Then learn ConfigMaps, Secrets, and why `.env` is not the whole story anymore.
- Exit check: Are secrets and non-secret config separated sensibly?

### Step 3: Implement

- Focus: Move into persistence, probes, and service discovery.
- Exit check: Do readiness and liveness probes represent useful health signals?

### Step 4: Harden

- Focus: Finish with rollout and scaling behavior so teams stop treating pods like fixed machines.
- Exit check: Is persistence modeled for a cluster rather than a local machine?

## If the user is stuck, choose this next move

- If they are porting line by line, redirect to the mental model in `docs/mental-model-map.md` and call out: Assuming host-path volume behavior in a cluster where pods can move.
- If they need proof, show `examples/worked-example.md` and explain what changed structurally.
- If they are ready to merge or publish, run the checklist in `docs/review-checklist.md`.

## Escalate when

- The implementation still violates this review check: Would the deployment behave sensibly under scaling or restart conditions?
- The chosen approach depends on preserving a source-side habit that keeps causing trouble: Treating Kubernetes as Compose with more YAML.
