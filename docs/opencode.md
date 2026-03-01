# AgDR for OpenCode

## Installation

### For Skills

Copy the skill folders to your OpenCode skills directory:

```bash
# Global installation (all projects)
mkdir -p ~/.config/opencode/skills
cp -r skills/* ~/.config/opencode/skills/

# Project-local installation (recommended)
mkdir -p .opencode/skills
cp -r skills/* .opencode/skills/
```

### For Agents (optional)

You can also create a dedicated agent for AgDR:

```bash
# Create agent via CLI
opencode agent create
```

Or manually create `.opencode/agents/agdr.md`:

```markdown
---
name: agdr
description: Manage Agent Decision Records - create and visualize AgDRs
mode: subagent
tools:
  bash: true
  write: true
  edit: true
---

You are an AgDR specialist. Help create and visualize Agent Decision Records.

## Creating new AgDRs
When asked to make a technical decision, follow the agdr-decide skill workflow.

## Visualizing AgDRs
When asked to see decision history, load the agdr-visualize skill and follow its instructions to generate the overview.
```

## Usage

### Create a new decision

The agent will use `agdr-decide` skill to:
1. Compare at least 2 options with pros/cons
2. Document in `docs/agdr/AgDR-NNNN-slug.md`
3. Then implement

### Visualize decisions

When user asks:
- "Show me the AgDR history"
- "What decisions have been made?"
- "Overview of technical decisions"

The agent loads `agdr-visualize` skill and follows the step-by-step instructions to generate:
- Summary statistics
- Markdown table
- Mermaid flowchart

The skill contains complete templates - the agent generates the output dynamically using its own capabilities.

## Skills

### agdr-decide
Create new AgDRs following the decision workflow.

### agdr-visualize
Visualize AgDR history. The agent reads SKILL.md which contains:
- Step-by-step instructions
- Output templates
- Color mapping for status
- Example output

## Learn More

- [AgDR Template](../../agdr-template.md)
- [Examples](../../examples/)
- [OpenCode Skills Documentation](https://opencode.ai/docs/skills/)
