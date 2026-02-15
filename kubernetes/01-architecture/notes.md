# Kubernetes Architecture – Notes

**Phase 1 · Topic 1**

---

## Control plane vs workers

- **Control plane:** Decides *what* runs and *where*. It does not run your app containers. It watches the cluster and keeps actual state in line with the state you declare (e.g. “3 replicas”).
- **Workers (nodes):** Run your containers. The kubelet on each node talks to the control plane and runs the Pods assigned to that node.

**In one line:** Control plane = brain; workers = hands that run the workloads.

---

## Control plane components

| Component | Role |
|-----------|------|
| **API Server** | Single entry point for all REST API calls (from kubectl, controllers, kubelet). Validates and stores state in etcd. |
| **etcd** | Distributed key-value store. Holds all cluster state (Pods, Services, ConfigMaps, etc.). Only the API Server talks to it. |
| **Scheduler** | Watches for Pods with no node assigned; picks a node based on resources, constraints, affinity, etc. |
| **Controller Manager** | Runs controllers that reconcile state (e.g. Deployment controller keeps desired replicas; Node controller watches node health). |

---

## Node (worker) components

| Component | Role |
|-----------|------|
| **kubelet** | Agent on each node. Registers the node with the API Server; runs Pods (via container runtime); reports status. |
| **Container runtime** | Runs containers (e.g. containerd, CRI-O). Kind uses containerd inside Docker. |
| **kube-proxy** | Network proxy on each node. Implements Services (ClusterIP, NodePort, etc.) so Pods can reach each other and be reached. |

---

## Desired state

You declare state (e.g. “I want 3 replicas of this app”). Kubernetes **reconciles**: it constantly compares actual state with desired state and fixes drift (restarts failed Pods, schedules new ones, etc.). You don’t “start” Pods manually; you declare what you want and let the control plane and kubelet do the work.

---

## Kind cluster

With **Kind** (Kubernetes in Docker), the control plane and worker nodes all run as containers on your machine. One node often acts as both control plane and worker.

- `kubectl get nodes` — see your nodes.
- `kubectl get pods -A` — see all Pods (including system ones like `kube-apiserver`, `etcd` in `kube-system`).

**Optional:** Draw a simple diagram of your Kind cluster (one box = control plane components, one or more boxes = nodes with kubelet, runtime, kube-proxy) and save it in this folder or in `docs/md/`.

---

## Conceptual questions (answer in your own words)

1. What is the main job of the control plane vs the workers?
2. Why does only the API Server talk to etcd?
3. If a Pod dies, which components are involved in replacing it?

---

*Next topic: Pods (lifecycle, init containers, readiness vs liveness probes).*
