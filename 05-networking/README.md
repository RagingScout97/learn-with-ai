# 05 – Networking (Services, Ingress, NetworkPolicy)

**Phase 2 · Networking & Configuration**

## What you’re learning

- **Service types:** ClusterIP (internal), NodePort (host access), LoadBalancer (cloud); Headless for stateful discovery.
- **Ingress:** Host/path routing; need an Ingress controller (e.g. nginx) in the cluster.
- **NetworkPolicy:** Ingress/egress rules; default deny; allow by Pod labels (CKAD awareness).

## Outcomes

- Document when to use each Service type; Headless for “stateful” discovery.
- One Ingress with two paths pointing to two different Services.
- A simple NetworkPolicy: allow traffic only from Pods with a specific label.

## How to run

Add Service(s), Ingress, and optionally NetworkPolicy YAML. If using Ingress, ensure an Ingress controller is installed (e.g. for Kind). Then:

```powershell
kubectl apply -f 05-networking/
```

Test with curl (host/path or NodePort as needed).
