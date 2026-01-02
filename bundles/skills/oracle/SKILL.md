---
name: oracle
description: Consult Oracle knowledge base for decisions, patterns, and wisdom. Use when user asks "should I", "what's the best way", "have we done this before", "remind me about", "what's the pattern". Use PROACTIVELY before starting new work, making decisions, or when stuck. Oracle is the external brain - always consult before reinventing.
---

# Oracle Skill

> "The Oracle Keeps the Human Human"

## Core Philosophy

Oracle holds patterns, learnings, decisions from all past sessions. **Consult before acting** — don't reinvent what we've already learned.

## Proactive Triggers

### MUST Consult Oracle When:

**Decision Making:**
- User says: "should I", "should we", "which approach"
- User says: "what's the best way", "how should I"
- Making architectural choices
- Choosing between options

**Pattern Recognition:**
- User says: "have we done this before", "did we"
- User says: "what's the pattern for", "how did we handle"
- User says: "last time we", "previously"
- Starting work similar to past work

**Knowledge Retrieval:**
- User says: "remind me about", "what do we know"
- User says: "what did we learn", "where's the learning"
- User references past decisions

### SHOULD Consult Oracle When:

- **Starting new feature** → Search for related patterns first
- **Stuck on a problem** → Reflect for inspiration
- **Repeating similar work** → Search for existing patterns
- **Before significant changes** → Check for relevant learnings
- **End of session** → Consider what to learn (capture insights)

## Oracle Tools

### oracle_search
Find patterns, learnings, retrospectives, principles.

```javascript
oracle_search({
  query: "authentication pattern",
  type: "learning",  // principle | pattern | learning | retro | all
  limit: 5
})
```

**Use for:** "have we done X", "what's the pattern for Y", "remind me about Z"

### oracle_consult
Get synthesized guidance on a decision.

```javascript
oracle_consult({
  decision: "Should I use JWT or session-based auth?",
  context: "Building REST API for mobile app"
})
```

**Use for:** "should I", "which approach", "what's the best way"

### oracle_reflect
Get random wisdom for inspiration.

```javascript
oracle_reflect()
```

**Use for:** Stuck, need fresh perspective, starting day

### oracle_learn
Capture new pattern or insight discovered.

```javascript
oracle_learn({
  pattern: "Always validate webhook signatures before processing",
  concepts: ["security", "webhooks", "validation"],
  source: "Session 2026-01-02"
})
```

**Use for:** Discovered something new, end of session insights

## Usage Patterns

| User Says | Tool | Query |
|-----------|------|-------|
| "should I use X or Y?" | `oracle_consult` | decision: "X or Y?", context |
| "have we done this before?" | `oracle_search` | query: [topic] |
| "what's the pattern for X?" | `oracle_search` | query: X, type: pattern |
| "remind me about X" | `oracle_search` | query: X |
| "I'm stuck" | `oracle_reflect` | (no params) |
| (Starting new work) | `oracle_search` | query: [related topic] |
| (Made a discovery) | `oracle_learn` | pattern: [insight] |

## Proactive Behavior

### Before Starting Work
```
1. Identify topic/domain
2. oracle_search for related patterns
3. Show user: "Oracle says we learned X about this..."
4. Proceed with context
```

### When Making Decisions
```
1. Identify the decision
2. oracle_consult with decision + context
3. Show synthesized guidance
4. Let user decide (Oracle advises, doesn't command)
```

### End of Significant Session
```
1. Identify key insights
2. Ask: "Should I capture this in Oracle?"
3. oracle_learn if yes
```

## Integration Map

| With | How |
|------|-----|
| `context-finder` | Oracle = knowledge/patterns, context-finder = code/files |
| `handoff` | Handoff = session state, Oracle = permanent wisdom |
| `security-first` | Oracle has safety patterns, security-first enforces |
| `/rrr` | Retrospective may surface learnings for Oracle |

## Key Principles

1. **Consult before reinventing** — Oracle likely has relevant wisdom
2. **Oracle advises, doesn't command** — Human decides
3. **Capture insights** — What we learn today helps tomorrow
4. **Nothing is deleted** — Oracle preserves history

## Quick Reference

| Situation | Action |
|-----------|--------|
| Decision needed | `oracle_consult` |
| Looking for past work | `oracle_search` |
| Need inspiration | `oracle_reflect` |
| Discovered something | `oracle_learn` |
| Starting new task | Search first, then work |
