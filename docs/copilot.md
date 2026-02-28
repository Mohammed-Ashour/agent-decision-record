# AgDR for GitHub Copilot

## Installation

Copy the skills to your project's `.github/` directory:

```bash
# For decision making
mkdir -p .github
cp skills/agdr-decide/SKILL.md .github/copilot-instructions.md

# For visualization
cp skills/agdr-visualize/SKILL.md .github/agdr-visualize.md
```

Or append to existing instructions:
```bash
cat skills/agdr-decide/SKILL.md >> .github/copilot-instructions.md
```

## Usage

### Create a new decision
Ask Copilot: "Which testing framework should we use?"

Copilot will:
1. Compare at least 2 real options
2. Create an AgDR file at `docs/agdr/AgDR-NNNN-slug.md`
3. Then proceed with implementation

### Visualize decisions
Ask Copilot: "Show me the AgDR history"

The agent loads the skill and generates the visualization dynamically.

## What Each Skill Does

### agdr-decide
When Copilot detects a technical decision:
1. Stop before implementing
2. Compare at least 2 real options
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
- [GitHub Copilot Custom Instructions](https://docs.github.com/copilot/customizing-copilot/adding-custom-instructions-for-github-copilot)
