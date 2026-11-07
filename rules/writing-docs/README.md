# Writing Docs

Rules for clear, useful documentation with accurate examples. See
[the rule](./writing-docs.md).

## Install or update

Run from your project's root directory to download the latest rule into
`.agents/rules/`. Run the same command again to update an existing copy:

```sh
mkdir -p .agents/rules
curl --fail --show-error --silent --location \
  https://raw.githubusercontent.com/vitalets/agentic-dev/main/rules/writing-docs/writing-docs.md \
  --output .agents/rules/writing-docs.md
```

## Reference in AGENTS.md

Add the following to your project's root `AGENTS.md` (create it if needed):

```md
## Documentation

Before writing, editing, or reviewing documentation, read
[the Writing Docs rule](.agents/rules/writing-docs.md) and apply its scope rules.
Before finishing, check the changed documentation against it.
```

Keep project-specific audience assumptions, site structure, API conventions, and
validation commands in the project's own instructions. When replacing an existing
documentation skill, retain those local details and replace duplicated editorial
guidance with a reference to this rule.
