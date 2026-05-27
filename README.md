# know-thyself-bot

> "Know thyself first. Everything else comes after." — Socrates

**Status: 🚧 In Planning — architecture and foundation phase**

---

## What This Is

A personal AI assistant that knows Zarko Vukovic — not from a generic profile, but from a deep, honest, continuously evolving self-assessment document built over months of structured reflection.

This is not a chatbot that pretends to be someone. It is a tool for self-understanding — powered by real documents, real evidence, and real language. It helps prepare for interviews, evaluate career decisions, and reflect on personal and professional identity.

The bot draws on three influences:
- **Spock** — logic, structure, honest assessment
- **Counselor Troi** — psychological depth, pattern recognition, the question beneath the question
- **Data** — the student, the learner, the one asking

---

## Why This Exists

Most AI assistants know nothing about the person using them. This one is built to know one person deeply — and to reflect that knowledge back with precision and honesty.

The primary goal is learning and self-knowledge. The secondary benefit is career preparation.

---

## Architecture (Planned)

```
know-thyself-bot/          ← public repo — code, architecture, documentation
know-thyself-data/         ← private repo — know-thyself.md and personal documents
```

The private data repo is cloned locally and referenced at runtime. It never appears in this public repo.

This follows Option C — Code/Data Separation via Private GitHub Repo.
See `docs/data-privacy-architecture.md` for full explanation.

**Planned stack (subject to change as we learn):**
- Python
- LangChain or equivalent
- Vector store: ChromaDB or FAISS
- Web interface: Streamlit (for now)
- Deployment: Render.com or HuggingFace Spaces

---

## Project Phases

**Phase 1 — Foundation (current)**
- Repo structure, architecture decisions, documentation
- No code yet — understanding comes before building

**Phase 2 — Learning (parallel with mock-interviews)**
- Study RAG, embeddings, vector stores, prompt engineering
- Each concept documented in `captains-log/` as it is learned

**Phase 3 — Build**
- First working prototype: ask a question, get an answer grounded in know-thyself.md
- Evaluate, iterate, improve

---

## Connected Projects

- **job-pipeline** — CV generation tool (github.com/zvuk1T/job-pipeline)
- **mock-interviews** — daily SQL and Python interview practice (github.com/zvuk1T/mock-interviews)
- **know-thyself-data** — private repo, source of truth documents (private)

---

*All work completed alongside full-time employment — demonstrating consistent self-discipline and commitment to career transition.*
