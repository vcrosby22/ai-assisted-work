# Finding `BACKLOG.md` and workspace paths

**Canonical backlog file:** **`BACKLOG.md`** at the **workspace (repository) root** — same level as `PROJECT_CONTEXT.md` and `activeContext.md`.

**Full path (this machine):**  
`/Users/victoriacrosby/Desktop/Cursor/BACKLOG.md`  
Shorthand: **`~/Desktop/Cursor/BACKLOG.md`** (`~` = `/Users/victoriacrosby`).

---

## In Cursor

1. **Quick Open:** `Cmd+P` (Mac) or `Ctrl+P` (Windows/Linux), type **`BACKLOG`**, choose **`BACKLOG.md`**.
2. **Explorer:** Left sidebar → open your **`Cursor`** workspace folder → **`BACKLOG.md`** is at the **top level**.

### Copy path or reveal in Finder

- Open **`BACKLOG.md`**, then **right‑click the editor tab** → **Reveal in Finder** or **Copy Path** (wording varies by Cursor/VS Code version).

---

## In Terminal

```bash
cd ~/Desktop/Cursor
ls BACKLOG.md
open BACKLOG.md    # optional: opens in default app
```

---

## Related

- **Backlog rules:** `.cursor/rules/backlog-prioritization.mdc`, `.cursor/rules/backlog-notify.mdc`
- **Quick add rows:** type **`a2b`** + Tab in `BACKLOG.md` (see [`../snippets/backlog-shortcut.md`](../snippets/backlog-shortcut.md))
- **Philosophy:** [`../../cursor-knowledge/backlog-philosophy.md`](../../cursor-knowledge/backlog-philosophy.md)
