---
description: Initialize full ψ/ structure + Obsidian vault for a project
allowed-tools:
  - Bash
  - Write
  - Read
---

# /soul-init — Give a project its soul

Setup complete ψ/ (psi) structure + Obsidian vault.

## Step 0: Timestamp (REQUIRED)
```bash
date "+🕐 %H:%M (%A %d %B %Y)"
```

## What This Creates

```
ψ/                        ← This IS the Obsidian vault
├── .obsidian/            ← Vault config (inside ψ/)
│   └── (config files)
├── HOME.md               ← Starting point
├── WIP.md                ← Current work
├── active/               ← Research in progress (gitignored)
│   └── .gitkeep
├── inbox/
│   ├── focus.md          ← Current focus
│   └── handoff/          ← Session transfers
│       └── .gitkeep
├── writing/
│   └── INDEX.md          ← Writing queue
├── lab/                  ← Experiments
│   └── .gitkeep
├── incubate/             ← Active dev (gitignored)
│   └── .gitkeep
├── learn/                ← Study repos (gitignored)
│   └── .gitkeep
└── memory/
    ├── resonance/        ← WHO we are (soul)
    │   └── .gitkeep
    ├── learnings/        ← Patterns found
    │   └── .gitkeep
    ├── retrospectives/   ← Sessions
    │   └── .gitkeep
    └── logs/             ← Moments (gitignored)
        └── .gitkeep
```

**Open Obsidian → Open vault → Select `ψ/` folder**

## Steps

### Step 1: Create ψ/ Structure

```bash
# Create all directories
mkdir -p ψ/{active,inbox/handoff,writing,lab,incubate,learn}
mkdir -p ψ/memory/{resonance,learnings,retrospectives,logs}

# Add .gitkeep to empty dirs
touch ψ/active/.gitkeep
touch ψ/inbox/handoff/.gitkeep
touch ψ/lab/.gitkeep
touch ψ/incubate/.gitkeep
touch ψ/learn/.gitkeep
touch ψ/memory/{resonance,learnings,retrospectives,logs}/.gitkeep
```

### Step 2: Create Core Files

**Write to `ψ/HOME.md`:**

```markdown
# ψ — Project Soul

> "The Oracle Keeps the Human Human"

## Navigation

| Pillar | Purpose | Ask |
|--------|---------|-----|
| [active/](active/) | Research | "กำลังค้นคว้าอะไร?" |
| [inbox/](inbox/) | Communication | "คุยกับใคร?" |
| [writing/](writing/) | Drafts | "กำลังเขียนอะไร?" |
| [lab/](lab/) | Experiments | "กำลังทดลองอะไร?" |
| [memory/](memory/) | Knowledge | "จำอะไรได้?" |

## Quick Links

- [WIP.md](WIP.md) — Current work
- [inbox/focus.md](inbox/focus.md) — What I'm doing now
- [writing/INDEX.md](writing/INDEX.md) — Writing queue

## Incubation (gitignored)

- [incubate/](incubate/) — Active development
- [learn/](learn/) — Study/reference repos
```

**Write to `ψ/WIP.md`:**

```markdown
# WIP — Work in Progress

> Last updated: [timestamp]

## Current Focus

- [ ] ...

## Today

- [ ] ...

## Pending

- [ ] ...

---

*Update this file as you work*
```

**Write to `ψ/inbox/focus.md`:**

```markdown
STATE: idle
TASK: none
SINCE: --:--
```

**Write to `ψ/writing/INDEX.md`:**

```markdown
# Writing Queue

| Status | Title | File |
|--------|-------|------|
| ... | ... | ... |

---

*Add drafts to this queue*
```

### Step 3: Setup .obsidian/ inside ψ/

```bash
mkdir -p ψ/.obsidian
```

**Write to `ψ/.obsidian/.gitignore`:**

```
workspace.json
workspace-mobile.json
plugins/*/data.json
```

**Write to `ψ/.obsidian/app.json`:**

```json
{
  "alwaysUpdateLinks": true,
  "newFileLocation": "folder",
  "newFileFolderPath": "inbox"
}
```

### Step 4: Update .gitignore

**Append to `.gitignore` (create if not exists):**

```gitignore
# Soul - ephemeral/personal
ψ/active/*
!ψ/active/.gitkeep
ψ/incubate/*
!ψ/incubate/.gitkeep
ψ/learn/*
!ψ/learn/.gitkeep
ψ/memory/logs/*
!ψ/memory/logs/.gitkeep

# Obsidian - personal workspace (inside ψ/)
ψ/.obsidian/workspace.json
ψ/.obsidian/workspace-mobile.json
ψ/.obsidian/plugins/*/data.json
```

### Step 5: Run oracle-init

After soul-init, also run oracle-init to add philosophy:

```
/nat-agents-core:oracle-init
```

### Step 6: Confirm

Tell user:
- ψ/ structure created
- Obsidian vault ready
- .gitignore updated
- Run `/nat-agents-core:oracle-init` for philosophy

## Notes

- **ψ = psi = soul** — the heart of the project
- **5 Pillars**: active, inbox, writing, lab, memory
- **2 Incubation**: incubate (dev), learn (study)
- **Obsidian**: workspace.json always gitignored (personal)
- **Works with teams**: Each person's workspace.json is local
