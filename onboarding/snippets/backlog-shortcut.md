# Backlog shortcut: **A-2-B** (`a2b`)

**Mnemonic:** **A**dd → **2** (tab through fields) → **B**acklog.

## Fastest: snippet trigger (no keybinding needed)

1. Open [`BACKLOG.md`](../../BACKLOG.md) at the **Active items** table (last data row).
2. Start a **new line** inside the table.
3. Type **`a2b`** and press **Tab** (or choose “BACKLOG.md row (A-2-B)” from the snippet picker).
4. Fill placeholders: **BL id**, **Priority**, **Purpose** (`PU-01`–`PU-05` — must match Epic in [`backlog/EPIC_REGISTRY.md`](../../backlog/EPIC_REGISTRY.md)), **Epic**, **Title**, **Notes** (Status defaults to `open`).

Defined in **`.vscode/backlog.code-snippets`** (workspace). Prefixes: `a2b`, `A2B`, `blrow`.

## Optional: keyboard chord **⌘K ⌥2 B** (macOS)

Cursor/VS Code do not load keybindings from the repo automatically. Add this to **your user** keybindings:

1. **Cursor** → **Settings** → search **Open Keyboard Shortcuts (JSON)**.
2. Paste inside the outer `[ ... ]` array:

```json
{
  "key": "cmd+k alt+2 b",
  "command": "editor.action.insertSnippet",
  "when": "editorTextFocus && editorLangId == markdown && resourceFilename == BACKLOG.md",
  "args": {
    "name": "BACKLOG.md row (A-2-B)"
  }
}
```

- **Mnemonic:** **A** = **⌥** (Option/Alt), **2** = **2**, **B** = **b** after the **⌘K** leader — close to **A-2-B** in spirit.
- If the chord conflicts on your machine, change `"key"` (e.g. `"cmd+alt+b"`) or drop the `cmd+k` leader.

### Windows / Linux

Use **`ctrl+k alt+2 b`** (or **`ctrl+alt+b`**) and the same `args`:

```json
{
  "key": "ctrl+k alt+2 b",
  "command": "editor.action.insertSnippet",
  "when": "editorTextFocus && editorLangId == markdown && resourceFilename == BACKLOG.md",
  "args": {
    "name": "BACKLOG.md row (A-2-B)"
  }
}
```

## After inserting

- Bump **BL-** id to the next free number (see table above).
- Keep **Priority / Epic / Status** aligned with `.cursor/rules/backlog-prioritization.mdc`.
