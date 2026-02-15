# 07 – CKAD Practice (Jobs, CronJobs, Security)

**Phase 4 · Advanced CKAD Practice**

## What you’re learning

- **CKAD-style tasks:** Time-boxed; use imperative commands where faster (e.g. `kubectl run`, `kubectl create`, `kubectl scale`).
- **Jobs:** One-off run to completion; backoffLimit, restartPolicy.
- **CronJobs:** Scheduled runs; useful for batch or cleanup (e.g. every minute for learning).
- **Security context:** runAsNonRoot; readOnlyRootFilesystem (basics for CKAD).

## Outcomes

- 2–3 past-CKAD-style tasks: create Deployment, scale, expose, update (imperative where it helps).
- A Job that runs once; a CronJob that runs every minute (for practice).
- A Pod with runAsNonRoot and readOnlyRootFilesystem.
- Final scenario: from scratch—namespace, Deployment, Service, ConfigMap; scale; rollback; debug one failure.

## How to run

Add Job, CronJob, and security-context Pod YAML here. Apply and observe:

```powershell
kubectl apply -f 07-ckad-practice/
kubectl get jobs
kubectl get cronjobs
```

Use this folder for timed practice and consolidation notes.
