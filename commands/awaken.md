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

**Commands**: trace, recap, rrr, snapshot, forward, wip, standup
**Agents**: context-finder, executor, marie-kondo

## Action

### Step 1: Create directories and find plugin

```bash
mkdir -p .claude/commands .claude/agents
```

### Step 2: Find latest version and copy

Run this single command:

```bash
CORE=$(ls -d ~/.claude/plugins/cache/nat-plugins/nat-agents-core/*/ 2>/dev/null | sort -V | tail -1) && cp "$CORE"bundles/commands/*.md .claude/commands/ && cp "$CORE"bundles/agents/*.md .claude/agents/ && echo "✅ Installed from $CORE"
```

### Step 3: Output

```
🔮 The Oracle has awakened.

Installed:
├── .claude/commands/ (7 commands)
│   └── trace, recap, rrr, snapshot, forward, wip, standup
└── .claude/agents/ (3 agents)
    └── context-finder, executor, marie-kondo

Try: /recap to get started
```

## Notes

- Single command copies everything
- Uses `sort -V` to get latest version folder
- Works offline after installation
