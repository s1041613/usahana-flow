# usahana-flow

Usahana's dev flow for Claude Code. Before work starts on an issue, it runs Preflight. Preflight picks one route:

- **BDD first.** A business rule has more than one option. Agree on it with Usahana first.
- **Poteto build.** Nothing is stuck. `/pstack:poteto-mode` builds it and hands back evidence.
- **Ask Usahana.** A fact is missing, or the work is a one-way door.

It needs [pstack](https://github.com/cursor/plugins/tree/main/pstack). It uses pstack's principles and does not copy them.

## What is in this repo

```
skills/usahana-flow/                 the main flow and its playbooks
skills/principle-check-source-first/ the one principle pstack does not have
agents/usahana-agent.md              read-only helper for Preflight and bug tracing
templates/usahana-models.md          copy to ~/.claude/rules/ to pick models
templates/project-settings/          copy to docs/usahana-flow/ in each project
```

## Try it

Load it from this folder for one session:

```
claude --plugin-dir ~/Documents/usahana-flow
```

Then run `/usahana-flow` on an issue.

## Set up a project

1. Copy `templates/project-settings/` to `docs/usahana-flow/` in the project.
2. Fill in the topic files. Delete the ones the project does not need.
3. Copy `templates/usahana-models.md` to `~/.claude/rules/` if you want to change the models.
