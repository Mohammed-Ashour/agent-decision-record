---
id: AgDR-0002
timestamp: 2026-02-28T00:00:00Z
agent: codex
model: gpt-5
trigger: user-prompt
status: executed
supersedes: AgDR-0001
---

# Add Repo-Wide AgDR Flow Visualization (Mermaid + Table)

> In the context of an AgDR repository with multiple decision records, facing a request to visualize the history of all decisions, I decided to implement dedicated skills for all supported agents plus a deterministic Python script that generates both a Mermaid flowchart and a markdown table, accepting the tradeoff of additional code to maintain for maximum utility (visual flow + quick scanning).

## Context

- The repository had AgDR-0001 as the first decision record.
- Users needed a quick overview of all decisions before reading individual ones.
- A Mermaid diagram alone wasn't sufficient for quick scanning.
- The same script should work across all supported agents (Codex, Claude Code, Cursor, Copilot, Windsurf, OpenCode, etc.).

## Options Considered

| Option | Pros | Cons |
|--------|------|------|
| Mermaid only | Visual relationships | Hard to scan quickly |
| Table only | Quick scanning | No visual flow |
| Dual output (chosen) | Best of both: visual flow + quick scan | Slightly more complex |

## Decision

Chosen: **Dual output (Mermaid + markdown table) via centralized Python script**, because it provides both visual relationship understanding and quick decision history scanning in a single file.

## Consequences

- Users can visualize AgDR relationships via skills for all agents.
- Output contains: summary stats, markdown table, Mermaid flowchart.
- Status colors in Mermaid: executed=green, proposed=orange, superseded=gray.
- Chronological, supersedes, and reference edges show relationships.
- Agent-native approach: skills contain step-by-step instructions, no script needed.
- Skills are portable and work across all agents.

## Artifacts

- `skills/agdr-visualize/SKILL.md` - Agent-native visualization instructions
- `skills/agdr-decide/SKILL.md` - Decision creation skill
- `docs/codex.md` - Codex setup
- `docs/claude-code.md` - Claude Code setup
- `docs/cursor.md` - Cursor setup
- `docs/copilot.md` - Copilot setup
- `docs/windsurf.md` - Windsurf setup
- `docs/opencode.md` - OpenCode setup
