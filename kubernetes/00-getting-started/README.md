# 00 – Getting started (Phase 0)

**Phase 0 · Before you run anything**

Use this folder for notes and outcomes from Phase 0 in [ROADMAP.md](../ROADMAP.md).

## Steps

| Step | Where to put it |
|------|------------------|
| **What is Kubernetes?** | Short note in your words here (e.g. `what-is-kubernetes.md`) or in `docs/md/`. |
| **Containers (minimal)** | Optional: just run `docker run nginx:alpine`; no file needed unless you want a note. |
| **Installation** | Note your install steps or versions here if you like (e.g. `installation.md`); checklist is in [CHECKLIST.md](../CHECKLIST.md). |
| **Project setup** | Once cluster is up and first workload is applied, you’re done; optional note here. |

## Practical task

Create the Kind cluster, apply one workload (e.g. from `02-hello-k8s/` or a minimal Pod), and run `kubectl get pods`.

## Questions to answer (Phase 0)

- What problem does Kubernetes solve that plain Docker doesn’t?
- In one sentence, what is "desired state"?
- What are the three things you installed (Docker, kubectl, Kind) and what is each for?
