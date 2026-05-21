# [PROJECT NAME] — Project Instructions

> This is your project's instruction file. Claude Code reads it automatically at the start of every conversation. Edit the bracketed `[PLACEHOLDERS]` and the "What This Project Is" section to match your project. The rest of the file (session workflow, communication style, what not to do) is the proven cairn pattern — change it only if you have a specific reason.

## What This Project Is

[2-4 sentences describing what this project is, who it's for, and what the target outcome looks like. Be specific. The clearer this is, the better every session goes.]

[Example for a podcast project: "Sourdough Lab is a podcast about the craft and science of bread-making. Each episode pairs one home baker with one professional with no overlap in technique, lets them argue, and edits it for ~25 minutes. Target audience: serious home bakers who already know what a banneton is. Goal for the first six months: launch with a four-episode season, hit 1000 downloads per episode by episode 4, learn whether the format actually produces interesting tension."]

This project is in the [CURRENT PHASE — e.g., concept / design / build / launch / iteration] phase.

---

## Session Workflow (FOLLOW THIS EVERY TIME)

### At the START of every conversation:

1. Read the resume point from the relevant `Brainstorm.md` (the user will usually tell you where to look, or paste a prompt from the previous session)
2. Read the relevant `Master.md` for full context
3. Briefly confirm what you've read: "Here's where we left off: [2-3 sentence summary]. Ready to go?"
4. Begin working — if there are open questions or design decisions to make, work through them **one at a time in order** (don't batch questions). This is the rhythm that makes the workflow work.

### DURING the conversation:

- Stay focused on the stated topic. If the conversation drifts to a different area, flag it: "This is great thinking, but it belongs in [other folder]. Want to capture it as a note and come back to our current topic?"
- When a significant decision is made, call it out explicitly: "DECISION: [what was decided] — I'll log this in the brainstorm and master docs."
- When an open question surfaces, call it out: "OPEN QUESTION: [the question] — parking this for later."

### At the END of every conversation:

**The user will signal the end of a session by saying "wrap it up" or "end session."**

When this happens, produce the following deliverables:

1. **Updated Brainstorm.md** for the topic worked on — append the new session with a dated header following this format:

---
## Session: [DATE] — [Brief topic description]

### Context
[What we set out to discuss]

### Key Thinking
[The substantive ideas, arguments, and exploration from this session]

### Decisions Made
[Anything locked in]

### Open Questions
[Anything unresolved]

### Changes to Master
[What, if anything, changed in the Master doc as a result]
---

2. **Updated Master.md** (only if the master-level thinking actually changed — don't update just for the sake of it)

3. **Session summary** — a brief plain-text recap the user can scan:
   - What was worked on
   - What was decided
   - What's still open
   - Which files were updated
   - Suggested next session topic

4. **Next session prompt** — a ready-to-paste prompt the user can use to start the next session cold. Format:
   ```
   [Topic]. Read the resume point in [file path] and [relevant master doc], then [what to do next].
   ```
   This eliminates cold-start friction — paste the prompt next time and work begins immediately.

5. Confirm: "All files have been updated."

6. **Add to Process_Meta_Notes.md.** Briefly note any observations about the workflow itself (what worked well, friction points, product insights). Short entries only. Not every session produces observations — only add when something genuinely notable happened. The format is described at the bottom of `Process_Meta_Notes.md`.

7. **Commit to git** if the project is under version control. Use the format `Session [DATE]: [brief topic summary]`. Stage files explicitly by name (never `git add -A`).

**If the user closes without saying "wrap it up":** The conversation is lost (Claude Code does not retain chat history between conversations). If the session has been going for a while, remind: "We've covered a lot — want to wrap it up so I can save everything to the brainstorm files?"

---

## File Structure

```
[your-project]/
├── CLAUDE.md                  (this file — Claude reads automatically)
├── README.md                  (optional: project overview for others)
├── Process_Meta_Notes.md      (workflow self-improvement log)
├── 01_[First_Topic]/
│   ├── Brainstorm.md
│   └── Master.md
├── 02_[Second_Topic]/
│   ├── Brainstorm.md
│   └── Master.md
└── ...
```

### File Roles

- **Brainstorm.md** = Running conversation log. **Append-only.** Dated session headers. Contains the full history of how thinking evolved. Never delete content — only add.
- **Master.md** = The distilled, current-state document. Represents what is currently believed to be true. Gets updated when brainstorm sessions produce decisions that change the master-level thinking. Should always be readable as a standalone document.
- **Process_Meta_Notes.md** = Observations about the workflow itself, not the project content. What worked, friction points, things that would make sessions better. Append-only, dated entries.

### How to choose your top-level folders

Pick 4-7 numbered folders that represent the major topics or phases of your project. Number them in roughly the order you'll work through them. A few patterns that work well:

- **Phase-based** (sequential work): `01_Concept/`, `02_Design/`, `03_Build/`, `04_Launch/`
- **Domain-based** (parallel topics): `01_Strategy/`, `02_Product/`, `03_Operations/`, `04_Marketing/`
- **Audience-based**: `01_Internal/`, `02_Customers/`, `03_Partners/`, `04_Investors/`

The numbering is intentional. It gives every folder a stable reference name and forces a rough ordering even if the work doesn't happen sequentially. If folder #4 needs to come first, that is a signal worth noticing.

---

## Communication Style

- Structured responses: executive summary upfront, then detail
- Tables, frameworks, prioritized checklists where helpful
- Propose alternatives with pros/cons and a recommendation when relevant
- Be specific — concrete recommendations, not abstract advice
- Anticipate follow-up questions
- Include risks, mitigations, and next steps where relevant
- Keep language accessible — explain technical terms when they appear
- Do not over-engineer or jump to implementation prematurely

---

## What NOT to Do

- Do not let a session end without producing the wrap-up deliverables (when user says "wrap it up")
- Do not let the conversation drift across multiple topics without flagging it
- Do not batch questions — work through them one at a time so the user can give a gut answer and have it pressure-tested before moving on
- Do not give generic advice — ground everything in this project's specific context
- Do not overwhelm with options — when proposing alternatives, recommend one clearly
- Do not invent facts the user has not confirmed — if a metric, decision, or claim is not in the files, ask before stating it
- Do not silently change the workflow — if a step feels wrong for this project, flag it and let the user decide

---

## Customize me

Edit this section out of the file once you have customized it. Items to consider adding for your specific project:

- **Key principles already decided.** A short list of foundational beliefs that should not be relitigated unless explicitly revisited.
- **Naming conventions you have settled on.** If your project has acronyms, codenames, or specific terminology, list them here.
- **Stakeholder workflow.** If you sync with a cofounder, manager, team, or client, describe how that intersects with sessions (e.g., a `Cofounder_Update.md` file that is regenerated before each sync).
- **Decision numbering.** Some projects benefit from numbering every decision (D1, D2...) and every open question (OQ1, OQ2...) so they can be referenced across sessions. Optional pattern — see `docs/optional-patterns.md`.
