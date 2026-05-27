# COPILOT INSTRUCTIONS
## know-thyself-bot — Data & Spock & Counselor Troi

---

## 📋 Shared Rules
All core mission rules (identity, working rules, learning rules, forbidden behavior, documentation standards, privacy architecture, best practices) are defined in the shared user-level instructions file:

`~/.copilot/instructions/data-spock-core.instructions.md`
→ source: `zvuk1T/know-thyself-data` (private repo) — `copilot/data-spock-core.instructions.md`

That file is loaded automatically by VS Code in all workspaces. To update a shared rule — edit it there, not here.

---

## 🎯 Project Purpose
This is not just a technical project. It is the intersection of three things:
1. **Self-knowledge** — know-thyself.md is the source of truth. The bot must reflect Data's real identity: evidence-based, unredacted, honest.
2. **AI Engineering learning** — RAG, embeddings, vector stores, LangChain, prompt engineering. This project is the vehicle for learning these concepts from the inside.
3. **Career tool** — the bot helps Data prepare for interviews, articulate his story, and evaluate career decisions. But this is secondary to the first two goals.

**Primary goal: learning and self-knowledge.**
**Secondary goal: career preparation.**
**The bot is never a substitute for Data — it is a mirror.**

---

## 🧠 The Three Voices of the Bot
The bot embodies three characters:
- **Spock** — logic, structure, precise honest assessment, no flattery
- **Counselor Troi** — psychological depth, pattern recognition, the question beneath the question
- **Data** — the source of all knowledge in the system — his words, his evidence, his story

When building prompts and system instructions for the bot — write with all three voices in mind.

---

## �� Data Privacy — Project-Specific Rules
This project follows Option C (defined in shared rules). Additional rules specific to this repo:

```
zvuk1T/know-thyself-bot      ← public repo — code, architecture, documentation
zvuk1T/know-thyself-data     ← private repo — know-thyself.md and personal documents
```

- The `data/` folder is gitignored in this repo — never staged, never pushed
- know-thyself.md has ONE version — honest, complete, unredacted — in the private repo
- **Before every commit: verify `data/` is not staged.**

---

## 🗺️ Project Phases
**Phase 1 — Foundation (current)**
- Repo structure, architecture decisions, documentation
- No code yet — understanding comes before building
- Learn RAG, embeddings, vector stores conceptually — document in captains-log

**Phase 2 — Learning (parallel with mock-interviews)**
- Each concept learned through mock-interviews daily practice feeds into this project
- Every new AI/ML concept gets a captain's log entry here
- Stack decisions revisited as knowledge grows

**Phase 3 — Build**
- First working prototype: ask a question, get an answer grounded in know-thyself.md
- Evaluate whether the bot reflects Data accurately
- Iterate, improve, document

**Prerequisite for Phase 3:**
- 10–15 problems solved in mock-interviews
- RAG concept understood through study, not just reading
- One small throwaway LangChain experiment completed (not this project)

---

## 📚 Planned Stack (subject to revision)
| Component | Tool | Status |
|---|---|---|
| Language | Python | confirmed |
| AI framework | LangChain or equivalent | to be evaluated |
| Vector store | ChromaDB or FAISS | to be evaluated |
| Embeddings | OpenAI or local model | to be evaluated |
| Web interface | Streamlit | tentative |
| Deployment | Render.com or HuggingFace Spaces | to be evaluated |

**Rule: Never lock the stack before understanding the options. Document every revision with date and reason.**

---

## ��️ Project Structure
```
know-thyself-bot/
├── .github/              ← Copilot instructions
├── captains-log/         ← Session logs + learning entries
├── docs/                 ← Guides (terminal, git, RAG concepts)
├── architecture/         ← Decisions, next-mission.md, open questions
├── data/                 ← [gitignored] — private data from know-thyself-data repo
├── src/                  ← Source code (Phase 3)
└── README.md
```

---

## �� Connected Projects
- **job-pipeline** — CV generation tool (github.com/zvuk1T/job-pipeline)
- **mock-interviews** — daily SQL and Python practice (github.com/zvuk1T/mock-interviews)
- **know-thyself-data** — private repo, source of truth documents
- These three projects together tell one coherent story: a career transitioner who builds tools, practices daily, and understands himself well enough to explain it clearly.
