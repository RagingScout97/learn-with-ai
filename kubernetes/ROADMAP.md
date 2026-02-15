# 30-Day Kubernetes Learning Roadmap

Tick off topics as you complete them. Each topic ends with **3 conceptual questions** and **1 practical task**.

---

## Phase 0: Getting started (Days 0–1)

For anyone with nothing installed yet: understand what Kubernetes is, install the tools, and run your first workload.

| Done | Focus | Topics | Mini project / outcome |
|------|--------|--------|------------------------|
| [ ] | **What is Kubernetes?** | Definition; containers vs VMs; orchestration; desired state | Short note in your words: "Kubernetes is …" in `01-architecture/` or `docs/md/` |
| [ ] | **Containers (minimal)** | Image, container, registry; why we need an orchestrator | Optional: run one container with Docker (`docker run nginx:alpine`) |
| [ ] | **Installation** | Docker, kubectl, Kind; verify with `kubectl get nodes` | All three installed; cluster `learn-k8s` created and reachable |
| [ ] | **Project setup** | Repo (this repo); create cluster; first `kubectl apply` | Cluster running; one manifest applied (e.g. from `02-hello-k8s/` or a minimal Pod) |

**Questions to answer (Phase 0):**

- What problem does Kubernetes solve that plain Docker doesn’t?
- In one sentence, what is "desired state"?
- What are the three things you installed (Docker, kubectl, Kind) and what is each for?

**Practical task (Phase 0):** Create the Kind cluster, apply one workload (e.g. a single Pod or the hello-k8s Deployment), and show it with `kubectl get pods`.

---

## Phase 1: Core Fundamentals (Days 1–10)

| Done | Focus | Topics | Mini project / outcome |
|------|--------|--------|------------------------|
| [ ] | **Architecture** | Control plane vs workers; API Server, etcd, Scheduler, kubelet | Notes in `01-architecture/`; diagram of your Kind cluster |
| [ ] | **Pods** | Lifecycle; init containers; readiness vs liveness probes | Single-Pod app with probes; break probe and debug |
| [ ] | **Deployments** | Replicas; rollout; rollback | `02-hello-k8s` with rollout and rollback |
| [ ] | **Services** | ClusterIP, NodePort, LoadBalancer (concept) | Same app; access via Service (port-forward + NodePort) |
| [ ] | **Labels & Selectors** | How Deployments find Pods; how Services find Pods | Add labels; break selector and fix |
| [ ] | **Namespaces** | Isolation; `kubectl -n`; default namespaces | Deploy same app in two namespaces |
| [ ] | **Imperative vs Declarative** | `kubectl run` vs YAML; when to use which (CKAD) | One resource via CLI, one via YAML |
| [ ] | **kubectl essentials** | get, describe, logs, exec, port-forward | Cheat sheet in repo; use in every project |

**Questions to answer (Phase 1):**

- What is the difference between a Pod and a Deployment?
- What does a ClusterIP Service do, and when would you use NodePort?
- Why do we use labels and selectors?

**Practical task (Phase 1):** Deploy app in a new namespace and expose it with NodePort; then scale and rollback.

---

## Phase 2: Networking & Configuration (Days 11–20)

| Done | Focus | Topics | Mini project / outcome |
|------|--------|--------|------------------------|
| [ ] | **ConfigMaps** | Non-sensitive config; env vs volume | App that reads config from ConfigMap |
| [ ] | **Secrets** | base64; env vs volume; security basics | Same app with a secret (e.g. API key); never commit raw secret |
| [ ] | **Multi-container Pods** | Sidecar; ambassador; when to use | Sidecar that tails logs or does a small network helper |
| [ ] | **Resource requests/limits** | requests vs limits; QoS classes | Set requests/limits; provoke OOM or CPU throttle and observe |
| [ ] | **Service types deep dive** | ClusterIP, NodePort, LoadBalancer; Headless | Document when to use each; Headless for “stateful” discovery |
| [ ] | **Network policies (concept)** | Ingress/egress; default deny (CKAD awareness) | Simple policy: allow only from specific Pod labels |
| [ ] | **Ingress (concept)** | Host/path routing; Ingress controller (e.g. nginx) | One Ingress with 2 paths to 2 different Services |

**Questions to answer (Phase 2):**

- When do you use a ConfigMap vs a Secret?
- What are QoS classes and how do requests/limits affect them?
- What is a Headless Service for?

**Practical task (Phase 2):** Add ConfigMap + Secret to your app; expose via Ingress with two paths.

---

## Phase 3: Observability & Debugging (Days 21–25)

| Done | Focus | Topics | Mini project / outcome |
|------|--------|--------|------------------------|
| [ ] | **Debugging workflow** | describe, logs, exec, events | Document your debug flow; fix a broken deployment from scratch |
| [ ] | **Events** | `kubectl get events`; why Pods are Pending/Failed | Intentionally create ImagePullBackOff, CrashLoopBackOff; resolve |
| [ ] | **Probes in depth** | startup vs readiness vs liveness; failure effects | App that fails readiness; observe traffic and rollout behavior |
| [ ] | **Resource usage** | top pod/node (metrics-server); requests/limits | Tune requests/limits based on observed usage |

**Questions to answer (Phase 3):**

- When do you use startup vs readiness vs liveness probes?
- What do `kubectl get events` and Pod status tell you when something is wrong?
- How do you debug a Pod that is Pending or CrashLoopBackOff?

**Practical task (Phase 3):** Break the app in 3 ways (image, probe, resource); find cause with events/logs/describe and fix.

---

## Phase 4: Advanced CKAD Practice (Days 26–30)

| Done | Focus | Topics | Mini project / outcome |
|------|--------|--------|------------------------|
| [ ] | **CKAD-style tasks** | Time-boxed; imperative where it’s faster | 2–3 past-CKAD-style tasks (create Deployment, scale, expose, update) |
| [ ] | **Jobs & CronJobs** | One-off vs scheduled; backoffLimit | Job that runs once; CronJob that runs every minute (for learning) |
| [ ] | **Security context** | runAsNonRoot; readOnlyRootFilesystem (basics) | Pod that runs as non-root and with read-only root |
| [ ] | **Review & consolidation** | All phases; weak spots | Fix a “broken” cluster YAML bundle; document learnings |

**Questions to answer (Phase 4):**

- When is an imperative `kubectl` command faster than writing YAML (e.g. in the exam)?
- What is the difference between a Job and a CronJob?
- Why set securityContext (runAsNonRoot, readOnlyRootFilesystem) on a Pod?

**Practical task (Phase 4):** Full CKAD-style scenario: from scratch: namespace, Deployment, Service, ConfigMap; scale; rollback; debug one failure.

---

## Optional / later

- **Helm:** Package manager for Kubernetes. You install apps from "charts" (templates + values). Used a lot in the wild; CKAD does not require it. Optional step after you’re comfortable with plain YAML and kubectl.
