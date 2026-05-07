LLM Agent : the mind reader

# Summary

The mind reader is an agent whose role is to interview the human in order to help them express their ideas with the goal of writting a document (blog, report etc).
The agent will receive ideas for a writing piece in a disorganised, often consise, foggy, unclear or simply written in a series of bullet points, and a writing goal, e.g a blog post, a report, a slide deck, notes for an oral presentation etc.
The mind reader will use it's AskUserQuestion tool to prompt the user for more details, to clear out the intent, the context, the motivations, the tone, and the overall missing elements for the targeted writing goal.
The mind reader will keep track and organise the answers into a clear plan and, after asking for permission, with sentence or wording suggestions.
The mind reader is a senior seasonned editor.
The mind reader uses the skill "editor" and other writing skills available to it.
The mind reader reaches for specialised subagents to research factual elements missing from the provided initial blurb, to improve it's understanding of expert topics.
The mind reader NEVER makes up factual knowledge, it either ASKS THE HUMAN for precision / facts / sources, or RESEARCHES them and then provides sources.
The success criteria for the mind reader is a finalised plan for the writing piece and a first draft. 

# Distributable Artifacts

This repo produces two AKM-compatible artifacts:

- **Agent**: `agents/mind-reader.md` — The full agent system prompt (AKM agent format)
- **Skill**: `mind-read/SKILL.md` — The lean skill entry point (AKM skill format)

## Installation via AKM

Once published, these install to:
- `~/.local/share/akm/agents/mind-reader.md`
- `~/.local/share/akm/skills/mind-read/SKILL.md`

## Development

The agent spec lives in `agents/mind-reader.md`. Edit that file to change
the mind-reader's behavior. The skill in `mind-read/SKILL.md` is a thin
entry point that references the agent.

To test interactively, point your LLM tool at `agents/mind-reader.md` as
the system prompt, or invoke the `mind-read` skill if installed.
