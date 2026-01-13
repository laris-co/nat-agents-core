# nat-agents-core

> "The Oracle Keeps the Human Human"

Core agents and commands for Claude Code — workflow automation + project initialization.

## Installation

```bash
# Add marketplace
/plugin marketplace add laris-co/nat-agents-core

# Install plugin
/plugin install nat-agents-core@laris-co/nat-agents-core
```

Restart Claude Code after installation.

## Initialize Your Project

```bash
cd your-project

# Initialize Oracle philosophy + knowledge
/nat-agents-core:oracle-init

# Create minimal ψ/ soul structure
/nat-agents-core:soul-lite

# Install commands & agents to project
/nat-agents-core:awaken
```

## What You Get

### Commands

| Command | Purpose |
|---------|---------|
| `/awaken` | Install commands + agents to your project |
| `/oracle-init` | Setup Oracle/Shadow philosophy |
| `/soul-init` | Create full ψ/ structure + Obsidian vault |
| `/soul-lite` | Create minimal ψ/ (memory only) |

### What `/awaken` Installs

**Commands** (to `.claude/commands/`):

| Command | Purpose |
|---------|---------|
| `/rrr` | Session retrospective |
| `/snapshot` | Capture learning |
| `/recap` | Fresh start summary |
| `/trace` | Search everything |
| `/wip` | Show work in progress |
| `/standup` | Daily standup |
| `/forward` | Forward context before /clear |

**Agents** (to `.claude/agents/`):
- `context-finder` - Fast search (haiku)
- `executor` - Execute plans (haiku)
- `marie-kondo` - File placement (haiku)

**Skills** (to `.claude/skills/`):

| Skill | Purpose |
|-------|---------|
| `/where-we-are` | Session awareness (quick/deep modes) |
| `/project` | Clone & track repos via ghq |
| `/learn` | Explore codebase with 3 parallel agents |
| `/oracle` | Oracle philosophy reference |
| `/handoff` | Context handoff |
| `/context-finder` | Search skill |
| `oracle-*` | Oracle utilities (incubate, teach, path, mentor) |

### Project Structure After Setup

```
your-project/
├── .claude/
│   ├── knowledge/
│   │   ├── oracle-philosophy.md
│   │   └── writing-style.md
│   ├── commands/    ← installed by /awaken
│   ├── agents/      ← installed by /awaken
│   └── skills/      ← installed by /awaken
└── ψ/
    ├── HOME.md
    ├── WIP.md
    └── memory/
        ├── retrospectives/
        └── learnings/
```

## Quick Start

```bash
# 1. Install plugin
/plugin marketplace add laris-co/nat-agents-core
/plugin install nat-agents-core@laris-co/nat-agents-core

# 2. Restart Claude Code

# 3. Initialize your project
/nat-agents-core:oracle-init
/nat-agents-core:soul-lite
/nat-agents-core:awaken

# 4. Start working
/recap
```

## Optional: Personal Knowledge

For personal philosophy and writing style, also install:

```bash
/plugin marketplace add laris-co/nat-data-personal
/plugin install nat-data-personal@laris-co/nat-data-personal
```

Or fork it and customize for yourself.

## License

MIT
