# AgDR for Windsurf

## Installation

Copy the skills to your project's `.windsurf/rules/` directory:

```bash
# For decision making
mkdir -p .windsurf/rules
cp skills/agdr-decide/SKILL.md .windsurf/rules/agdr.md

# For visualization
cp skills/agdr-visualize/SKILL.md .windsurf/rules/agdr-visualize.md
```

## Usage

### Create a new decision
Ask Cascade: "Decide on authentication strategy"

Cascade will:
1. Compare options with pros/cons
2. Create `docs/agdr/AgDR-NNNN-slug.md`
3. Then implement

### Visualize decisions
Ask Cascade: "Show me the AgDR history"

The agent loads the skill and generates the visualization dynamically.

## What Each Skill Does

### agdr
When Windsurf Cascade detects a technical decision:
1. Stop before implementing
2. Present options with pros/cons
3. Create an AgDR file
4. Then proceed with implementation

### agdr-visualize
Generates `docs/agdr/flow.md` with:
- Summary statistics
- Markdown table for quick scanning
- Mermaid flowchart with color-coded statuses

## Note on Character Limits

Windsurf rules have a 6,000 character limit per file and 12,000 combined. Keep skills focused.

## Learn More

- [AgDR Template](../../agdr-template.md)
- [Examples](../../examples/)
- [Windsurf Rules Documentation](https://docs.windsurf.com/windsurf/cascade)
