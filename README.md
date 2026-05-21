# Cairn

**A project template for working on long-running projects with Claude Code.**

Cairn is the folder structure, instruction file, and session ritual that turn one-shot conversations with an AI into continuous, accumulating work. You start each session by reading a resume point, end each session by writing one, and the project's thinking compounds across weeks instead of resetting every time.

The name comes from the small stack of stones hikers add to as a trail marker — each session you place one more stone, and the next person (or the next you, two weeks later) can find the trail.

---

### Already familiar with Claude Code? TL;DR

Clone the repo. Rename the folder. Open Claude Code in it. Type anything. Claude reads `CLAUDE.md`, sees this is a fresh install, runs `SETUP.md` to walk you through 5 questions (~5 min), then writes your customized `CLAUDE.md`, creates your topic folders, and removes itself. After that: a `CLAUDE.md` per project, numbered topic folders each with a `Brainstorm.md` (append-only session log) and `Master.md` (distilled current state), a `Process_Meta_Notes.md` for workflow observations, and a hard rule that every session ends with the user typing "wrap it up" so Claude produces the next-session prompt before context is lost.

See [docs/workflow.md](docs/workflow.md) for the session ritual, [docs/optional-patterns.md](docs/optional-patterns.md) for advanced patterns.

---

## Who this is for

**Primary: non-technical people who have started using Claude Code (or Claude.ai with file uploads) and noticed that long projects fall apart between conversations.** You start a great session, you come back two days later, and Claude has no idea what you decided or what to work on next. You spend ten minutes re-explaining context. By session four, you have decisions scattered across five chat logs and no idea what the current state is.

Cairn fixes this with a deliberately simple set of habits:

- One file (`CLAUDE.md`) that Claude reads automatically at the start of every conversation.
- One pair of files per topic (`Brainstorm.md` for the running log, `Master.md` for the distilled current state).
- One ritual at the end of every session ("wrap it up") that produces the next session's starter prompt.

There is no software to install. There is no platform to sign up for. It's a folder structure and a set of conventions that the AI follows because you put them in `CLAUDE.md`.

**Secondary: technical people who want a repeatable scaffold for AI-assisted projects.** Same template, less hand-holding in the docs.

## What this is not

- **Not a Claude Code extension or tool.** It's just a folder layout and a `CLAUDE.md` file. The AI reads the file, and the file tells the AI how to behave.
- **Not opinionated about the work itself.** Cairn works for writing a novel, launching a podcast, planning a wedding, building software, running a job search, designing a board game, or anything else that requires sustained thinking over multiple sessions.
- **Not a productivity system.** No tags, no kanban, no priorities, no metrics. Just structured conversation logs.

## How it works

### The two-file pattern

Every topic in your project has two files:

- `Brainstorm.md` — **Append-only**. Every session you have on this topic gets a dated header and entry. You never delete from it. It is the historical record of how thinking evolved.
- `Master.md` — **Current state**. What you currently believe to be true about this topic, expressed as a standalone document. Updated when brainstorm sessions produce decisions that change the master-level thinking.

Why both? Because the running log preserves the **why** (how you arrived at each decision), and the master doc gives a clean **what** (the current answer) without forcing readers to scroll through five sessions of thinking. They serve different purposes.

### The session ritual

Every session has a defined start and end.

**At the start**, you point Claude at a "resume point" — usually a one-paragraph prompt written by Claude at the end of the previous session. Claude reads the relevant files, confirms what it found, and starts working.

**During the session**, Claude flags decisions and open questions explicitly, and stays focused on the topic at hand. If the conversation drifts, Claude flags the drift rather than going along with it.

**At the end**, you type "wrap it up." Claude produces five things:

1. An updated `Brainstorm.md` with the new session appended
2. An updated `Master.md` if anything meaningful changed
3. A plain-text session summary you can scan
4. A ready-to-paste prompt for the next session
5. (Optional) An entry in `Process_Meta_Notes.md` if something notable about the workflow itself happened

This ritual is what makes cairn work. Without it, sessions don't connect. With it, the project accumulates instead of evaporating.

### The numbered folders

Top-level folders are numbered (`01_Foundation/`, `02_Production_Setup/`, etc.) and named after the major topics or phases of your project. The numbering gives every folder a stable reference so you can say "in 03_Launch_Strategy" without ambiguity.

Most projects fit naturally into 4-7 top-level topics. Pick names that match your domain and number them in roughly the order you expect to work through them. The example project in this template (Sourdough Lab, a podcast) uses phase-based folders. Other patterns are described in [docs/optional-patterns.md](docs/optional-patterns.md).

## Getting started

### Quick start

1. **Clone or download this repo** (or click the green "Use this template" button at the top of the cairn GitHub page if you want a fresh copy under your own account).
2. **Rename the folder** from `cairn/` to your project name.
3. **Open Claude Code in that folder.** (Install instructions: [claude.com/claude-code](https://claude.com/claude-code).)
4. **Type anything to Claude** — `start`, `hi`, `let's go`, whatever. Claude will see this is a fresh install, read `SETUP.md`, and walk you through five questions to customize the project.
5. **Answer the questions.** About 5 minutes total. At the end Claude writes your customized `CLAUDE.md`, creates your topic folders, and offers to start your first session right away.

That's it. No manual file editing. No folder structure to memorize before you can start. The setup flow is the user-facing entry point; the structure underneath it is the cairn pattern.

### Your first session

If you say yes to starting immediately after setup, Claude moves directly into the first topic you chose and begins asking questions one at a time. When you're ready to stop, type **"wrap it up"** and Claude produces the deliverables that let your next session resume cleanly: an updated `Brainstorm.md`, an updated `Master.md`, a session summary, and a "next session prompt" you can paste at the start of next time.

If you'd rather come back later, Claude gives you the next-session prompt at the end of setup. Save it somewhere you can find it.

### After session one

Paste the next-session prompt at the start of your next conversation. Claude reads the files, confirms the context, and picks up where you left off. Repeat.

## The worked example

A populated example project (a hypothetical podcast called Sourdough Lab) lives in [`.cairn/example/`](.cairn/example/) — `Brainstorm.md` and `Master.md` showing what two sessions of real thinking look like in the cairn format. Read it once before your first session if you want to see the shape of filled-in files. It includes how decisions get numbered (F1, F2...), how open questions get flagged (F-OQ1, F-OQ2...), and how the resume point at the end of each session feeds into the next.

The example does not interfere with your project. It lives in the hidden `.cairn/` directory and only loads if you open it directly. Delete it anytime.

## Optional patterns

A few patterns work well for projects beyond the basics but are not part of the minimal template. See [docs/optional-patterns.md](docs/optional-patterns.md) for:

- **Decision and question numbering** (D1, D2... and OQ1, OQ2...) for projects with enough accumulated decisions that they need to be referenced across sessions.
- **Stakeholder sync files** for projects where you regularly update a cofounder, manager, or client.
- **Phased decision lists** for projects that move through clearly distinct phases (design → build → launch).
- **Test data folders** for projects that need to keep sample data separate from the working files.

## Contributing back

If you use cairn for a real project and notice something that worked well, broke down, or could be sharper — open an Issue or a PR on this repo with a meta note. The format is in [`Process_Meta_Notes.md`](Process_Meta_Notes.md). Patterns that show up across multiple contributions get folded into the template README.

**Share processes, never content.** Contribute the workflow lesson, not your project's actual decisions or material. The point is to improve the template, not to publish your work.

This is a manual, low-volume contribution pattern. There is no telemetry, no database, no automatic collection. If usage grows enough that something more structured would be useful, that decision happens later with deliberate design — not by default.

## License

MIT. Use freely. Modify freely. Share freely. Credit appreciated but not required.

## A note on origins

Cairn distills a workflow that emerged from running long-running projects with Claude Code over several months. The patterns that survived multiple projects are in the template. The patterns that were specific to one project (or that needed more discipline than they were worth) are not.

If you find yourself adding a fifth file type or a tenth folder convention, pause and consider whether you are improving the workflow or just rebuilding the project-specific scaffolding you previously had. The leverage of cairn is in keeping the surface small.
