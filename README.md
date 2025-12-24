# nat-agents-core

Core agents and commands for Claude Code — workflow automation + project initialization.

## Installation

```
/plugin install nat-agents-core@nat-plugins
```

First time? Add the marketplace first:
```
/plugin marketplace add laris-co/nat-plugins
```

## Commands

| Command | What it does |
|---------|--------------|
| `/awaken` | 🔮 Install commands + agents to your project |
| `/soul-init` | Create full ψ/ structure + Obsidian vault |
| `/soul-lite` | Create minimal ψ/ (memory only) |
| `/oracle-init` | Setup Oracle/Shadow philosophy |
| `/context-finder` | Search git history, issues, files |

## What /awaken Installs

Running `/awaken` in your project installs:

**Commands** (to `.claude/commands/`):
- `/trace` - Search git, issues, files
- `/recap` - Fresh start context summary
- `/rrr` - Session retrospective
- `/snapshot` - Quick knowledge capture
- `/forward` - Forward context to new session
- `/wip` - Show work in progress
- `/standup` - Daily standup

**Agents** (to `.claude/agents/`):
- `context-finder` - Fast search (haiku)
- `executor` - Run commands from specs (haiku)
- `marie-kondo` - File placement consultant (haiku)

## Quick Start

```
# 1. Install plugin
/plugin install nat-agents-core@nat-plugins

# 2. Initialize your project (choose one)
/soul-lite                    # Minimal setup
/soul-init                    # Full setup with Obsidian

# 3. Install workflow commands
/awaken

# 4. Start working
/recap
```

## License

MIT
