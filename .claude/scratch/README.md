# Scratch — Working Memory

This directory is for **working documents** — communication between main context, agents, and human.

Unlike WORLD.md (semantic memory that persists meaning), scratch files are temporary working space.

## How to Use

### Agent → Human
Agent writes findings, questions, or drafts here. Human reads and responds in the file.

### Human → Agent
Human adds context, answers, or corrections. Agent reads on next pass.

### Main Context
Reads files on demand instead of loading everything into context. Summarizes, doesn't dump.

## Conventions

| File | Purpose |
|------|---------|
| `task-*.md` | Working document for a specific task |
| `questions.md` | Agent asks, human answers |
| `findings.md` | Research dumps, read selectively |
| `draft-*.md` | Drafts for review |

## Lifecycle

1. Create when needed
2. Use during task
3. Delete or archive when done

These files are ephemeral. WORLD.md is permanent. Don't confuse them.
