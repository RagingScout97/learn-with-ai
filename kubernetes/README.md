# Kubernetes (CKAD track)

Structured learning for **Kubernetes fundamentals** and **CKAD preparation**. Learn by building on a local **Kind** cluster.

## Learning goals

- Master Kubernetes fundamentals (architecture, Pods, Deployments, Services, config, networking)
- Prepare for CKAD (declarative YAML, imperative commands, debugging)
- Think like a Kubernetes engineer: desired state, reconciliation, production patterns
- Relate everything to real scenarios (e.g. AKS at work)

## Prerequisites

- **Docker** (Kind runs clusters in containers)
- **kubectl** ([install](https://kubernetes.io/docs/tasks/tools/))
- **Kind** – Kubernetes in Docker ([install](https://kind.sigs.k8s.io/docs/user/quick-start/#installation))

If you have nothing installed yet, start with **Phase 0** in [ROADMAP.md](ROADMAP.md) (what is Kubernetes, installation, project setup).

## Kind setup

Create a cluster named `learn-k8s`:

```powershell
kind create cluster --name learn-k8s
```

Verify:

```powershell
kubectl cluster-info --context kind-learn-k8s
kubectl get nodes
```

## Repo structure (this track)

| Path | Purpose |
|------|--------|
| `ROADMAP.md` | 30-day phased roadmap; tick off as you go |
| `CHECKLIST.md` | Setup, phases, document-export checklist |
| `docs/md/` | Markdown notes and summaries (source for Word export) |
| `docs/docx/` | Generated Word documents ([md2docx](https://github.com/RagingScout97/md2docx) output) |
| `01-architecture/` | Architecture notes and diagrams |
| `02-hello-k8s/` | First project: Deployment + Service |
| `03-pods-and-probes/` | Pods, init containers, probes |
| `04-config-and-secrets/` | ConfigMaps, Secrets |
| `05-networking/` | Services, Ingress, NetworkPolicy |
| `06-observability/` | Debugging, events, metrics |
| `07-ckad-practice/` | Timed tasks, Jobs, CronJobs, security |
| `cheatsheets/` | kubectl, YAML snippets, CKAD tips |

## How to run projects

Each numbered folder has a `README.md` with what you’re learning and how to run. From **repo root**:

```powershell
kubectl apply -f kubernetes/02-hello-k8s/
```

Or from this folder (`kubernetes/`):

```powershell
kubectl apply -f 02-hello-k8s/
```

## Document export (MD → Word)

Notes live in `kubernetes/docs/md/`. Use [md2docx](https://github.com/RagingScout97/md2docx). From **repo root**:

```powershell
python "e:\Projects\Learn with AI\MD_TO_DOC_convertor\convert.py" --file "kubernetes/docs/md/your-note.md" --output "kubernetes/docs/docx/your-note.docx"
```

## Progress

Use `ROADMAP.md` and `CHECKLIST.md` in this folder to track phases; push to GitHub to keep history in one place.
