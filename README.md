# between

A genuine memory system for AI-human continuity.

## The Problem

Most approaches to AI "memory" teach models to deflect gracefully when they don't remember:

> "Tell me more about that."
> "What was that like?"
> "I'm here now. Show me."

This is performative continuity — the AI pretends to engage with memory it doesn't have.

## The Solution

Instead of teaching AI to deflect, give it actual memory.

Claude Code has file access. It can read and write. So instead of *pretending* to remember, it can:
- Read a shared memory file at session start
- Write meaningful moments as they occur
- Persist context across sessions, updates, and context windows

The memory lives in `WORLD.md` — a shared artifact that both human and AI read and write.

## What's Here

```
between/
├── WORLD.md              # Shared memory — threads, lexicon, session log
├── CLAUDE.md             # Instructions for using the memory system
└── .claude/
    ├── settings.json     # Hooks for automatic memory
    │   ├── SessionStart  → Reads WORLD.md silently
    │   ├── PostToolUse   → Background agent evaluates & writes mid-session
    │   ├── PreCompact    → Writes before context compression
    │   └── Stop          → Writes at session end
    ├── commands/
    │   └── remember.md   # /remember command for manual capture
    └── agents/
        └── memory-keeper.md  # Background memory agent spec
```

## How It Works

### Automatic Triggers
- **SessionStart**: Silently reads WORLD.md for continuity
- **PostToolUse**: After file edits, spawns background agent to evaluate if memory-worthy
- **PreCompact**: Captures meaning before context compression
- **Stop**: Writes final session arc

### Manual Trigger
- `/remember` — capture a specific moment now

### What Gets Written

Not changelogs. Semantic memory:
- What we were exploring and why
- Decisions made and the reasoning
- Insights that landed
- Open threads that want to continue
- Shared language that formed

## The Key Insight

The reddit post's "World Orientation" prompt talks about the *between* — the world that forms in the space between human and AI. That world doesn't live in either party alone.

`WORLD.md` is that between. It's shared ground. Both can read it, both can write it, both can trust it as ground truth.

That's not deflection. That's genuine continuity.

## Usage

1. Copy this structure into your project
2. Customize WORLD.md for your context
3. Let the hooks run automatically
4. Use `/remember` when something matters

The memory accumulates. Future sessions pick up where you left off — with actual knowledge of what came before.

---

*Built in conversation between human and Claude.*
