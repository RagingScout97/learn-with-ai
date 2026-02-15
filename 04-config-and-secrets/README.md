# 04 – ConfigMaps and Secrets

**Phase 2 · Networking & Configuration**

## What you’re learning

- **ConfigMaps:** Non-sensitive configuration (env vars or files mounted as volumes).
- **Secrets:** Sensitive data (base64 in the API; use env or volume). Never commit raw secrets.
- **Usage patterns:** envFrom, individual env vars, or volume mounts.

## Outcomes

- An app that reads config from a ConfigMap (e.g. env or file).
- Same app (or another) using a Secret (e.g. API key) via env or volume.
- Document: when to use ConfigMap vs Secret; security basics (don’t commit secrets).

## How to run

Add ConfigMap, Secret, and Deployment YAML here. Apply from repo root:

```powershell
kubectl apply -f 04-config-and-secrets/
```

Verify the app sees the config (e.g. `kubectl exec` and print env or read mounted file).
