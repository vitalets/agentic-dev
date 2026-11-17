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

### Writing TypeScript

Write your TypeScript source files to make code easier to read and maintain for both humans and agents.

[Rule source](rules/writing-typescript.md).

To install or update the rule, give your agent this prompt:

```text
Install or update the rule below, following project's rule-storage conventions and preserving local customizations.
- https://raw.githubusercontent.com/vitalets/agentic-dev/main/rules/writing-typescript.md
Add or update a reference in AGENTS.md or CLAUDE.md stating when the rule applies.
```

To review an existing codebase after installing or updating this rule, use this prompt:

```text
Review the existing codebase for compliance with the Writing TypeScript rule and report violations with suggested fixes.
```

### Writing Tests

Write tests that human can read.

[Rule source](rules/writing-tests.md).

To install or update the rule, give your agent this prompt:

```text
Install or update the rule below, following project's rule-storage conventions and preserving local customizations.
- https://raw.githubusercontent.com/vitalets/agentic-dev/main/rules/writing-tests.md
Add or update a reference in AGENTS.md or CLAUDE.md stating when the rule applies.
```

To review an existing codebase after installing or updating this rule, use this prompt:

```text
Review the existing codebase for compliance with the Writing Tests rule and report violations with suggested fixes.
```

### Writing Docs

Write concise and readable documentation for humans.

[Rule source](rules/writing-docs.md).

To install or update the rule, give your agent this prompt:

```text
Install or update the rule below, following project's rule-storage conventions and preserving local customizations.
- https://raw.githubusercontent.com/vitalets/agentic-dev/main/rules/writing-docs.md
Add or update a reference in AGENTS.md or CLAUDE.md stating when the rule applies.
```

To review an existing codebase after installing or updating this rule, use this prompt:

```text
Review the existing codebase for compliance with the Writing Docs rule and report violations with suggested fixes.
```

## Install All Rules

Give your agent this prompt:

```text
Install or update the rules below, following project's rule-storage conventions and preserving local customizations.
- https://raw.githubusercontent.com/vitalets/agentic-dev/main/rules/writing-typescript.md
- https://raw.githubusercontent.com/vitalets/agentic-dev/main/rules/writing-tests.md
- https://raw.githubusercontent.com/vitalets/agentic-dev/main/rules/writing-docs.md
Add or update references in AGENTS.md or CLAUDE.md stating when each rule applies.
```

## Templates

### AGENTS.md Template

[Template source](templates/agents-md.md).

To install or update the template, give your agent this prompt:

```text
Install or update AGENTS.md or CLAUDE.md using applicable sections from the template below, following project's conventions and preserving local customizations.
- https://raw.githubusercontent.com/vitalets/agentic-dev/main/templates/agents-md.md
```

## Contributing

Edit files under `rules/` or `templates/`, following the [repository guidance](AGENTS.md).
No build step is needed.
