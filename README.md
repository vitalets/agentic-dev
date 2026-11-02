# Agentic Dev

Reusable instructions for coding agents.

## Available rules

- [TypeScript file structure](rules/ts-file-structure/ts-file-structure.md): Organize TypeScript source files, comments, and code for readability.
- [Good tests](rules/good-tests/good-tests.md): Write readable tests that verify observable behavior.
- [AGENTS.md guidance](rules/agents-md/agents-md.md): Reusable sections to merge into a project's `AGENTS.md`, including planning guidance.

## Install or update a consumer repository

Give your coding agent this instruction from the consumer repository:

```text
Install or update the applicable rules from https://github.com/vitalets/agentic-dev
using the latest version on main.

Copy the relevant rule files into .agents/rules/ and add or update references to
them in the root AGENTS.md, creating it if needed. Merge relevant snippets from
rules/agents-md/agents-md.md into AGENTS.md rather than copying that file wholesale.

Preserve existing project-specific instructions and reconcile any local rule
customizations with the upstream changes. Avoid duplicate sections or references.
Review the resulting diff and summarize what changed.
```
