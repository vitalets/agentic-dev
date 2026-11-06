# Writing TypeScript

A rule for organizing TypeScript source files for top-down reading, documenting their public API, and guiding code quality. See [the rule](./writing-typescript.md) for the full instructions.

## Install

Run from your project's root directory to download the rule into `.agents/rules/`:

```sh
mkdir -p .agents/rules
curl --fail --show-error --silent --location \
  https://raw.githubusercontent.com/vitalets/agentic-dev/main/rules/writing-typescript/writing-typescript.md \
  --output .agents/rules/writing-typescript.md
```

## Reference in AGENTS.md

Add the following to your project's root `AGENTS.md` (create it if needed):

```md
## Source file structure

Before creating or editing TypeScript source files, read
[the Writing TypeScript rule](.agents/rules/writing-typescript.md) and apply
its scope rules. Before finishing, check the changed code against it.
```
