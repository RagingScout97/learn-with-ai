# 01 – Kubernetes Architecture

**Phase 1 · Core Fundamentals**

## What you’re learning

- **Control plane vs workers:** The control plane decides *what* runs and *where*; worker nodes run your containers.
- **Key components:** API Server, etcd, Scheduler, Controller Manager (control plane); kubelet, container runtime, kube-proxy (per node).
- **Desired state:** You declare state (e.g. “3 replicas”); Kubernetes reconciles actual state to match.

## Outcomes

- Notes or a short summary in your own words: “Control plane does X; workers do Y.”
- Optional: a diagram of your Kind cluster (control plane + nodes).

## How to run

This folder is for **notes and diagrams**, not runnable manifests. Use `docs/md/` for exportable Markdown if you want to convert to Word later.

## Kind reminder

Kind runs the control plane and nodes as containers on your machine. Use `kubectl get nodes` and `kubectl get pods -A` to see the system components.
