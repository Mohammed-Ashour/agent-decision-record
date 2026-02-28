---
id: AgDR-0001
timestamp: 2026-02-08T17:54:33Z
agent: codex
model: gpt-5
trigger: user-prompt
status: executed
---

# Add Codex Skill Integration for AgDR

> In the context of an AgDR repository with integrations for multiple AI coding assistants, facing a request to add Codex support, I decided to add a native Codex skill integration and documentation to achieve parity with existing tool integrations and enforce AgDR creation in Codex workflows, accepting the tradeoff of additional maintenance for another integration surface.

## Context

- The repository already had dedicated integrations for Claude Code, Cursor, Copilot, Windsurf, and generic system prompts.
- The user explicitly asked to create Codex skill support and requested changes to `README.md`.
- A generic system-prompt path existed, but no Codex-native skill folder or install instructions were present.
- Consistency of onboarding mattered because this repo is primarily an integration/reference project.

## Options Considered

| Option | Pros | Cons |
|--------|------|------|
| Keep only generic system-prompt guidance | Minimal changes and low maintenance | Does not provide Codex-native skill packaging or explicit trigger guidance |
| Add README mentions for Codex only | Quick visibility that Codex is supported | Documentation-only approach without executable/portable skill instructions |
| Add dedicated Codex integration (`tools/codex/agdr-decide`) plus README updates | Matches existing integration pattern, gives concrete install/usage path, and encodes AgDR workflow directly for Codex | Adds another maintained integration and documentation surface |

## Decision

Chosen: **Add dedicated Codex integration (`tools/codex/agdr-decide`) and update docs**, because it provides a concrete, reusable, and tool-native way to enforce AgDR behavior in Codex instead of relying on ad-hoc prompts.

## Consequences

- Codex users now have a clear installation and invocation path via `tools/codex/README.md`.
- The root `README.md` now lists Codex as a first-class integration, improving discoverability.
- The project must keep the Codex skill and docs aligned with template/rule updates over time.

## Artifacts

- Commit: `c2ace4fb22623495324179b3f2a2c234c6a5d9d8`
- Files:
  - `README.md`
  - `tools/codex/README.md`
  - `tools/codex/agdr-decide/SKILL.md`
  - `tools/system-prompts/README.md`
