---
name: principle-check-source-first
description: "Use when you write a spec, update a spec, or start work. Check each rule in the spec against the real source code. Do not trust docs, issue text, or memory alone."
disable-model-invocation: true
---

# Check Source First

Read the source code before you write the spec. For each rule in the spec, give the `path:line` where the code does it.

**Why:** A spec can say one thing while the code does another. If you build from a wrong spec, the tests pass, but the feature is still wrong. Nobody sees the problem until a user hits it.

Read the real thing, not a summary of it:

- Read the code on the main branch of the remote. Your local copy can be behind, or on another branch.
- If the project moves features from an old system, read the old code the same way. The old-system topic in the project settings says where it is.
- If the docs and the code are different, the code wins. Write down the difference.
- If the spec and the code disagree, and someone must choose, do not choose. Ask Usahana.

If you cannot find a rule in the code, mark it "guess".
