# AgDR Skills

This directory contains reusable skills for managing Agent Decision Records (AgDRs).

## Available Skills

### agdr-decide

Create new Agent Decision Records when making technical decisions.

**When to use:** When you need to document a technical decision (choosing libraries, patterns, architecture).

**Install:** Copy `agdr-decide/` folder to your agent's skills directory.

### agdr-visualize

Visualize the history of all AgDR decisions in a repository using the agent's own capabilities.

**When to use:** When you want to see an overview of all decisions made (summary + table + Mermaid diagram).

**How it works:** The agent reads the SKILL.md which contains step-by-step instructions and templates. The agent follows the recipe to generate the output dynamically - no script needed.

**Features:**
- Summary statistics (total, by status, by agent)
- Markdown table for quick scanning
- Mermaid flowchart with color-coded statuses
- Chronological, superseded, and reference edges

## Directory Structure

```
skills/
├── agdr-decide/
│   └── SKILL.md              # Decision creation skill
├── agdr-visualize/
│   └── SKILL.md              # Visualization skill (agent-native instructions)
└── README.md                 # This file
```

## Documentation

See `docs/` directory for agent-specific setup instructions:
- `docs/codex.md` - Codex
- `docs/claude-code.md` - Claude Code
- `docs/cursor.md` - Cursor
- `docs/copilot.md` - Copilot
- `docs/windsurf.md` - Windsurf
- `docs/opencode.md` - OpenCode
