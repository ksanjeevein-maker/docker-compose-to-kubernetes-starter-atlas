# Docker Compose to Kubernetes Starter Atlas Review Checklist

Use this checklist during code review, design review, or migration planning.

- Did each Compose concern get mapped to the right Kubernetes object?
- Are secrets and non-secret config separated sensibly?
- Do readiness and liveness probes represent useful health signals?
- Is persistence modeled for a cluster rather than a local machine?
- Would the deployment behave sensibly under scaling or restart conditions?
