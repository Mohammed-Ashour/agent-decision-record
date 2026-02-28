# AgDR for Codex

## Installation

Copy the skill folders to your Codex skills directory:

```bash
# For decision making
cp -r skills/agdr-decide ~/.codex/skills/

# For visualization
cp -r skills/agdr-visualize ~/.codex/skills/
```

If `CODEX_HOME` is not set:

```bash
mkdir -p ~/.codex/skills
cp -r skills/agdr-decide ~/.codex/skills/
cp -r skills/agdr-visualize ~/.codex/skills/
```

## Usage

### Create a new decision

```
$agdr-decide decide REST vs GraphQL for the new API
```

### Visualize decisions

The agent loads the `agdr-visualize` skill and follows the step-by-step instructions to generate the visualization dynamically.

## What Each Skill Does

### agdr-decide
When Codex is about to make a non-trivial technical decision:
1. Stop before implementing
2. Compare at least 2 real options with pros/cons
3. Create an AgDR file at `docs/agdr/AgDR-NNNN-slug.md`
4. Then proceed with implementation

### agdr-visualize
Generates `docs/agdr/flow.md` with:
- Summary statistics
- Markdown table for quick scanning
- Mermaid flowchart with color-coded statuses

## Files

| File | Purpose |
|------|---------|
| `skills/agdr-decide/SKILL.md` | Decision gating skill |
| `skills/agdr-visualize/SKILL.md` | Visualization skill |

## Learn More

- [AgDR Template](../../agdr-template.md)
- [Examples](../../examples/)
