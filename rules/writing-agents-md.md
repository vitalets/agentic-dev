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

Before creating or editing TypeScript source files, read
[the Writing TypeScript rule](.agents/rules/writing-typescript.md) and apply
its scope rules. Before finishing, check the changed code against it.
```

### Tests

**Example:**

```md
## Tests

Before creating or editing test files, read and follow
[the Writing Tests rule](.agents/rules/writing-tests.md).
Before finishing, check the changed tests against it.
```

### Documentation

**Example:**

```md
## Documentation

Before writing, editing, or reviewing documentation, read
[the Writing Docs rule](.agents/rules/writing-docs.md) and apply its scope rules.
Before finishing, check the changed documentation against it.
```

### Planning

**Example:**

```md
## Planning

When the user asks for a plan, do not edit files until they explicitly ask to implement it.
Treat follow-up additions and corrections as updates to the plan, not permission to implement.
```
