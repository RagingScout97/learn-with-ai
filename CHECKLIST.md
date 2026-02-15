# Learning Checklist

Use this to track setup, phases, and document creation. Tick items as you complete them.

---

## Setup and workflow

- [ ] Kind cluster created (`learn-k8s`)
- [ ] Repo folders created (including `docs/md/`, `docs/docx/`)
- [ ] MD_TO_DOC_convertor tested (convert one `docs/md/*.md` to `docs/docx/*.docx`)

---

## Per phase (tick as you finish)

- [ ] Phase 1: Core fundamentals complete; 3 questions answered; 1 practical task done
- [ ] Phase 2: Networking and config complete; 3 questions answered; 1 practical task done
- [ ] Phase 3: Observability complete; 3 questions answered; 1 practical task done
- [ ] Phase 4: CKAD practice complete; full scenario done

---

## Document creation (learning skill)

- [ ] First note written in `docs/md/`
- [ ] First export to Word using convert.py (output in `docs/docx/`)
- [ ] Phase 1 summary exported to DOCX
- [ ] (Optional) Phase 2–4 summaries exported to DOCX

---

**When you ask to "create a document" or "export to Word,"** use content from `docs/md/` and run:

```powershell
python "e:\Projects\Learn with AI\MD_TO_DOC_convertor\convert.py" --file "docs/md/<name>.md" --output "docs/docx/<name>.docx"
```

Save results to `docs/docx/`.
