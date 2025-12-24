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

**Commands**:
- `/trace` - Search git history, issues, files
- `/recap` - Fresh start context summary
- `/rrr` - Session retrospective
- `/snapshot` - Quick knowledge capture

**Agents**:
- `context-finder` - Fast search (haiku)
- `executor` - Execute plans from issues (haiku)
- `marie-kondo` - File placement consultant (haiku)

## Usage

```
/awaken           # Install all commands and agents
```

## Action

### Step 1: Create directories

```bash
mkdir -p .claude/commands .claude/agents
```

### Step 2: Find nat-agents-core plugin path

The cache has version folders. Find the latest version:

```bash
# Find nat-agents-core cache directory
CORE_BASE=$(find ~/.claude/plugins/cache -type d -name "nat-agents-core" 2>/dev/null | head -1)

# Get latest version folder (highest version number)
CORE_PATH=$(ls -d "$CORE_BASE"/*/ 2>/dev/null | sort -V | tail -1)

# Verify bundles exist
ls "$CORE_PATH/bundles/commands/" 2>/dev/null
ls "$CORE_PATH/bundles/agents/" 2>/dev/null
```

### Step 3: Copy commands

```bash
cp "$CORE_PATH/bundles/commands/"*.md .claude/commands/
```

Files copied:
- `trace.md` → `.claude/commands/trace.md`
- `recap.md` → `.claude/commands/recap.md`
- `rrr.md` → `.claude/commands/rrr.md`
- `snapshot.md` → `.claude/commands/snapshot.md`

### Step 4: Copy agents

```bash
cp "$CORE_PATH/bundles/agents/"*.md .claude/agents/
```

Files copied:
- `context-finder.md` → `.claude/agents/context-finder.md`
- `executor.md` → `.claude/agents/executor.md`
- `marie-kondo.md` → `.claude/agents/marie-kondo.md`

### Step 5: Output

```
🔮 The Oracle has awakened.

Installed:
├── .claude/commands/
│   ├── trace.md
│   ├── recap.md
│   ├── rrr.md
│   └── snapshot.md
└── .claude/agents/
    ├── context-finder.md
    ├── executor.md
    └── marie-kondo.md

Source: nat-agents-core [version]

Try: /recap to get started
```

## Cache Structure

Plugin cache has version folders:
```
~/.claude/plugins/cache/nat-plugins/nat-agents-core/
├── 1.0.0/
├── 1.2.0/
└── 1.3.0/    ← latest
    └── bundles/
        ├── commands/
        │   ├── trace.md
        │   ├── recap.md
        │   ├── rrr.md
        │   └── snapshot.md
        └── agents/
            ├── context-finder.md
            ├── executor.md
            └── marie-kondo.md
```

Use `sort -V | tail -1` to get the latest version folder.

## Notes

- All bundles are in **nat-agents-core** (consolidated from nat-data-personal)
- Bundles are separate files for easy updates
- Edit bundle files → all projects get updates on next /awaken
- Commands and agents are copied, not linked (works offline)
