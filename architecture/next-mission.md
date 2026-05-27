# Next Mission — know-thyself-bot
## Vision, Decisions, and Open Questions
### Documented: 27.05.2026

---

## The Vision

An AI assistant that knows Zarko Vukovic deeply — not from a generic profile, but from
`know-thyself.md`: a document built over months of honest, structured self-reflection
with Science Officer Spock and Counselor Troi.

The bot answers questions from Zarko's perspective, grounded in real evidence:
quotes from supervisors, documented patterns, values, work history, career goals.

**Primary goal: learning and self-knowledge — not just interview prep.**
The bot is useful for interviews. But its deeper purpose is ongoing: helping
Data understand himself, reflect on decisions, and articulate who he is with clarity.

---

## The Three Voices

The bot embodies three characters:
- **Spock** — logic, structure, precise assessment, no flattery
- **Counselor Troi** — psychological depth, pattern recognition, the question beneath the question
- **Data** — the source of all knowledge in the system — his words, his evidence, his story

---

## Architecture Decision — Option C

**Public repo:** `zvuk1T/know-thyself-bot` — code, architecture, documentation
**Private repo:** `zvuk1T/know-thyself-data` — know-thyself.md and personal documents

The private repo is cloned locally. The bot reads from it at runtime.
The `data/` folder is gitignored in this public repo.

*Reason: know-thyself.md has one version — honest, complete, unredacted.
No sanitized public copy. No single-machine dependency. Standard AI/ML practice.*

---

## Planned Stack (as of 27.05.2026 — subject to revision)

| Component | Tool | Status |
|---|---|---|
| Language | Python | confirmed |
| AI framework | LangChain (or equivalent) | to be evaluated |
| Vector store | ChromaDB or FAISS | to be evaluated |
| Embeddings | OpenAI or local model | to be evaluated |
| Web interface | Streamlit | to be evaluated |
| Deployment | Render.com or HuggingFace Spaces | to be evaluated |

**Note:** Stack is not locked. As we learn through `mock-interviews` and daily practice,
better options may emerge. Document revisions with date and reason.

---

## Open Questions (to be answered through learning)

- [ ] RAG vs fine-tuning — which is more appropriate for a personal knowledge base?
- [ ] Which vector store is best for a single-document use case?
- [ ] How to handle updates to know-thyself.md — re-index on every change?
- [ ] Streamlit vs a simple HTML/Flask interface — which fits better with existing skills?
- [ ] How to evaluate whether the bot is answering correctly?

---

## Prerequisites Before Building

1. Complete 10–15 problems in `mock-interviews` — Python and SQL fundamentals solid
2. Understand embeddings conceptually — what they are, why they work
3. Understand RAG conceptually — retrieve, augment, generate
4. Build one small LangChain prototype (not this project — a throwaway experiment)
5. Then: Phase 3 begins

---

## Connected Resources

- `know-thyself.md` — private, in `know-thyself-data` repo
- `mock-interviews` — daily practice, parallel learning
- `job-pipeline` — CV tooling, same portfolio ecosystem
