# AgDR for Claude Code

## Installation

Copy the skills to your project's `.claude/commands/` directory:

```bash
# For decision making (becomes /decide command)
mkdir -p .claude/commands
cp skills/agdr-decide/SKILL.md .claude/commands/decide.md

# For visualization (becomes /agdr-visualize command)
cp skills/agdr-visualize/SKILL.md .claude/commands/agdr-visualize.md
```

## Usage

### Create a new decision
```
/decide which testing framework to use
```

### Visualize decisions
```
/agdr-visualize show me the AgDR history
```

The agent loads the skill and generates the visualization dynamically.

## What Each Skill Does

### /decide
Claude Code will:
1. Analyze your codebase context
2. Present 2-4 options with pros/cons table
3. Make a recommendation with the Y-statement format
4. Create an AgDR file at `docs/agdr/AgDR-NNNN-slug.md`
5. Then proceed with implementation

### /agdr-visualize
Generates `docs/agdr/flow.md` with:
- Summary statistics
- Markdown table for quick scanning
- Mermaid flowchart with color-coded statuses

## Enforcement via CLAUDE.md

For automatic decision detection, add to your `CLAUDE.md`:

```markdown
## Technical Decisions
Before making any technical decision, STOP and run /decide.
```

## Learn More

- [AgDR Template](../../agdr-template.md)
- [Examples](../../examples/)
