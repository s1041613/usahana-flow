### BDD first

**Agree on the business rules with Usahana before you write code.** Use this playbook only when Preflight question 3 is stuck.

1. List the rules that have more than one option. For each rule, give where it is in the spec. If there is old code, give where it is in the old code too (**principle-check-source-first**).
2. For each rule, write two or three options and the cost of each one. If you can build each option and compare them, run `/pstack:arena` first.
3. Open lavish and go through the rules with Usahana one by one. Do not choose for Usahana.
4. Write each agreed rule as a Given, When, Then scenario. For each scenario, say which test will check it.
5. Write the scenarios and the decisions back into the issue.
6. Run **Preflight** again. When question 3 passes, use **Poteto build**.

**Reply:** the agreed rules, where the scenarios are, and the link to the updated issue.
