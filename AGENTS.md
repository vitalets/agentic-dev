# Repository guidance

This repository contains reusable instructions for coding agents. Write rules so
agents can apply them consistently and reviewers can judge whether code follows
them.

Follow [Writing Docs](rules/writing-docs.md) when writing, editing, or reviewing
this repository's documentation, including the rules themselves.

## Rule examples

Always prefix example labels with emojis: **❌ Bad**, **✅ Good**, and **✅ Example**.

When adding or editing rules under `rules/`, include examples where they help
readers understand or apply the guidance. Omit examples that merely repeat clear
instructions, scope definitions, or patterns already shown inline. Not every rule
needs an example. Place useful examples directly beneath the relevant rule: use
paired **❌ Bad** and **✅ Good** examples when the contrast clarifies the rule, or
a single **✅ Example** when showing the intended pattern is enough.

Keep `rules/writing-agents-md.md` concise: do not add **❌ Bad**/**✅ Good** or **✅ Example**
blocks to its rules or reusable `AGENTS.md` snippets. Its reference snippets may remain.

**❌ Bad:** Add a workflow bullet to `rules/writing-agents-md.md` followed by
**❌ Bad**/**✅ Good** sample responses.

**✅ Good:** Add only the workflow bullet to `rules/writing-agents-md.md`.

For paired examples, the bad example must demonstrate a violation of the specific
rule. The good example must show the same scenario corrected, with unrelated
details kept the same. Keep examples short and realistic, using code blocks for code conventions
and sample requests or responses for interaction guidance. Explain briefly why
each example violates or satisfies the rule when the distinction is not obvious.

For rules with exceptions or judgment calls, prefer examples that clarify the
boundary. Split independent requirements when doing so makes the guidance easier
to understand.

For example:

- Name functions with verbs that describe their action.

  **❌ Bad:**

  ```ts
  function total(items: Item[]) { ... }
  ```

  **✅ Good:**

  ```ts
  function calculateTotal(items: Item[]) { ... }
  ```

## Review

Before finishing a rule change, check whether examples would clarify any ambiguous
guidance. Verify that included examples add useful information, demonstrate the
rule, and do not contradict other applicable rules. Keep matching guidance in
installation instructions and reusable `AGENTS.md` snippets consistent.
