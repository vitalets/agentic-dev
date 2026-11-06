# Repository guidance

This repository contains reusable instructions for coding agents. Write rules so
agents can apply them consistently and reviewers can judge whether code follows
them.

## Rule examples

Each rule bullet or numbered rule under `rules/` must include paired examples
labeled **Bad** and **Good**, directly beneath that rule. Apply this requirement
when adding or editing rules. Navigation lists and installation steps do not need
these examples.

The bad example must demonstrate a violation of the specific rule. The good
example must show the same scenario corrected, with unrelated details kept the
same. Keep examples short and realistic, using code blocks for code conventions
and sample requests or responses for interaction guidance. Explain briefly why
each example violates or satisfies the rule when the distinction is not obvious.

For rules with exceptions or judgment calls, choose examples that clarify the
boundary. Split a bullet containing independent requirements when one example
pair cannot demonstrate them clearly.

For example:

- Name functions with verbs that describe their action.

  **Bad:**

  ```ts
  function total(items: Item[]) { ... }
  ```

  **Good:**

  ```ts
  function calculateTotal(items: Item[]) { ... }
  ```

## Review

Before finishing a rule change, verify that every added or edited rule has both
examples, that the examples demonstrate the stated distinction, and that they
do not contradict other applicable rules. Keep matching guidance in installation
instructions and reusable `AGENTS.md` snippets consistent.
