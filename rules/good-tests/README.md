# Good Tests

Rules for writing readable, reliable tests. See [the rule](./good-tests.md).

## Install or update

Run from your project's root directory to download the latest rule into `.agents/rules/`. Run the same command again to update an existing copy:

```sh
mkdir -p .agents/rules
curl --fail --show-error --silent --location \
  https://raw.githubusercontent.com/vitalets/agentic-dev/main/rules/good-tests/good-tests.md \
  --output .agents/rules/good-tests.md
```

## Reference in AGENTS.md

Add the following to your project's root `AGENTS.md` (create it if needed):

```md
## Tests

Before creating or editing test files, read and follow
[the good tests rule](.agents/rules/good-tests.md).
Before finishing, check the changed tests against it.
```
