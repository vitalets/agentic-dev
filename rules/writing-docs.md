# Writing Docs

Apply this guidance when writing, editing, or reviewing READMEs, guides, API
references, and contributor documentation. Apply the language and accuracy rules
to plans, specs, and design documents too, while following their existing formats.
Code comments follow the project's code-commenting rules.

## Objective

Help the reader accomplish their task with as little reading as necessary.
Simplify the wording without losing technical meaning.

## Reader and structure

- Identify the reader's task and expected knowledge from the request and existing
  documentation. Explain what this reader needs; omit background they can
  reasonably be expected to know. Ask only when missing context would change the
  result.

  **❌ Bad:**

  In a setup guide for developers who already use TypeScript:

  > TypeScript is a programming language that adds types to JavaScript. Install
  > the package with `npm install example-client`.

  **✅ Good:**

  > Install the package with `npm install example-client`.

- Lead with the reader's task or the feature's purpose. Introduce implementation
  details when they help the reader understand or use the feature. Explain the
  underlying problem first when the solution would otherwise be confusing.

  **❌ Bad:**

  > The client uses a subscription registry and a file watcher. Call `watch()` to
  > reload settings when the configuration file changes.

  **✅ Good:**

  > To reload settings when the configuration file changes, call `watch()`.

  The internal registry does not help the reader use this feature.

- Choose structure for the document's purpose. Use headings for distinct tasks or
  lookup needs, and lists or tables for steps and comparisons. Keep related
  explanatory sentences in connected paragraphs. Add introductions, conclusions,
  troubleshooting, or next steps only when they supply useful information.

  **❌ Bad:**

  > ### Overview
  > You can choose where generated files are saved.
  >
  > ### Configuration
  > Set `outputDir` to the destination directory.
  >
  > ### Conclusion
  > You now know how to choose where generated files are saved.

  **✅ Good:**

  > Set `outputDir` to choose where generated files are saved.

  A short explanation needs no section template; a longer guide may need several
  headings to make its tasks easy to find.

## Language

- Use familiar words, concrete subjects, and direct verbs. Keep established
  technical terms when they are precise. Prefer active voice when the actor
  matters, but do not rewrite clear passive sentences mechanically.

  **❌ Bad:**

  > Automatic installation of the extension is performed by the fixture prior to
  > the commencement of the test.

  **✅ Good:**

  > The fixture installs the extension before the test starts.

  Keep “fixture”: it names the exact concept the reader uses.

- Keep conditions close to the behavior they qualify. Split sentences when
  several conditions or actions make them difficult to follow, while preserving
  their relationship.

  **❌ Bad:**

  > The client retries the request, using the configured delay between attempts,
  > if the server returns a temporary error, until the retry limit is reached.

  **✅ Good:**

  > If the server returns a temporary error, the client retries the request until
  > it reaches the retry limit. It waits for the configured delay between attempts.

- Describe features without praise or unsupported claims. Replace promotional
  wording with the feature's purpose, not an invented measurement.

  **❌ Bad:**

  > This powerful, seamless cache makes repeated downloads incredibly fast.

  **✅ Good:**

  > The cache reuses downloaded files for later requests.

## Information and examples

- Remove repeated facts and prose that merely narrates nearby code. Keep prose
  that adds purpose, a prerequisite, timing, a consequence, or a limitation. Do
  not explain obvious substitutions for sample values.

  **❌ Bad:**

  > Set `outputDir` to `./dist`, as shown below. Replace `./dist` with your own
  > output directory. The path is relative to the configuration file.

  ```ts
  export default { outputDir: './dist' };
  ```

  **✅ Good:**

  > The output path is relative to the configuration file.

  ```ts
  export default { outputDir: './dist' };
  ```

  The path's base directory is necessary information that the code cannot convey.

- Keep prerequisites and caveats near the behavior they affect. Retain
  explanations that change how the reader must use an example, even when a method
  name appears self-explanatory.

  **❌ Bad:**

  > Call `start()` and wait for the `ready` event. See Limitations for event timing.

  **✅ Good:**

  > Subscribe to the `ready` event before calling `start()`: the event can fire
  > before `start()` returns.

- Link to authoritative documentation for background details and explain the
  project's additions or differences locally. Keep enough context for the reader
  to complete the task. Give shared setup or configuration a primary home and link
  to it instead of repeating it across pages.

  **❌ Bad:**

  On an API page, when authentication already has a dedicated setup guide:

  > Before calling `upload()`, create an account, generate a token, save it in
  > `EXAMPLE_TOKEN`, and pass it to the client constructor.

  **✅ Good:**

  > `upload()` requires an authenticated client. Follow the
  > [authentication setup](./authentication.md) before using this example.

- Use the smallest example that demonstrates a useful reader task. Keep details
  needed to understand the result; omit unrelated setup and checks. In testing
  guides, demonstrate useful behavior rather than internal identities or counts,
  unless those facts are the subject of the page.

  **❌ Bad:**

  In a guide to saving settings:

  ```ts
  await settings.save({ theme: 'dark' });
  expect(settings.internalCache.size).toBe(1);
  ```

  **✅ Good:**

  ```ts
  await settings.save({ theme: 'dark' });
  expect(await settings.load()).toEqual({ theme: 'dark' });
  ```

- Make complete examples usable with the imports and setup they need. Mark
  partial snippets clearly or rely on context already established on the page.
  Do not repeat full setup around every snippet.

  **❌ Bad:**

  Presented as a complete example, with no earlier setup:

  ```ts
  const client = createClient();
  await client.upload('./report.csv');
  ```

  **✅ Good:**

  > With the client created in the setup above, upload the report:

  ```ts
  await client.upload('./report.csv');
  ```

  This is explicitly a continuation. A standalone version would need the verified
  public import and client configuration instead.

- Use public APIs in examples for users of a package. Internal import paths from
  the package's tests are not automatically suitable for documentation.

  **❌ Bad:**

  ```ts
  import { createClient } from '../src/internal/client';
  ```

  **✅ Good:**

  ```ts
  import { createClient } from 'example-client';
  ```

  This assumes `createClient` is a verified public export of `example-client`.

- Show the filename when the snippet's location matters.

  **✅ Example:**

  > Add the configuration to `example.config.ts` in the project root:

  ```ts
  export default { outputDir: './dist' };
  ```

## Accuracy and editing

- Check technical claims and examples against relevant source, tests, or
  authoritative documentation. Never invent defaults, options, requirements,
  errors, or performance numbers to make prose more specific. Preserve meaningful
  uncertainty and limits when simplifying language.

  **❌ Bad:**

  Editing “The client may retry failed requests” without verifying its behavior:

  > The client retries every failed request three times.

  **✅ Good:**

  > The client may retry failed requests.

  Keep the qualification until evidence supports a more precise statement.

- Keep examples technically correct while simplifying them. Preserve required
  waits, ordering, and setup; brevity does not justify a race or missing
  prerequisite.

  **❌ Bad:**

  ```ts
  await page.getByRole('button', { name: 'Save' }).click();
  expect(await page.getByText('Saved').isVisible()).toBe(true);
  ```

  **✅ Good:**

  ```ts
  await page.getByRole('button', { name: 'Save' }).click();
  await expect(page.getByText('Saved')).toBeVisible();
  ```

  Saving can finish after the click returns, so the assertion must wait for the
  confirmation.

- Keep edits within the requested scope and preserve the document's working
  markup, metadata, and links.

  **✅ Example:**

  For “Simplify the wording in the installation guide,” edit its prose while
  preserving frontmatter, code tabs, and heading anchors. Leave a proposed site
  reorganization outside this wording change.

- When changing headings or paths, update affected links and navigation.

  **✅ Example:**

  When renaming “Setup” to “Installation,” update links targeting the generated
  `#setup` anchor to `#installation`, including links from other pages.

- Use the project's applicable documentation checks. Verify changed code examples
  against their API and behavior too; a successful site build does not prove that
  examples work. Do not add package tests solely for editorial changes.

  **✅ Example:**

  After simplifying prose, run the required documentation checks. If you also
  change a sample's event handling, verify its ordering against the implementation
  and relevant tests, and run a focused behavior check where needed. A build that
  renders the code block cannot detect a missed event.

## Review before finishing

- Review structure, deletion, language, and accuracy in that order. Check that the
  document answers the reader's task, each paragraph adds useful information, the
  wording is plain and connected, and edits preserve technical meaning. For a
  review-only request, report concrete issues with suggested edits.

  **✅ Example:**

  > The paragraph after the configuration example repeats its option values.
  > Replace it with “Paths are relative to the configuration file,” preserving
  > the one detail the example does not show.
