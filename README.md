# Learn with AI

Structured, AI-guided learning: track progress, build real projects, and push everything to GitHub. Each subject lives in its own folder so you can add more over time.

## Learning tracks

| Folder | Subject |
|--------|--------|
| [kubernetes/](kubernetes/) | Kubernetes fundamentals & CKAD |

Add more later (e.g. `python/`, `devops/`) as top-level folders with their own README and structure.

## Document export (MD → Word)

To turn Markdown notes into Word (e.g. from any track’s `docs/md/`):

- **Tool:** [md2docx](https://github.com/RagingScout97/md2docx) (GitHub)
- **Command** (from this repo root):

```powershell
python "e:\Projects\Learn with AI\MD_TO_DOC_convertor\convert.py" --file "kubernetes/docs/md/your-note.md" --output "kubernetes/docs/docx/your-note.docx"
```

Adjust paths for other tracks when you add them (e.g. `python/docs/md/`).
