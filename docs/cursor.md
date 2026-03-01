# AgDR for Cursor

## Installation

Copy the skills to your project's `.cursor/rules/` directory:

```bash
# For decision making
mkdir -p .cursor/rules
cp skills/agdr-decide/SKILL.md .cursor/rules/agdr.md

# For visualization
cp skills/agdr-visualize/SKILL.md .cursor/rules/agdr-visualize.md
```

This uses Cursor's MDC rule format with `alwaysApply: true`.

## Usage

### Create a new decision
Ask Cursor: "Decide which state management to use"

Cursor will:
1. Compare options with pros/cons
2. Create `docs/agdr/AgDR-NNNN-slug.md`
3. Then implement

### Visualize decisions
Ask Cursor: "Show me the AgDR history"

The agent loads the skill and generates the visualization dynamically.

## What Each Skill Does

### agdr (decide)
When Cursor detects a technical decision:
1. Stop before implementing
2. Present options with pros/cons
3. Create an AgDR file
4. Then proceed with implementation

### agdr-visualize
Generates `docs/agdr/flow.md` with:
- Summary statistics
- Markdown table for quick scanning
- Mermaid flowchart with color-coded statuses

## Learn More

- [AgDR Template](../../agdr-template.md)
- [Examples](../../examples/)
