# Agentic Dev

Opinionated rules and templates for coding agents.

- **Rules**
  - [Writing TypeScript](#writing-typescript)
  - [Writing Tests](#writing-tests)
  - [Writing Docs](#writing-docs)
  - [Install all rules](#install-all-rules)
- **Templates**  
  - [AGENTS.md](#agentsmd-template)

## Rules

Browse the rules below and install them individually as needed.

> [!TIP]
> By default, all rules are installed to `.agents/rules`. If your coding agent uses a different
> location, update `RULES_DIR` variable in the snippets.

### Writing TypeScript

Write your TypeScript source files to make code easier to read and maintain for both humans and agents.

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
the [Writing TypeScript rule](.agents/rules/writing-typescript.md).
```

### Writing Tests

Write tests that human can read.

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
## Writing Tests

When creating or editing test files, follow
the [Writing Tests rule](.agents/rules/writing-tests.md).
```

### Writing Docs

Write concise and readable documentation for humans.

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
the [Writing Docs rule](.agents/rules/writing-docs.md).
```

## Install All Rules

Run this script from your project's root to install or update all rules:

```sh
RULES_DIR=".agents/rules"

mkdir -p "$RULES_DIR"
for rule in \
  writing-typescript \
  writing-tests \
  writing-docs
do
  curl -fsSL "https://raw.githubusercontent.com/vitalets/agentic-dev/main/rules/$rule.md" \
    -o "$RULES_DIR/$rule.md" || break
done
```

## Templates

### AGENTS.md Template

Pick applicable bullets from the [AGENTS.md template](templates/agents-md.md).

## Contributing

Edit files under `rules/` or `templates/`, following the [repository guidance](AGENTS.md).
No build step is needed.
