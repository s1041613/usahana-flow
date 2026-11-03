### Poteto build

**poteto-mode builds the work. This playbook says what evidence it must give back.** Use it only when nothing in Preflight is stuck.

1. Make a branch with `/worktree`. Add `-C <worktree absolute path>` to every git command.
2. Run `/pstack:poteto-mode`. Give it the issue ID, the Preflight result, and the items marked "check by eye".
3. For each acceptance item that a program can check, write a test. The test fails before the change and passes after it.
4. For each item marked "check by eye", add a screenshot or a video. Make one at each screen size in the project settings.
5. If the change writes data on the server, ask a different model to review it and try to break it.
6. Run `/no-mistakes`. Open the PR only after it passes.
7. In the PR description, list each acceptance item next to its evidence.

**Reply:** the PR link, each acceptance item with its evidence, and the screenshots or videos for Usahana to look at.
