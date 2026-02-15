# 02 – Hello Kubernetes (Deployment + Service)

**Phase 1 · Core Fundamentals**

## What you’re building

A minimal “Hello Kubernetes” app:

- **Deployment:** Run N replicas of a container image (e.g. `nginx:alpine`). Kubernetes creates Pods and replaces them if they die.
- **Service:** Stable name and IP (e.g. ClusterIP or NodePort) so you can reach the app from inside the cluster or from your host.

## Your turn first

1. **Create a Kind cluster** (if not already): `kind create cluster --name learn-k8s`
2. **Write by hand** (in this folder):
   - A **Deployment** that runs 2 replicas of `nginx:alpine` (or another image you prefer).
   - A **Service** (ClusterIP or NodePort) that targets that deployment’s Pods (use labels/selectors).
3. **Apply and verify:**  
   `kubectl apply -f .`  
   Then: `kubectl get pods`, `kubectl get svc`, and either `kubectl port-forward` or curl to the NodePort.
4. **Break something on purpose:** Use a wrong image name or set replicas to 0; observe behavior; fix it.

Add your `deployment.yaml` and `service.yaml` here. Only after you attempt should you ask for reference YAML.

## How to run (after you add manifests)

From repo root:

```powershell
kubectl apply -f 02-hello-k8s/
```

## Optional

Add a short note in `docs/` (or in `docs/md/`) explaining what a Deployment and a Service do in your own words.
