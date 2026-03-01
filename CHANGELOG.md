# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.2.0] - 2026-02-28

### Added

- New `agdr-visualize` skill for generating visual decision history
  - Agent-native approach with step-by-step instructions (no script dependency)
  - Generates summary statistics, markdown table, and Mermaid flowchart
  - Supports three edge types: chronological, superseded, and references
  - Status color coding: green (executed), orange (proposed), gray (superseded/unknown)
- Centralized `skills/` directory for portable agent skills
  - `skills/agdr-decide/` - decision creation skill
  - `skills/agdr-visualize/` - visualization skill
- New `docs/` directory with per-agent setup guides
  - OpenCode, Codex, Claude Code, Cursor, Copilot, Windsurf
- AgDR-0002 documenting the visualization decision

### Changed

- **BREAKING**: Restructured repository layout
  - Skills moved from `tools/` to `skills/` directory
  - Agent setup docs moved to `docs/` directory
  - Skills are now self-contained and portable across agents
- Made skills agent-agnostic
  - Removed hardcoded "codex" references from skill descriptions
  - Agent field now uses `{agent-name}` placeholder in templates
- Updated README.md
  - New install commands for all agents
  - Simplified structure overview
  - Updated Quick Start section
- Improved `agdr-visualize` skill documentation
  - Added output destination (`docs/agdr/flow.md`)
  - Added edge case handling (no files, missing fields, self-loops)
  - Added troubleshooting table
  - Fixed Mermaid template (escaped pipe characters)

### Removed

- **BREAKING**: Removed Python-based visualization script
  - Deleted `tools/agdr-visualize/scripts/generate_agdr_flow.py`
  - Deleted associated unit tests
  - Deleted CI workflow for tests
  - Rationale: agent-native approach is more portable and requires no dependencies
- Removed deprecated documentation
  - `docs/agdr/AGENTS-VISUALIZE.md` (replaced by skill)
  - `docs/agdr-mermaid-flow-plan.md` (implementation complete)
- Removed old `tools/` directory structure

## [1.1.0] - 2026-02-08

### Added

- Claude Code plugin packaging — installable via `/plugin marketplace add me2resh/agent-decision-record`
- `.claude-plugin/plugin.json` — plugin manifest for Claude Code recognition
- `.claude-plugin/marketplace.json` — marketplace catalog for registry auto-discovery
- `commands/decide.md` — user-invoked `/decide` slash command
- `skills/decide/SKILL.md` — model-invoked skill with YAML frontmatter

### Changed

- Updated README with plugin install instructions in Quick Start section

## [1.0.0] - 2026-02-05

### Added

- Initial release of the AgDR standard
- Full and short AgDR templates (`agdr-template.md`, `agdr-template-short.md`)
- 6 real-world examples (auth, DynamoDB, migration, MVVM, CI/CD, image loading)
- Tool integrations for Claude Code, Cursor, GitHub Copilot, Windsurf, and generic system prompts
- Pre-commit hook for AgDR enforcement
- Contributing guidelines and CC BY 4.0 license
