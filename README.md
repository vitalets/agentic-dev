# Agentic Dev

Opinionated rules for coding agents for writing readable and maintainable code, tests, and documentation.

## Rules

- [Writing TypeScript](#writing-typescript)
- [Writing Tests](#writing-tests)
- [Writing Docs](#writing-docs)
- [Writing AGENTS.md](#writing-agentsmd)

### Writing TypeScript

Organize your TypeScript source files to make code easier to read and maintain.

Install to `.agents/rules`:

```sh
mkdir -p .agents/rules
curl -fsSL https://raw.githubusercontent.com/vitalets/agentic-dev/main/rules/writing-typescript.md \
  -o .agents/rules/writing-typescript.md
```

> [!TIP]
> Check your coding agent’s documentation for its supported rules location and
> adjust the paths as needed.

Append to `AGENTS.md`:

```markdown
## Writing TypeScript

When creating or editing TypeScript source files, follow
[the Writing TypeScript rule](.agents/rules/writing-typescript.md).
```

### Writing Tests

Write tests that clearly show the behavior being
verified, with simple steps and assertions.

Install to `.agents/rules`:

```sh
mkdir -p .agents/rules
curl -fsSL https://raw.githubusercontent.com/vitalets/agentic-dev/main/rules/writing-tests.md \
  -o .agents/rules/writing-tests.md
```

> [!TIP]
> Check your coding agent’s documentation for its supported rules location and
> adjust the paths as needed.

Append to `AGENTS.md`:

```markdown
## Tests

When creating or editing test files, follow
[the Writing Tests rule](.agents/rules/writing-tests.md).
```

### Writing Docs

Write clear and readable documentation for humans.

Install to `.agents/rules`:

```sh
mkdir -p .agents/rules
curl -fsSL https://raw.githubusercontent.com/vitalets/agentic-dev/main/rules/writing-docs.md \
  -o .agents/rules/writing-docs.md
```

> [!TIP]
> Check your coding agent’s documentation for its supported rules location and
> adjust the paths as needed.

Append to `AGENTS.md`:

```markdown
## Documentation

When writing, editing, or reviewing documentation, follow
[the Writing Docs rule](.agents/rules/writing-docs.md).
```

### Writing AGENTS.md

Write good `AGENTS.md` for you agents.

Install to `.agents/rules`:

```sh
mkdir -p .agents/rules
curl -fsSL https://raw.githubusercontent.com/vitalets/agentic-dev/main/rules/writing-agents-md.md \
  -o .agents/rules/writing-agents-md.md
```

> [!TIP]
> Check your coding agent’s documentation for its supported rules location and
> adjust the paths as needed.

## Contributing

Edit files under `rules/`, following [the repository guidance](AGENTS.md).
No build step is needed.
