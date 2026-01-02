---
description: "🔮 Awaken the Oracle - Install commands and agents in your project"
allowed-tools:
  - Bash
  - Read
  - Write
---

# /awaken - Awaken the Oracle

Install Oracle commands and agents in your project.

## What Gets Installed

**Commands**: trace, recap, rrr, snapshot, forward, wip, standup, now, hours, jump, pending
**Agents**: context-finder, executor, marie-kondo
**Skills**: handoff, context-finder, oracle, oracle-incubate

> Note: `hours`, `jump`, `pending` work best after `/soul-init` or `/soul-lite`

## Action

### Step 1: Create directories and find plugin

```bash
mkdir -p .claude/commands .claude/agents
```

### Step 2: Find latest version and copy

Run this single command:

```bash
CORE=`ls -d ~/.claude/plugins/cache/nat-plugins/nat-agents-core/*/ 2>/dev/null | sort -V | tail -1` && mkdir -p .claude/scripts .claude/skills && cp "$CORE"bundles/commands/*.md .claude/commands/ && cp "$CORE"bundles/agents/*.md .claude/agents/ && cp "$CORE"bundles/scripts/*.sh .claude/scripts/ 2>/dev/null && cp -r "$CORE"bundles/skills/* .claude/skills/ 2>/dev/null && chmod +x .claude/scripts/*.sh 2>/dev/null && echo "✅ Installed from $CORE"
```

### Step 3: Output

```
🔮 The Oracle has awakened.

Installed:
├── .claude/commands/ (11 commands)
│   └── trace, recap, rrr, snapshot, forward, wip, standup, now, hours, jump, pending
├── .claude/agents/ (3 agents)
│   └── context-finder, executor, marie-kondo
└── .claude/skills/ (4 skills)
    └── handoff, context-finder, oracle, oracle-incubate

Try: /recap to get started
```

## Notes

- Single command copies everything
- Uses `sort -V` to get latest version folder
- Works offline after installation
- Uses backticks for bash/zsh compatibility
