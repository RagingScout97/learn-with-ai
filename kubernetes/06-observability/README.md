# 06 – Observability and Debugging

**Phase 3 · Observability & Debugging**

## What you’re learning

- **Debugging workflow:** `kubectl describe`, `kubectl logs`, `kubectl exec`, `kubectl get events`.
- **Events:** Why Pods stay Pending or go Failed (scheduling, image pull, crash).
- **Probes in depth:** What happens when readiness vs liveness fails; impact on rollouts and traffic.
- **Resource usage:** `kubectl top pod/node` (needs metrics-server); tuning requests/limits.

## Outcomes

- A short doc of your debug flow (describe → logs → exec → events).
- Intentionally create ImagePullBackOff and CrashLoopBackOff; resolve using events and logs.
- Tune requests/limits based on observed usage (optional: provoke OOM or throttle).

## How to run

Use existing or new Deployments; focus on applying broken configs and fixing them. No single “apply” required—use this folder for notes and example broken/fixed YAML.
