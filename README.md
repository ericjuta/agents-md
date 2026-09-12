# agents-md

My cross-project working agreement for coding agents.

[AGENTS.md](AGENTS.md) holds the always-on preferences. Repository setup, command recipes, and project-specific procedures belong in workspace instructions or task-specific skills.

## What it covers

- Finish the requested work, verify it, and stop at the agreed scope.
- Load context for the task instead of reading every document upfront.
- Fix causes, reuse existing conventions, and keep verification proportional to risk.
- Preserve unrelated work and respect authorization for Git, external, and destructive actions.
- Keep evidence honest and reports concise.

## Use it

1. Read [AGENTS.md](AGENTS.md) and adapt it to your tools, permissions, and workflow.
2. Merge the parts you want into your existing instructions rather than overwriting them. For Codex global guidance, use `AGENTS.md` in `CODEX_HOME`, normally `~/.codex/AGENTS.md`.
3. Keep project rules in the repository's own `AGENTS.md`. Start a new Codex session after changing its instructions.

The **Durable second brain** section describes my private Obsidian setup and references a locally installed skill. Neither the vault nor that skill is included here. Replace or remove that section for your own setup, and define your own authorization boundaries rather than inheriting mine.

## Background

Refactored using OpenAI's [Rethinking skills and prompts for GPT-6 Astra](https://developers.openai.com/blog/rethinking-skills-and-prompts-for-gpt-6-astra): trim blanket procedures, load guidance when relevant, and make completion and decision boundaries explicit.

These are personal operating preferences, not an official OpenAI template or a benchmarked claim of better model performance.

For instruction discovery and precedence, see [Codex's AGENTS.md documentation](https://developers.openai.com/codex/guides/agents-md).
