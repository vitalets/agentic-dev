# Test File Structure

Tests should make it clear what is being tested as the reader reads them, without requiring a dive into implementation details. All rules below support this guiding principle of readability.

- Avoid loops in tests unless explicitly requested by the user.
- When test actions can be expressed through a meaningfully named helper, prefer extracting them over keeping their details in the test body. Hide irrelevant complexity, but pass values important to the test as explicit parameters; do not silently set them inside the helper. Place helpers used only in one test file at the bottom of that file; place helpers shared across test files in a separate helpers file.
- When asserting thrown errors, use a regular expression to match keywords that convey the error's meaning, rather than the entire message.
- Test observable behavior at the highest practical level without slowing down the test suite. Avoid assertions on implementation details that are likely to change or difficult to understand.
- When test data values are arbitrary, prefer using neutral placeholders such as `foo`, `bar`, `baz` for strings, or 1, 2, 3 for numbers. Avoid values that describe the test scenario or imply meaning readers need to interpret; keep cognitive load minimal.
