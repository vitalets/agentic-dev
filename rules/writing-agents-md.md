# Writing AGENTS.md

Apply this guidance when writing or reviewing `AGENTS.md`. The sections below
show this repository's preferred patterns for explicit rule loading and planning.

## Workflow

```md
## Workflow

- When the user asks for a plan, do not edit files until they explicitly ask to implement it.
Treat follow-up additions and corrections as updates to the plan, not permission to implement.
```

## Reference rules from this repo

The reference examples assume rules are stored in `.agents/rules/`. Adapt the
paths if your project uses a different layout, and include only references to
rules you have installed.

```md
## Writing TypeScript

When writing, editing, or reviewing TypeScript source files, follow
[the Writing TypeScript rules](.agents/rules/writing-typescript.md).

## Writing Tests

When writing, editing, or reviewing test files, follow
[the Writing Tests rules](.agents/rules/writing-tests.md).

## Writing Docs

When writing, editing, or reviewing documentation, follow
[the Writing Docs rules](.agents/rules/writing-docs.md).
```
