# agency-agents

This is your agency: a `/agent-reach` (alias `/agents-reach`) Claude Code
command that routes a task to the right specialists across the 293-agent
roster from [`msitarzewski/agency-agents`](https://github.com/msitarzewski/agency-agents)
— 17 divisions (academic, design, engineering, finance, game-development,
gis, healthcare, marketing, paid-media, product, project-management, sales,
security, spatial-computing, specialized, support, testing) — and executes
against it, instead of you manually picking which specialist fits and
dispatching one at a time.

## What's actually here

- `.claude/commands/agent-reach.md` — the command itself (also installed as
  `agents-reach` under the alternate spelling, identical content).

This repo does **not** bundle the 293 agent definitions themselves — those
come from `msitarzewski/agency-agents` directly. `/agent-reach` assumes
they're already installed (via Claude Code's plugin/agent install flow) and
available to the `Agent` tool by their display names (e.g. "Frontend
Developer", "Security Architect", "AI Engineer").

## Install

Drop `.claude/commands/agent-reach.md` (and/or `agents-reach.md`) into a
project's `.claude/commands/` directory, or `~/.claude/commands/` to make it
available everywhere. Requires the `msitarzewski/agency-agents` roster
already installed as agent types.

## Use

```
/agent-reach build a rate-limited webhook receiver with retry and dead-lettering
```

The command reads the task, decides which specialists it actually needs
(not all 293 — routing is precision, not maximum blast radius), dispatches
them, verifies their work rather than trusting self-reports, and reports
back a synthesis — not a raw transcript dump. Full behavior is documented
in the command file itself.
