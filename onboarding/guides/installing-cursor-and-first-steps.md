# Installing Cursor and first steps

## At a glance

=== "Beginner"

    This guide walks you through downloading Cursor, opening a folder, and having your first AI conversation. It takes about **10 minutes** and assumes you've never used a code editor before.

=== "Intermediate"

    Install Cursor (VS Code-based editor with built-in AI chat), open a project folder so the assistant can read/edit files, and understand the two modes: **Plan** (think together, review changes) vs. **Agent** (assistant edits files and runs commands directly).

=== "Advanced"

    Cursor is an Electron-based fork of VS Code with integrated LLM chat (Claude, GPT-4, etc.), agentic file editing, and context-aware indexing. Key setup: open a workspace folder (enables `.cursorignore`, rules, and codebase indexing), configure model preferences, and understand Plan vs. Agent mode for different iteration speeds.

---

This guide walks you from zero to your first AI-assisted conversation. It takes about 10 minutes.

---

## 1. Download and install

1. Go to [**cursor.com**](https://www.cursor.com/) and click **Download**.
2. Open the downloaded file:
   - **Mac:** Drag Cursor to your Applications folder, then open it.
   - **Windows:** Run the installer and follow the prompts.
   - **Linux:** Follow the instructions on the download page.
3. On first launch, Cursor may ask if you want to **import settings from VS Code**. If you've never used VS Code, skip this — it doesn't matter.
4. **Sign in** (or create a free account) when prompted. The free tier gives you limited AI usage to start.

> **Tip:** Cursor is built on VS Code, the most popular code editor in the world. If a guide or video mentions "VS Code," most of it applies to Cursor too.

---

## 2. Open a folder

Cursor works best when it can see a **folder** (also called a "project" or "workspace"). Even one file inside a folder is enough.

1. **Create a folder** anywhere on your computer — your Desktop is fine. Name it something simple, like `my-first-project`.
2. Inside that folder, create a text file called `notes.md` (or anything — it just helps to have *something* in the folder).
3. In Cursor, go to **File → Open Folder** and select your folder.

You should see your folder name in the left sidebar with your file listed underneath.

> **Why a folder?** When you open a folder, the AI assistant can read and edit the files inside it. Without a folder, the assistant can only chat — it can't help you build anything persistent.

---

## 3. Open the chat

Look for the **chat panel** on the right side of the screen (or use the keyboard shortcut **Cmd+L** on Mac / **Ctrl+L** on Windows).

You'll see a text box where you can type. This is where you talk to the AI assistant.

---

## 4. Have your first conversation

Type something like:

> "I have a folder with one notes file. Help me write a short project outline for [describe any idea you have]. Put it in a new file called outline.md."

The assistant will:
- Read your folder to understand what's there
- Draft an outline based on your description
- Offer to create the file (or create it directly, depending on the mode)

**That's it — you just used Cursor.**

---

## 5. Understand the two modes

Cursor has two main modes for working with the AI. You'll see these options near the chat input:

| Mode | What happens | When to use it |
|------|-------------|----------------|
| **Plan** | The assistant **thinks with you** — it suggests changes but doesn't edit files until you approve | When you want to review before anything changes |
| **Agent** | The assistant **acts** — it can edit files, create new ones, and run commands | When you trust the direction and want to move fast |

**Start with Plan** if you're cautious. Switch to **Agent** when you're comfortable. You can always **undo** (Cmd+Z / Ctrl+Z) if something goes wrong.

---

## 6. Try three things

Before you read anything else, try these on your own (use your own words — these are just patterns):

| Goal | Example prompt |
|------|---------------|
| **Ask for feedback** | "What are the biggest gaps in this outline? Be honest." |
| **Restructure something** | "Turn these messy bullet points into a clean one-page summary with headers." |
| **Create a file** | "Draft a simple landing page for [your idea] as an HTML file I can open in my browser." |

Notice how you describe **what you want**, not **how to code it**. That's the whole idea.

---

## What's next

- [**Building with agentic AI (non-technical)**](building-with-agentic-ai-non-technical.md) — the mindset for working with AI: you steer, the assistant builds
- [**Working with AI context**](working-with-ai-context.md) — when to start a new chat, how to keep the assistant accurate
- [**First-week checklist**](../checklists/first-week-cursor-non-technical.md) — a light daily plan for your first week
- [**Back to all guides**](../INDEX.md)

---

## Troubleshooting

**"I don't see the chat panel."** Try **View → Toggle Chat** or the keyboard shortcut Cmd+L (Mac) / Ctrl+L (Windows).

**"The assistant didn't create the file."** You might be in Plan mode. Switch to Agent mode, or say "go ahead and create it."

**"I ran out of free AI messages."** The free tier has a daily or monthly limit. You can wait for it to reset or upgrade at [cursor.com/pricing](https://www.cursor.com/pricing).

**"This looks like a code editor — is this for me?"** Yes. Cursor is a code editor by design, but you don't need to write code. Think of it as a workspace where you and the AI collaborate on files — text, plans, web pages, whatever you need.
