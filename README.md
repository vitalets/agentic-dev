# Agentic Dev

Reusable rules for coding agents.

- [Writing TypeScript](#writing-typescript)
- [Writing Tests](#writing-tests)
- [Writing Docs](#writing-docs)
- [Writing AGENTS.md](#writing-agentsmd)

## Rules

Run the commands for the rules you want from your project's root. Each rule has
one command to download it and another to append its reference to `AGENTS.md`.
Run the append command only once per rule; to update, rerun just the download
command (which replaces local edits to the downloaded file).

### Writing TypeScript

Organize TypeScript source files, comments, and code for readability.

Download:

```sh
mkdir -p .agents/rules
curl -fsSL https://raw.githubusercontent.com/vitalets/agentic-dev/main/rules/writing-typescript.md \
  -o .agents/rules/writing-typescript.md
```

Append to `AGENTS.md`:

```sh
cat >> AGENTS.md <<'EOF'

## Source file structure

Before creating or editing TypeScript source files, read
[the Writing TypeScript rule](.agents/rules/writing-typescript.md) and apply
its scope rules. Before finishing, check the changed code against it.
EOF
```

### Writing Tests

Write readable tests that verify observable behavior.

Download:

```sh
mkdir -p .agents/rules
curl -fsSL https://raw.githubusercontent.com/vitalets/agentic-dev/main/rules/writing-tests.md \
  -o .agents/rules/writing-tests.md
```

Append to `AGENTS.md`:

```sh
cat >> AGENTS.md <<'EOF'

## Tests

Before creating or editing test files, read and follow
[the Writing Tests rule](.agents/rules/writing-tests.md).
Before finishing, check the changed tests against it.
EOF
```

### Writing Docs

Write clear, useful documentation with accurate examples.

Download:

```sh
mkdir -p .agents/rules
curl -fsSL https://raw.githubusercontent.com/vitalets/agentic-dev/main/rules/writing-docs.md \
  -o .agents/rules/writing-docs.md
```

Append to `AGENTS.md`:

```sh
cat >> AGENTS.md <<'EOF'

## Documentation

Before writing, editing, or reviewing documentation, read
[the Writing Docs rule](.agents/rules/writing-docs.md) and apply its scope rules.
Before finishing, check the changed documentation against it.
EOF
```

### Writing AGENTS.md

Opinionated examples of explicit rule references and planning guidance for agent instructions.

Download:

```sh
mkdir -p .agents/rules
curl -fsSL https://raw.githubusercontent.com/vitalets/agentic-dev/main/rules/writing-agents-md.md \
  -o .agents/rules/writing-agents-md.md
```

Append to `AGENTS.md`:

```sh
cat >> AGENTS.md <<'EOF'

## Agent instructions

Before writing or reviewing `AGENTS.md`, read and follow
[the Writing AGENTS.md rule](.agents/rules/writing-agents-md.md).
Before finishing, check the changed instructions against it.
EOF
```

## Contributing

Edit files under `rules/`, following [the repository guidance](AGENTS.md).
No build step is needed.
