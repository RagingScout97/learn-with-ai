# Learn with AI

Structured, AI-guided learning: track progress, build real projects, and push everything to GitHub. Each subject lives in its own folder so you can add more over time.

## Learning tracks

| Folder | Subject |
|--------|--------|
| [kubernetes/](kubernetes/) | Kubernetes fundamentals & CKAD |

Add more later (e.g. `python/`, `devops/`) as top-level folders with their own README and structure.

## Git workflow

- **master:** Holds the full, up-to-date state. All merged work lives here; keep it stable.
- **Branches:** Use separate branches for tasks and learning projects (e.g. `task/hello-k8s`, `learn/phase1-pods`). Do work on the branch; merge to master when done.

So: master = source of truth; tasks and learning = branch → merge → push.

**Learning:** When working on a track (e.g. Kubernetes), follow that track’s roadmap: [kubernetes/ROADMAP.md](kubernetes/ROADMAP.md) (phases, topic order, 3 questions + 1 task per topic).

## Document export (MD → Word)

To turn Markdown notes into Word (e.g. from any track’s `docs/md/`):

- **Tool:** [md2docx](https://github.com/RagingScout97/md2docx) (GitHub)
- **Command** (from this repo root):

```powershell
python "e:\Projects\Learn with AI\MD_TO_DOC_convertor\convert.py" --file "kubernetes/docs/md/your-note.md" --output "kubernetes/docs/docx/your-note.docx"
```

Adjust paths for other tracks when you add them (e.g. `python/docs/md/`).
