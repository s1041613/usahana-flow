### Preflight

**Preflight picks a route. It does not write code.** Answer the six questions in order. The first question that gets stuck picks the route. Give evidence for each answer, such as a file path and line, a commit, or an issue ID.

1. **Do the spec and the code match?** Compare the spec with the main branch on the remote, not your local copy. Check the base commit, the issues it depends on, and the shared parts it uses. If the project moves features from an old system, also read the old source code (**principle-check-source-first**). If the spec is out of date, update it and go on. If the spec and the old code disagree, and someone must choose, write it down as a question.
2. **Is a fact missing?** Look for things the work needs that are not in the repo or the issue. Some examples are accounts, keys, test data, and settings for an outside service. If something is missing, stop and send questions to Usahana.
3. **Does a business rule have more than one option?** Look in the spec for "A or B", "TBD", "guess", and cases with no result. If you find one, use **BDD first**.
4. **Can a program check each acceptance item?** For each item, decide if a test or a query can say pass or fail. Mark the other items "check by eye". UI items are always "check by eye", at every screen size the project uses. This question does not stop the work.
5. **Is any part a one-way door?** Find out when migrations reach the live database. A migration that only adds things can go on. Put it in its own PR, and merge it before the code that uses it. Some work is a one-way door. It removes or changes data or schema, or it writes to an outside system. If so, stop and send questions to Usahana.
6. **Does the work clash with other open issues?** Compare the files that other open issues will change. Also check if they share a local database. If they overlap, do this issue after the other one. You do not need to ask Usahana about this.

Questions 1 and 6 change how and when you work. They do not change the route. If no question is stuck, use **Poteto build**.

**Reply:** the route, the answer and evidence for each question, and the items marked "check by eye". If the route is "ask Usahana", add the questions.
