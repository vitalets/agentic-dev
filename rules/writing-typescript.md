# Writing TypeScript

Structure TypeScript source files for top-down reading: a reader should understand what the file does before encountering implementation details.

## Files in Scope

- **Apply to:** TypeScript source files (`.ts` and `.tsx`), such as application modules, components, services, and shared utilities.

- **Ignore:** Configuration files (for example, `vite.config.ts`, `playwright.config.ts`, and `eslint.config.ts`), test files (for example, `*.test.ts`, `*.spec.ts`, and their `.tsx` equivalents), or files written in other languages.

These scope boundaries apply to all rules below.

## Ordering

1. **File purpose** — start the file with a concise block comment describing the module’s overall purpose and boundaries. Do not list its exports or repeat documentation provided on individual exported members.

   **❌ Bad:**

   ```ts
   /**
    * Exports loadSettings and saveSettings.
    */
   ```

   **✅ Good:**

   ```ts
   /**
    * Loads and saves application settings in local storage.
    * Remote synchronization is handled by the sync module.
    */
   ```

2. **Imports** — external dependencies first, then internal modules according to the project's import conventions.

3. **Module-level constants and configuration** — values shared across the file.

4. **Types** — types that define or support the file's API.

5. **Exported/public API** — main functions, classes, or values exposed by the module.

6. **Internal orchestration** — private functions that coordinate the module's main behavior.

7. **Lower-level implementation** — supporting functions ordered roughly by call flow, with callers before callees.

8. **Leaf helpers and utilities** — small implementation details with no meaningful orchestration responsibilities.

## Commenting

- Use multi-line block-form JSDoc for file-level, function, and method documentation,
  including existing comments. Reformat or
  rewrite these comments as needed, preserving their meaning and useful details.

  **❌ Bad:**

  ```ts
  // Persists settings for the next application launch.
  export async function saveSettings(settings: Settings) {
    await storage.set(STORAGE_KEY, settings);
  }
  ```

  **✅ Good:**

  ```ts
  /**
   * Persists settings for the next application launch.
   */
  export async function saveSettings(settings: Settings) {
    await storage.set(STORAGE_KEY, settings);
  }
  ```

- For variable and constant documentation, follow the comment style used in the
  project. Multi-line block-form JSDoc is not required.

- Document all exported functions and module-level constants, except as described below. Focus on their purpose and role, not on implementation.

- When a module centers on one exported class or function, document its purpose in the file-level comment and omit redundant documentation on that declaration. Supporting exports do not change this guidance. Keep declaration comments only when they add distinct, useful details.

  **✅ Example:**

  ```ts
  /**
   * Loads application settings from local storage.
   */

  export type Settings = { theme: string };

  export async function loadSettings() {
    return storage.get('settings');
  }
  ```

- Do not document constructors.

- For types, internal functions and helpers, comment them only when their purpose, behavior, or role in the module is not obvious from the code and naming.

  **✅ Example:**

  ```ts
  function getTotal(prices: number[]) {
    return prices.reduce((sum, price) => sum + price, 0);
  }

  /**
   * Treats legacy empty theme values as the system preference.
   */
  function normalizeTheme(theme: string) {
    return theme || 'system';
  }
  ```

- Do not restate implementation details that are already clear from the code.

  **❌ Bad:**

  ```ts
  /**
   * Calls storage.set with STORAGE_KEY and settings.
   */
  export async function saveSettings(settings: Settings) {
    await storage.set(STORAGE_KEY, settings);
  }
  ```

  **✅ Good:**

  ```ts
  /**
   * Persists settings for the next application launch.
   */
  export async function saveSettings(settings: Settings) {
    await storage.set(STORAGE_KEY, settings);
  }
  ```

- Do not add `@param` or `@returns` tags when TypeScript already expresses them.

  **❌ Bad:**

  ```ts
  /**
   * Formats a price for display.
   * @param amount A number.
   * @returns A string.
   */
  export function formatPrice(amount: number) {
    return amount.toFixed(2);
  }
  ```

  **✅ Good:**

  ```ts
  /**
   * Formats a price for display.
   */
  export function formatPrice(amount: number) {
    return amount.toFixed(2);
  }
  ```

- Where useful, include 1–2 short inline examples, especially for reusable helpers.

- Use simple, direct language. Keep important technical details; simplify the wording, not the content.

  **❌ Bad:**

  ```ts
  /**
   * Facilitates the persistence of preferences via a debouncing
   * mechanism utilizing a 250 ms temporal interval.
   */
  ```

  **✅ Good:**

  ```ts
  /**
   * Saves preferences with 250 ms debounce.
   */
  ```

- Preserve existing comments inside function and method bodies (including
  constructors and callbacks) as written, including their wording, comment syntax,
  and line breaks. Only adjust leading indentation when surrounding code moves.
  Change or remove these comments only when explicitly requested or when a code
  change makes them inaccurate. This preservation rule takes precedence over all
  other commenting guidance, including for declarations nested inside these bodies.

- When suppressing ESLint for a single line, use the `// eslint-disable-next-line ...` form, not `// eslint-disable-line ...`.

## Return Types

- Omit explicit return type annotations on functions and methods unless TypeScript requires them. Rely on inference from the implementation to keep code simpler to review.

  **❌ Bad:**

  ```ts
  function getTotal(prices: number[]): number {
    return prices.reduce((sum, price) => sum + price, 0);
  }
  ```

  **✅ Good:**

  ```ts
  function getTotal(prices: number[]) {
    return prices.reduce((sum, price) => sum + price, 0);
  }
  ```

## Code Quality

- **Align variable names with their types:** Use the type’s domain term in variable names rather than introducing a different term. For example, a value of type `SavedItem` could be named `savedItem`. Add role-specific qualifiers when needed to distinguish values, such as `sourceItem` and `targetItem`.

- **Prefer explicit function and method names:** Name functions and methods with verbs that describe their action. For example, prefer `getTotal` over `total`. Where practical, use specific verbs such as `find`, `save`, `remove`, or `create` rather than broad terms like `resolve`, `prepare`, or `process`. Make meaningful side effects visible, especially when a function or method both looks up and creates data. For example, prefer `findOrCreateStoredGroup` over `resolveLocalGroup`, and `saveGroupFromMatchingBindingHint` over `recognizeGroup`. General verbs are still reasonable when they accurately describe the function or method’s role, such as an event handler.

  **❌ Bad:**

  ```ts
  async function resolveLocalGroup(name: string) {
    return (await findStoredGroup(name)) ?? createStoredGroup(name);
  }
  ```

  **✅ Good:**

  ```ts
  async function findOrCreateStoredGroup(name: string) {
    return (await findStoredGroup(name)) ?? createStoredGroup(name);
  }
  ```

  `findOrCreateStoredGroup` makes the possible creation visible; an event handler name such as `handleGroupChange` can still accurately describe a broader role.

- **Simple control flow:** Keep branches and conditions easy to follow. Use optional chaining when it simplifies access.

  **❌ Bad:**

  ```ts
  const theme = settings && settings.appearance
    ? settings.appearance.theme
    : undefined;
  ```

  **✅ Good:**

  ```ts
  const theme = settings?.appearance?.theme;
  ```

- **Shallow nesting:** Prefer guard clauses and early returns. Extract meaningful operations when nested blocks obscure the main flow.

  **❌ Bad:**

  ```ts
  async function saveIfChanged(settings: Settings | undefined, changed: boolean) {
    if (settings) {
      if (changed) {
        await saveSettings(settings);
      }
    }
  }
  ```

  **✅ Good:**

  ```ts
  async function saveIfChanged(settings: Settings | undefined, changed: boolean) {
    if (!settings || !changed) return;

    await saveSettings(settings);
  }
  ```

- **Readable callbacks:** Avoid deeply nested callbacks. Use named helpers or `async`/`await` where appropriate without changing execution behavior.

  **❌ Bad:**

  ```ts
  function refreshSettings() {
    return loadSettings().then(settings => {
      return saveSettings(settings).then(() => {
        renderSettings(settings);
      });
    });
  }
  ```

  **✅ Good:**

  ```ts
  async function refreshSettings() {
    const settings = await loadSettings();
    await saveSettings(settings);
    renderSettings(settings);
  }
  ```

- **Small parameter lists:** Keep inputs easy to understand at call sites. Group related inputs into a named object when that clarifies their meaning.

  **❌ Bad:**

  ```ts
  function createPanel(width: number, height: number, title: string) {
    return { width, height, title };
  }

  createPanel(320, 200, 'Settings');
  ```

  **✅ Good:**

  ```ts
  type PanelOptions = { width: number; height: number; title: string };

  function createPanel({ width, height, title }: PanelOptions) {
    return { width, height, title };
  }

  createPanel({ width: 320, height: 200, title: 'Settings' });
  ```

- **Focused functions:** Keep functions, methods, and callbacks concise and centered on a clear responsibility.

  **❌ Bad:**

  ```ts
  async function saveSettings(settings: Settings) {
    await storage.set(STORAGE_KEY, settings);
    renderSettings(settings);
  }
  ```

  **✅ Good:**

  ```ts
  async function saveSettings(settings: Settings) {
    await storage.set(STORAGE_KEY, settings);
  }

  async function saveAndRenderSettings(settings: Settings) {
    await saveSettings(settings);
    renderSettings(settings);
  }
  ```

- **Separate orchestration from implementation:** Functions and methods that coordinate a workflow should read as a sequence of meaningful steps. Extract the implementation details of those steps into named helpers, even when short or used only once. Keep straightforward assignments and control flow inline. Apply this when writing new code as well as refactoring.

  **❌ Bad:**

  ```ts
  async function refreshSettings() {
    const settings = await loadSettings();
    document.documentElement.dataset.theme = settings.theme;
    document.title = settings.title;
  }
  ```

  **✅ Good:**

  ```ts
  async function refreshSettings() {
    const settings = await loadSettings();
    applySettings(settings);
  }

  function applySettings(settings: Settings) {
    document.documentElement.dataset.theme = settings.theme;
    document.title = settings.title;
  }
  ```

  Keep the straightforward `settings` assignment inline; name the UI update step to explain its role.

- **Readable lines:** Break long expressions at natural boundaries. Keep URLs intact and preserve existing body comments according to the commenting rules.

  **❌ Bad:**

  ```ts
  const visibleItems = items.filter(item => item.enabled && item.category === selectedCategory).map(item => item.label);
  ```

  **✅ Good:**

  ```ts
  const visibleItems = items
    .filter(item => item.enabled)
    .filter(item => item.category === selectedCategory)
    .map(item => item.label);
  ```

- **Focused files:** Keep each module centered on a cohesive purpose. Separate distinct responsibilities when a file becomes difficult to navigate.

- **Meaningful refactoring:** Preserve useful comments and whitespace. Avoid compressing code solely to make functions or files shorter. Extract helpers to communicate intent and keep a consistent level of abstraction, not merely to shorten code. Avoid helpers whose names add no meaning beyond the expressions they wrap.

  **❌ Bad:**

  ```ts
  function findEnabledItems(items: Item[]) {
    return items.filter(isEnabled);
  }

  function isEnabled(item: Item) {
    return item.enabled;
  }
  ```

  **✅ Good:**

  ```ts
  function findEnabledItems(items: Item[]) {
    return items.filter(item => item.enabled);
  }
  ```

  The helper only repeats the property name; it adds no useful abstraction.
