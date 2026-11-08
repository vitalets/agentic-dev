# Writing AGENTS.md

Apply this guidance when writing or reviewing `AGENTS.md`. The sections below
show this repository's preferred patterns for explicit rule loading and planning.

The reference examples assume rules are stored in `.agents/rules/`. Adapt the
paths if your project uses a different layout, and include only references to
rules you have installed.

### Source file structure

**Example:**

```md
## Source file structure

When creating or editing TypeScript source files, follow
[the Writing TypeScript rule](.agents/rules/writing-typescript.md).
```

### Tests

**Example:**

```md
## Tests

When creating or editing test files, follow
[the Writing Tests rule](.agents/rules/writing-tests.md).
```

### Documentation

**Example:**

```md
## Documentation

When writing, editing, or reviewing documentation, follow
[the Writing Docs rule](.agents/rules/writing-docs.md).
```

### Planning

**Example:**

```md
## Planning

When the user asks for a plan, do not edit files until they explicitly ask to implement it.
Treat follow-up additions and corrections as updates to the plan, not permission to implement.
```
