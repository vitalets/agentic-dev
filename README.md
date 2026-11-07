# Agentic Dev

Reusable instructions for coding agents.

## Available rules

- [Writing TypeScript](rules/writing-typescript/writing-typescript.md): Organize TypeScript source files, comments, and code for readability.
- [Writing tests](rules/writing-tests/writing-tests.md): Write readable tests that verify observable behavior.
- [Writing docs](rules/writing-docs/writing-docs.md): Write clear, useful documentation with accurate examples.
- [Writing AGENTS.md](rules/writing-agents-md/writing-agents-md.md): Reusable sections to merge into a project's `AGENTS.md`, including planning guidance.

## Install or update a consumer repository

Give your coding agent this instruction from the consumer repository:

```text
Install or update the applicable rules from https://github.com/vitalets/agentic-dev
using the latest version on main.

Copy the relevant rule files into .agents/rules/ and add or update references to
them in the root AGENTS.md, creating it if needed. Merge relevant snippets from
rules/writing-agents-md/writing-agents-md.md into AGENTS.md rather than copying that file wholesale.
Use explicit loading instructions from those snippets: read the relevant rule
before working on the relevant files, respect its scope, and check the changed
files against it before finishing.

Preserve existing project-specific instructions and reconcile any local rule
customizations with the upstream changes. Avoid duplicate sections or references.
Review the resulting diff and summarize what changed.
```
