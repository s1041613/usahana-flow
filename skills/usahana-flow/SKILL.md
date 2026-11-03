---
name: usahana-flow
description: Usahana's dev flow. Run Preflight before work starts on an issue. Preflight picks one route. Use for /usahana-flow, "can this issue start?", or "which route does this issue take?".
disable-model-invocation: true
---

# Usahana flow

Each issue takes one route. Preflight picks the route. Do not pick it by feeling.

## Read the project settings when you need them

Each project keeps its settings in `docs/usahana-flow/`. Read `index.md` before you run Preflight. It is short. It lists the topic files and says when to read each one.

Open a topic file only when a step needs it. Do not read all of them at the start.

If `index.md` does not exist, ask Usahana to make one. If a step needs a topic that the index does not list, ask Usahana. Do not guess.

## Always do these

- Before work starts on any issue, run **Preflight** (`playbooks/preflight.md`).
- Check every spec against the source code before you trust it. Use **principle-check-source-first**.
- Before you ask Usahana a question, give the evidence. Give two or three options and the cost of each one. Say which option you will use if Usahana does not answer. Send all questions in one message.
- When there is more than one good way to build something, and you can build each way, run `/pstack:arena`. Then show the result to Usahana in lavish.
- For every UI change, check every screen size in the project settings.
- If a migration removes or changes something, stop and ask Usahana.
- If you find a bug after a merge, fix it with `/pstack:poteto-mode`. Then find the issue, the spec line, or the decision that caused it. Add it to the incidents topic in the project settings. If Preflight should have caught it, add a check to Preflight.

## Principles

Read the full SKILL.md of a principle before you use it.

From this flow:

- **Check Source First.** Use it when you write a spec, update a spec, or start work. If the spec and the code say different things, the code wins.

From pstack. Use them as they are. Do not copy them.

- **Prove It Works** (`/pstack:principle-prove-it-works`). Use it before you say a task is done.
- **Never Block on the Human** (`/pstack:principle-never-block-on-the-human`). Do not ask about work you can undo.
- **Exhaust the Design Space** (`/pstack:principle-exhaust-the-design-space`). Use it when there is more than one good way to build something.
- **Migrate Callers Then Delete Legacy APIs** (`/pstack:principle-migrate-callers-then-delete-legacy-apis`). Use it when you remove old code or old schema.
- **Encode Lessons in Structure** (`/pstack:principle-encode-lessons-in-structure`). Use it when a script, a lint, or CI can do a check.
- **Sequence Work into Verifiable Units** (`/pstack:principle-sequence-verifiable-units`). Use it when you split an issue into PRs.

## Subagents

- For Preflight research and for tracing a bug, spawn `usahana-agent`. Give it the absolute path of this SKILL.md and of the project's `index.md`.
- Pick the model for each role from `~/.claude/rules/usahana-models.md`. Each line names a role and a model. If the file or the line is missing, use the default below.
  - `preflight search`: finds files, reads old code, and counts things. Default `haiku`.
  - `preflight compare`: compares the spec with the code. Default `sonnet`.
  - `bug trace`: traces a bug to its issue and decision. Default `sonnet`.
  - `judgment`: picks the route and writes questions for Usahana. Default: the main chat model.
- `usahana-agent` does not write code. Poteto build gives code work to `/pstack:poteto-mode`, and it spawns its own agents.
- Read each agent's reply yourself before you use it. Check its evidence.

## Playbooks

Make a todo list from the steps of the playbook. If you skip a step, keep it on the list and write `skip: <reason>`.

- **Preflight.** Run it before every issue. Answer six questions and pick a route.
- **BDD first.** Use it when Preflight question 3 is stuck. Agree on the business rules with Usahana first.
- **Poteto build.** Use it when nothing in Preflight is stuck. Give the work to `/pstack:poteto-mode` and ask for the evidence in the playbook.

Some cases do not use a playbook. If Preflight question 2 is stuck, or if the work is a one-way door, send your questions to Usahana.
