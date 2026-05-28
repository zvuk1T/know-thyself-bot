# Data Privacy Architecture

**Created:** 28.05.2026
**Project:** Know Thyself Bot
**Visibility:** Public — this file is safe for recruiters and collaborators to read

---

## The Core Principle

This project separates code from personal data at the repository level.

```
know-thyself-bot   → public engine   (this repo)
know-thyself-data  → private fuel    (separate private repo)
```

Recruiters and collaborators may inspect the engine.
They must not see the private fuel.

---

## Option C — Code/Data Separation

This project follows the **Option C** privacy architecture pattern:

| Layer | Repository | Visibility | Contains |
|---|---|---|---|
| Engine | `zvuk1T/know-thyself-bot` | **Public** | Code, architecture, documentation |
| Fuel | `zvuk1T/know-thyself-data` | **Private** | Personal documents, source-of-truth data |

The private repository is cloned locally and referenced at runtime.
It never appears in the public repository — not as a submodule, not as a folder, not in any commit.

---

## How It Works at Runtime

```
Local machine:
├── know-thyself-bot/     ← public repo — cloned from GitHub
│   ├── data/             ← gitignored — never pushed
│   └── src/
│
└── know-thyself-data/    ← private repo — cloned separately
    └── source-of-truth/
        └── know-thyself.md
```

At runtime, the bot reads from the local `know-thyself-data/` path.
The `data/` folder in this repo is gitignored — it is either symlinked or referenced via a local path configuration.

---

## What the Private Repo Contains

The private repo (`know-thyself-data`) holds:
- `source-of-truth/know-thyself.md` — the primary personal document used for RAG retrieval
- `evidence/` — certificates, recommendation letters, work history [future]
- `captains-log/` — private session notes and reflections

None of these files appear in this public repo.

---

## What This Repo Contains

The public repo (`know-thyself-bot`) holds:
- Application code — retrieval pipeline, prompt logic, chat interface
- Architecture documentation — this file and others in `docs/`
- Sanitized captain's logs — decisions and progress, no personal content
- No personal data, no private documents, no sensitive information

---

## The `.gitignore` Rule

The `data/` folder in this repo is gitignored:

```
data/
```

This is the single most important safety rule. Before every commit, verify `data/` is not staged.

---

## Why This Architecture

Three reasons:

1. **Privacy** — personal documents never leave the local machine via a public repo
2. **Professionalism** — public code is clean, reviewable, and contains no accidental data leaks
3. **Demonstrability** — the architecture itself shows engineering judgment: a candidate who understands public/private separation at the system design level

---

## Connected Repositories

```
zvuk1T/know-thyself-bot     ← THIS REPO — public engine
zvuk1T/know-thyself-data    ← private fuel — not publicly accessible
zvuk1T/job-pipeline         ← CV generation tool
zvuk1T/mock-interviews      ← daily SQL + Python practice
```
