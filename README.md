# Agentic Dev

Opinionated rules that help coding agents write readable and maintainable code, tests, and documentation.

- [Writing TypeScript](#writing-typescript)
- [Writing Tests](#writing-tests)
- [Writing Docs](#writing-docs)
- [Writing AGENTS.md](#writing-agentsmd)

## Install All Rules

Run this script from your project's root to install or update all rules:

```sh
RULES_DIR=".agents/rules"

mkdir -p "$RULES_DIR"
for rule in \
  writing-typescript \
  writing-tests \
  writing-docs \
  writing-agents-md
do
  curl -fsSL "https://raw.githubusercontent.com/vitalets/agentic-dev/main/rules/$rule.md" \
    -o "$RULES_DIR/$rule.md" || break
done
```

## Rules

Browse the rules below and install them individually as needed.

### Writing TypeScript

Organize your TypeScript source files to make code easier to read and maintain.

Install to `.agents/rules`:

```sh
RULES_DIR=".agents/rules"
mkdir -p "$RULES_DIR"
curl -fsSL https://raw.githubusercontent.com/vitalets/agentic-dev/main/rules/writing-typescript.md \
  -o "$RULES_DIR/writing-typescript.md"
```

> [!TIP]
> Check your coding agent’s documentation for its supported rules location.
> To use a different directory, change `RULES_DIR` above and update any rule
> links in `AGENTS.md` to match.

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
RULES_DIR=".agents/rules"
mkdir -p "$RULES_DIR"
curl -fsSL https://raw.githubusercontent.com/vitalets/agentic-dev/main/rules/writing-tests.md \
  -o "$RULES_DIR/writing-tests.md"
```

> [!TIP]
> Check your coding agent’s documentation for its supported rules location.
> To use a different directory, change `RULES_DIR` above and update any rule
> links in `AGENTS.md` to match.

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
RULES_DIR=".agents/rules"
mkdir -p "$RULES_DIR"
curl -fsSL https://raw.githubusercontent.com/vitalets/agentic-dev/main/rules/writing-docs.md \
  -o "$RULES_DIR/writing-docs.md"
```

> [!TIP]
> Check your coding agent’s documentation for its supported rules location.
> To use a different directory, change `RULES_DIR` above and update any rule
> links in `AGENTS.md` to match.

Append to `AGENTS.md`:

```markdown
## Documentation

When writing, editing, or reviewing documentation, follow
[the Writing Docs rule](.agents/rules/writing-docs.md).
```

### Writing AGENTS.md

Write clear `AGENTS.md` instructions for your agents.

Install to `.agents/rules`:

```sh
RULES_DIR=".agents/rules"
mkdir -p "$RULES_DIR"
curl -fsSL https://raw.githubusercontent.com/vitalets/agentic-dev/main/rules/writing-agents-md.md \
  -o "$RULES_DIR/writing-agents-md.md"
```

> [!TIP]
> Check your coding agent’s documentation for its supported rules location.
> To use a different directory, change `RULES_DIR` above and update any rule
> links in `AGENTS.md` to match.

## Contributing

Edit files under `rules/`, following [the repository guidance](AGENTS.md).
No build step is needed.
