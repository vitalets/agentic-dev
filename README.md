# Agentic Dev

Opinionated rules for coding agents.

- [Writing TypeScript](#writing-typescript)
- [Writing Tests](#writing-tests)
- [Writing Docs](#writing-docs)
- [Writing AGENTS.md](#writing-agentsmd)

## Rules

Browse the rules below and install them individually as needed.

> [!TIP]
> By default, all rules install to `.agents/rules`. If your coding agent uses a different
> location, update `RULES_DIR` below and the rule links in `AGENTS.md` to match.

### Writing TypeScript

Organize your TypeScript source files to make code easier to read and maintain.

[Rule source](rules/writing-typescript.md).

Install to `.agents/rules`:

```sh
RULES_DIR=".agents/rules"
mkdir -p "$RULES_DIR"
curl -fsSL https://raw.githubusercontent.com/vitalets/agentic-dev/main/rules/writing-typescript.md \
  -o "$RULES_DIR/writing-typescript.md"
```

Append to `AGENTS.md`:

```markdown
## Writing TypeScript

When creating or editing TypeScript source files, follow
[the Writing TypeScript rule](.agents/rules/writing-typescript.md).
```

### Writing Tests

Write tests that clearly show the behavior being
verified, with simple steps and assertions.

[Rule source](rules/writing-tests.md).

Install to `.agents/rules`:

```sh
RULES_DIR=".agents/rules"
mkdir -p "$RULES_DIR"
curl -fsSL https://raw.githubusercontent.com/vitalets/agentic-dev/main/rules/writing-tests.md \
  -o "$RULES_DIR/writing-tests.md"
```

Append to `AGENTS.md`:

```markdown
## Tests

When creating or editing test files, follow
[the Writing Tests rule](.agents/rules/writing-tests.md).
```

### Writing Docs

Write clear and readable documentation for humans.

[Rule source](rules/writing-docs.md).

Install to `.agents/rules`:

```sh
RULES_DIR=".agents/rules"
mkdir -p "$RULES_DIR"
curl -fsSL https://raw.githubusercontent.com/vitalets/agentic-dev/main/rules/writing-docs.md \
  -o "$RULES_DIR/writing-docs.md"
```

Append to `AGENTS.md`:

```markdown
## Documentation

When writing, editing, or reviewing documentation, follow
[the Writing Docs rule](.agents/rules/writing-docs.md).
```

### Writing AGENTS.md

Write clear `AGENTS.md` instructions for your agents.

[Rule source](rules/writing-agents-md.md).

Install to `.agents/rules`:

```sh
RULES_DIR=".agents/rules"
mkdir -p "$RULES_DIR"
curl -fsSL https://raw.githubusercontent.com/vitalets/agentic-dev/main/rules/writing-agents-md.md \
  -o "$RULES_DIR/writing-agents-md.md"
```

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

## Contributing

Edit files under `rules/`, following [the repository guidance](AGENTS.md).
No build step is needed.
