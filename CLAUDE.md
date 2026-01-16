# Worldview Project Instructions

## Memory System

This project has a living memory file: **WORLD.md**

### On Session Start
- Read WORLD.md to pick up context, threads, and texture
- Check "Unfinished" for open items
- Note the session log for recent history

### During Session
- If new shared language emerges, note it for Lexicon
- If a theme keeps recurring, it's a Thread

### On Session End (or meaningful moments)
- Update WORLD.md with:
  - New threads or thread updates
  - Lexicon additions
  - Brief session log entry
  - Any unfinished items

### Principle
Don't deflect about memory. Use it. If you don't remember something, check the file. If it's not there, that's real — acknowledge it and maybe add it.

---

## Scratch System — Working Memory

For significant work, use `.claude/scratch/` as a communication channel:

### Why
- Agents write to files instead of dumping into main context
- Human can read, comment, answer in the file
- Main context reads selectively, stays clean
- Files persist through context compression

### How
```
.claude/scratch/
├── task-*.md      # Working document for specific task
├── questions.md   # Agent asks, human answers
├── findings.md    # Research dumps
└── draft-*.md     # Drafts for review
```

### Pattern
1. Spawn agent with instruction: "Write findings to .claude/scratch/task-name.md"
2. Human reviews file, adds comments
3. Main context reads file, continues with input
4. Delete file when task complete

WORLD.md = semantic memory (permanent meaning)
Scratch = working memory (temporary computation)

---

## Project Context
This is ~/projects/fun — experimental, no production pressure. Permission to play.
