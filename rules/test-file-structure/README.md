# Test File Structure

Rules for structuring test files. See [the rule](./test-file-structure.md).

## Install or update

Run from your project's root directory to download the latest rule into `.agents/rules/`. Run the same command again to update an existing copy:

```sh
mkdir -p .agents/rules
curl --fail --show-error --silent --location \
  https://raw.githubusercontent.com/vitalets/agentic-dev/main/rules/test-file-structure/test-file-structure.md \
  --output .agents/rules/test-file-structure.md
```

## Reference in AGENTS.md

Add the following to your project's root `AGENTS.md` (create it if needed):

```md
## Tests

When creating or editing test files, read and follow
[the test file structure rule](.agents/rules/test-file-structure.md).
```
