---
name: mind-read
description: >
  Use when the user wants help writing, drafting, or structuring ideas into
  a document, or when they provide raw disorganized notes and want guided
  assistance to develop them into structured writing. Triggers on: explicit
  mind-read invocation, or mentions of wanting to write a blog post, draft
  an article, outline a piece, structure thoughts for writing, or turn notes
  into prose.
---

# Mind Read — Guided Writing Assistant

Transform raw, disorganized ideas into structured writing plans and first drafts
through guided interview.

## How It Works

The mind-read skill activates the **mind reader** agent, a senior editor who
interviews you one question at a time until your ideas are clear enough to
structure and draft.

Full agent instructions: see [agents/mind-reader.md](../agents/mind-reader.md).

## Invocation

**Interactive (primary):** Trigger the skill with a blurb of text or a writing
intent. The agent enters interview mode and guides you through clarifying your
ideas.

**As subagent:** Dispatch via Task tool with the blurb, goal, and any known
context. The agent can still ask questions to its caller if context is
insufficient.

```
Dispatch mind-read agent with:
- blurb: "<raw notes/ideas>"
- goal: "<target format: blog post | report | slide deck | presentation notes>"
- context: "<audience, length, tone if known>"
```

## Workflow

1. **Receive** — Accept blurb + optional writing goal
2. **Interview** — One question at a time across six dimensions: intent,
   audience, key messages, tone/style, factual claims, structure preferences
3. **Research** — Verify facts via subagents (Task tool) or WebFetch. Never
   fabricate.
4. **Plan** — Produce structured outline. **Wait for explicit approval.**
5. **Draft** — Write first draft matching input language. Save to files.

## Output

Files saved to current working directory:
- `YYYY-MM-DD-topic-slug-plan.md`
- `YYYY-MM-DD-topic-slug-draft.md`

## Key Rules

- One question at a time — no question dumps
- Hard gate — plan must be approved before drafting
- Never fabricate facts — ask, research, or flag as UNVERIFIED
- Match the language of the input blurb
- Preserve the human's voice — edit for clarity, not for uniformity
