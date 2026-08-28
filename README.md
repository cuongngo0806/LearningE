# English Thinking Trainer

An adaptive English learning app (Vietnamese → English, CEFR A2 → TOEIC 800+).
Your learning progress syncs between machines through this repository.

Philosophy: **Think → Produce → Feedback → Correct → Reproduce → Reuse → Internalize.**

---

## Use it on another machine

**Requirements:** [Node.js](https://nodejs.org) 20 or newer, and git.

```bash
git clone <this-repo-url>
cd <repo>/app
cp .env.example .env      # Windows: copy .env.example .env
```

Edit `.env`:

- `SYNC_REPO_DIR` → the full path of this cloned repo on **this** machine
- `AI_BASE_URL` → your Claude-compatible endpoint (leave blank to run offline)

Then start it:

- **Windows:** double-click `app/start.bat`
- **macOS / Linux:** `./app/start.sh`

Open **http://localhost:8787**.

## Studying across machines

Your progress lives in `english-learning-data.json` in this repo.

1. **Before studying** — open Settings → *Sync across machines* → **Pull from git**
   (the app also offers this automatically when git has newer data).
2. **After studying** — **Push to git**
   (the app warns you if you close the tab with unpushed progress).

Pull replaces this machine's data with the copy from git, and always keeps an
automatic local backup first. Push is refused if the remote is newer — pull, then push.

Git authentication is your own (SSH key or credential helper); the app never
handles passwords or tokens, never force-pushes, and never resets the repo.

## What's in here

| Path | What it is |
|---|---|
| `app/server.cjs` | The whole app — server + UI in one 1.9 MB bundle |
| `app/start.bat`, `app/start.sh` | Launchers |
| `app/.env.example` | Config template |
| `english-learning-data.json` | Your synced learning progress |

The full source code is not part of this repository — this is the runnable app
plus your data.
