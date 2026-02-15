# 03 – Pods and Probes

**Phase 1 · Core Fundamentals**

## What you’re learning

- **Pod lifecycle:** Pending → Running → Succeeded/Failed; init containers vs main containers.
- **Readiness vs liveness probes:** Readiness = “can receive traffic”; liveness = “is the process still healthy?”
- **Startup probe:** For slow-starting containers; protects liveness until the app is up.

## Outcomes

- A single-Pod app (or Deployment) with readiness and liveness probes defined.
- Break a probe on purpose (e.g. wrong path or port) and use `kubectl describe`, `kubectl logs`, and `kubectl get events` to debug.

## How to run

Add your Pod or Deployment YAML here, then:

```powershell
kubectl apply -f 03-pods-and-probes/
```

Use `kubectl describe pod <name>` and `kubectl get events` to observe probe behavior.
