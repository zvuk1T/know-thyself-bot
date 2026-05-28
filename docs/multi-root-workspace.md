# 🗂️ MULTI-ROOT WORKSPACE IN VS CODE
## One Window, Multiple Repos — Best Practice for Code/Data Separation
### Lieutenant Commander Data & Science Officer Spock
### Created: 27.05.2026

---

## 🧠 Why This Exists

When following Option C architecture (code in public repo, data in private repo),
you have two separate folders on your laptop that need to work together.

The problem: VS Code normally opens one folder at a time.
If you open `know-thyself-bot/`, you cannot see `know-thyself-data/`.
Copilot cannot read `know-thyself.md`. You cannot reference it in chat.

The solution: **Multi-root Workspace** — VS Code opens multiple folders simultaneously
in one window, as if they were one project.

---

## 🧠 Mental Model

```
Normal VS Code:
Window  →  one folder  →  one repo 📁

Multi-root Workspace:
Window  →  multiple folders  →  multiple repos, one view 📁📁📁
```

Think of it like a desk with multiple project folders open at the same time —
you can read from any of them without switching rooms.

---

## 🪜 HOW TO SET IT UP

### Option A — Manual (every session)

1. Open your primary project folder normally:
   `File → Open Folder → know-thyself-bot/`

2. Add the data folder:
   `File → Add Folder to Workspace → know-thyself-data/`

3. Both folders now appear in the Explorer panel.
   Copilot can read files from both.

**Downside:** You have to repeat this every time you open VS Code.

---

### Option B — Save as .code-workspace file (recommended)

This saves the multi-root configuration permanently.

1. Set up the workspace manually (Option A above)

2. Save it:
   `File → Save Workspace As...`
   → save as `data-spock.code-workspace` in `/Users/zeal.v/Desktop/vs_code/`

3. Next time: just double-click `data-spock.code-workspace` to open everything at once.

**The `.code-workspace` file looks like this:**
```json
{
  "folders": [
    { "path": "know-thyself-bot" },
    { "path": "know-thyself-data" },
    { "path": "job-pipeline" },
    { "path": "mock-interviews" }
  ]
}
```

You can add all four projects — then one double-click opens your entire ecosystem.

---

## ⚠️ IMPORTANT — Git still works per folder

Multi-root workspace does NOT merge your git repos.
Each folder keeps its own independent git history.
`git status`, `git commit`, `git push` — all still run per folder.

```
know-thyself-bot/   →  git repo #1 (public)
know-thyself-data/  →  git repo #2 (private)
job-pipeline/       →  git repo #3 (public)
mock-interviews/    →  git repo #4 (public)
```

In the VS Code Source Control panel, you will see all four repos listed separately.

---

## 🔐 Privacy is unchanged

Adding `know-thyself-data/` to a workspace does NOT make it public.
The folder is still a private GitHub repo.
The `.code-workspace` file contains only folder paths — no file content.

**Rule: never commit the `.code-workspace` file to any repo.**
Add it to `.gitignore` everywhere, or keep it outside all repo folders.

Recommended location:
```
/Users/zeal.v/Desktop/vs_code/data-spock.code-workspace
```
This file lives in `vs_code/` but outside any individual repo — so it is never accidentally committed.

---

## 🔧 TROUBLESHOOTING

**Problem: Copilot still cannot see know-thyself.md**
Check that the folder was added correctly — look in Explorer panel on the left.
Both folder names should appear as top-level items.

**Problem: git commands run in wrong folder**
In the integrated terminal, check the working directory with `pwd`.
Use `cd` to navigate to the correct repo before running git commands.

**Problem: .code-workspace file accidentally staged**
Run: `git rm --cached data-spock.code-workspace`
Then add it to `.gitignore`.

---

## ✅ Notes for Students

**What is the most important thing to understand here?**

Multi-root Workspace is a VS Code display feature — it changes what you *see*,
not what git *tracks*. Your repos remain completely independent.
Opening two folders in one window does not merge them, link them, or expose private data.
It just lets you read and edit files from both in one place.

**What is the most common mistake?**

Saving the `.code-workspace` file inside one of your repos and accidentally committing it.
It contains local file paths — not sensitive, but messy and irrelevant to collaborators.
Keep it in the parent folder (`vs_code/`) where it belongs to no repo.

**What should you remember next time?**

One double-click on `data-spock.code-workspace` opens your entire working environment.
Set it up once, use it every day. This is how professionals work with multiple related repos.
