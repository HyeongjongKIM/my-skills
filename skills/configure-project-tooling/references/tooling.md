# TypeScript tooling preferences

These are target-project examples, not files to execute here. Follow [adoption](adoption.md) before selecting packages or merging configuration. Required means necessary for a selected integration; the tool choices are default preferences unless stated otherwise. Verify each API against the selected release's official documentation.

## TypeScript

Target file: `tsconfig.json` in the relevant package. Merge into existing `compilerOptions`; retain framework extends, references, paths and generation requirements. Required package: local `typescript`, plus runtime-specific declarations when needed.

```json
{
  "compilerOptions": {
    "strict": true,
    "noEmit": true
  }
}
```

Strict checking is the default preference. `noEmit` applies when a bundler/framework produces output or the config is checking-only; compiler-emitted libraries need a deliberate build config instead. Select module, moduleResolution, target, lib and JSX settings from the actual runtime/build tool, not a universal browser preset. Define include/exclude and project references for source, tests and configuration files deliberately. Typecheck and build are separate commands. See the [TSConfig reference](https://www.typescriptlang.org/tsconfig/).

## ESLint

Default: Flat Config, TypeScript recommended rules and the explicit checks below. Required local development packages for this recipe: `eslint`, `@eslint/js`, `typescript`, `typescript-eslint` and `eslint-config-prettier`. Add `globals` only when using its runtime-specific sets.

Target file: root `eslint.config.mjs` (or the target's recognized Flat Config file). Merge the fragments in order with existing presets and keep checks already configured for other file types. This example requires an ESLint release supporting `defineConfig` and scoped `extends` from `eslint/config`. For an existing supported release with a different composition API, follow its documented equivalent and keep the same file scopes. The TypeScript recommended preset includes TypeScript-specific rules such as `no-require-imports`, so scope it to TypeScript files to avoid imposing it on existing JavaScript and CommonJS tooling. [ESLint Flat Config](https://eslint.org/docs/latest/use/configure/configuration-files#extending-configurations), [typescript-eslint setup](https://typescript-eslint.io/getting-started/), [no-require-imports](https://typescript-eslint.io/rules/no-require-imports/).

```js
import js from '@eslint/js';
import { defineConfig } from 'eslint/config';
import ts from 'typescript-eslint';
import formatting from 'eslint-config-prettier';
import { dirname } from 'node:path';
import { fileURLToPath } from 'node:url';

const typescriptFiles = ['**/*.{ts,tsx,mts,cts}'];

export default defineConfig([
  {
    ignores: [
      '**/node_modules/**',
      '**/dist/**',
      '**/coverage/**',
      '**/.husky/_/**',
    ],
  },
  {
    files: ['**/*.{js,cjs,mjs,jsx,ts,tsx,mts,cts}'],
    extends: [js.configs.recommended],
    rules: {
      eqeqeq: 'error',
      'no-duplicate-imports': ['error', { allowSeparateTypeImports: true }],
    },
  },
  {
    files: ['**/*.jsx'],
    languageOptions: { parser: ts.parser },
  },
  {
    files: typescriptFiles,
    extends: [ts.configs.recommended],
  },
  {
    files: typescriptFiles,
    languageOptions: {
      parserOptions: {
        projectService: true,
        tsconfigRootDir: dirname(fileURLToPath(import.meta.url)),
      },
    },
    rules: {
      '@typescript-eslint/consistent-type-imports': [
        'error',
        { prefer: 'type-imports', fixStyle: 'separate-type-imports' },
      ],
      '@typescript-eslint/consistent-type-exports': 'error',
      '@typescript-eslint/no-floating-promises': 'error',
      '@typescript-eslint/no-misused-promises': 'error',
      '@typescript-eslint/await-thenable': 'error',
      '@typescript-eslint/only-throw-error': 'error',
      '@typescript-eslint/no-unnecessary-type-assertion': 'error',
      '@typescript-eslint/no-unnecessary-condition': 'warn',
      '@typescript-eslint/no-deprecated': 'warn',
      '@typescript-eslint/switch-exhaustiveness-check': 'error',
    },
  },
  // Insert selected framework presets and scoped overrides before formatting.
  formatting,
]);
```

The ignore-only object supplies global ignores. Merge actual generated output paths and keep authored files in scope. The JSX entry retains JSX-aware parsing without applying the TypeScript rules to JavaScript. Keep an existing compatible JSX parser when present. Scope Node/browser globals to real execution environments, including configuration files and tests. In mixed projects, verify a representative JavaScript or CommonJS config and a TypeScript file in the same lint run, plus JSX/TSX when used. [TypeScript parser JSX support](https://typescript-eslint.io/packages/parser/#jsx), [ESLint language options](https://eslint.org/docs/latest/use/configure/language-options).

| Rule / group | Purpose | Default severity |
| --- | --- | --- |
| eqeqeq | Avoid coercive equality | error |
| consistent-type-imports / consistent-type-exports | Explicit type-only module boundaries | error |
| no-duplicate-imports | Merge duplicates while allowing separate type/value declarations | error |
| no-floating-promises / no-misused-promises | Handle asynchronous results and callback contracts | error |
| await-thenable | Await valid thenables | error |
| only-throw-error | Throw Error values | error |
| no-unnecessary-type-assertion | Remove assertions that do not change types | error |
| no-unnecessary-condition | Identify redundant conditions | warn |
| no-deprecated | Identify deprecated API use | warn |
| switch-exhaustiveness-check | Check union/enum switch coverage | error |

These are explicit default severities, not permission to lower an existing project's checks. Resolve intentional deviations with behavioral reasons. Review the [current rule documentation](https://typescript-eslint.io/rules/) when names or options change. Use the supported [core duplicate-import option](https://eslint.org/docs/latest/rules/no-duplicate-imports); do not revive a removed TypeScript duplicate-import rule or force an incompatible ESLint release. Separate `import type` and value imports are intentional.

### Typed-lint coverage

[Project service](https://typescript-eslint.io/getting-started/typed-linting/) supplies type information from each file's nearest tsconfig. `tsconfigRootDir` is the directory of the target config; adapt it if configuration lives elsewhere. Cover all typed-linted source and test files in real tsconfig projects, including workspace packages and referenced projects. Verify the selected service's discovery behavior; a root solution config alone does not prove coverage.

Out-of-project tool/config files require a deliberate choice: include them in an appropriate real project, use a narrowly bounded `allowDefaultProject` when suitable, or exclude those specific files from the type-aware entry while retaining the base TypeScript checks. Do not use broad default-project globs, disable typed rules on application files or blanket-ignore errors to make lint pass. Ordinary TS coverage does not prove typed lint inside framework templates. [Typed-lint troubleshooting](https://typescript-eslint.io/troubleshooting/typed-linting/).

Keep [eslint-config-prettier](https://github.com/prettier/eslint-config-prettier) after presets/overrides that may enable conflicting formatting rules. It disables conflicts; it does not run Prettier. Do not run Prettier as an ESLint rule.

### Source filename linting

Default preference: enforce kebab-case source filenames through `unicorn/filename-case`. Additional required local development package: `eslint-plugin-unicorn`, with a supported ESLint/runtime combination and the existing language parsers. Follow the selected release's [plugin usage](https://github.com/sindresorhus/eslint-plugin-unicorn) and [rule options](https://github.com/sindresorhus/eslint-plugin-unicorn/blob/main/docs/rules/filename-case.md). Check its ESM, Node and ESLint requirements at adoption; do not force an incompatible installation or upgrade unrelated tools to match an example. Report a blocked filename integration and continue independent setup when no supported combination is available.

Target file: existing `eslint.config.mjs`. Merge the import and spread `filenameEntries` into the existing exported array after relevant framework presets and before final formatting conflict disabling. Keep existing parser settings and register the plugin only once per matching scope. Enable this rule individually; do not add the entire Unicorn recommended preset solely for filenames.

```js
import unicorn from 'eslint-plugin-unicorn';

const filenameEntries = [
  {
    files: ['**/*.{js,cjs,mjs,jsx,ts,cts,mts,tsx}'],
    plugins: { unicorn },
    rules: {
      'unicorn/filename-case': [
        'error',
        {
          case: 'kebabCase',
          checkDirectories: false,
          multipleFileExtensions: true,
        },
      ],
    },
  },
];
```

This checks linted source filenames, including React TSX and TypeScript helpers. It leaves directories and code identifiers unchanged and permits compound suffixes such as `.test.tsx`; suffix segments are not checked for kebab-case. Markdown, document templates and unlinted files are outside this scope. For Astro, extend this entries object's files list with `**/*.astro` only after applying the [Astro parser layer](astro.md); a glob alone does not supply a parser. Check physical components rather than processor-generated virtual scripts.

Keep generated/dependency paths in existing global ignores. Preserve framework-required names and route parameters; use narrowly scoped overrides of this filename rule or its documented anchored ignore patterns for genuine exceptions, while retaining other lint checks. Do not exempt an entire source tree to conceal ordinary filename violations. Scope adoption deliberately in existing projects rather than bulk-renaming unrelated files. For authorized renames, update affected imports, links and route references.

Verify in the target that a kebab-case filename passes and a PascalCase/camelCase filename fails under the same parser and lint command. Include TSX and physical `.astro` files when used, a compound-suffix filename and actual route exceptions. Confirm these files are included in normal lint/CI scope. Treat this as diagnostics, not an automatic rename operation; review references when changing paths. Record exclusions and checks not run honestly.

### Tailwind canonical classes

When Tailwind CSS is present, follow [Tailwind tooling](tailwind.md) for `better-tailwindcss/enforce-canonical-classes`, the ESLint counterpart to `tailwindcss(suggestCanonicalClasses)`. Enable only with a supported version/parser combination and the actual stylesheet; Prettier class sorting alone does not enforce canonical names. Follow applicable target instructions for styling preferences.

## Prettier

Target file: `.prettierrc.json`, or merge into the target's single existing supported Prettier config. Required local development package: `prettier`.

```json
{
  "singleQuote": true,
  "trailingComma": "all"
}
```

These are the only shared style options. Do not add arbitrary permanent choices for semicolons, line width, tabs or other unspecified styles. Preserve deliberate existing options unless changing them is in scope. Run formatting separately from lint; avoid unrelated whole-project formatting during adoption. See [configuration](https://prettier.io/docs/configuration).

Target file: `.prettierignore`. Merge applicable patterns; remove lockfile names the target does not use and add its actual generated paths.

```gitignore
**/node_modules/**
**/dist/**
**/coverage/**
**/.husky/_/**
**/package-lock.json
**/npm-shrinkwrap.json
**/pnpm-lock.yaml
**/yarn.lock
**/bun.lock
**/bun.lockb
```

[Prettier ignores](https://prettier.io/docs/ignore) are separate from ESLint ignores. Astro formatting requires its optional layer. Add `prettier-plugin-tailwindcss` only when Tailwind is used; follow its [documented integration and plugin order](https://github.com/tailwindlabs/prettier-plugin-tailwindcss), including any required stylesheet/config path. Do not install either plugin for plain TypeScript.

## VS Code

Optional when VS Code is used; default behavior is project-local TypeScript, ESLint and Prettier, format on save and ESLint fixes on explicit saves. Required local packages are those selected above. Merge settings objects and extension arrays; preserve existing workspace-specific overrides.

Target file: `.vscode/settings.json` (or the existing workspace settings location). Merge supported keys; check the installed editor/extension schema first.

```json
{
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": "explicit"
  },
  "prettier.requireConfig": true,
  "[javascript]": { "editor.defaultFormatter": "esbenp.prettier-vscode" },
  "[javascriptreact]": { "editor.defaultFormatter": "esbenp.prettier-vscode" },
  "[typescript]": { "editor.defaultFormatter": "esbenp.prettier-vscode" },
  "[typescriptreact]": { "editor.defaultFormatter": "esbenp.prettier-vscode" },
  "[json]": { "editor.defaultFormatter": "esbenp.prettier-vscode" },
  "[jsonc]": { "editor.defaultFormatter": "esbenp.prettier-vscode" },
  "[markdown]": { "editor.defaultFormatter": "esbenp.prettier-vscode" }
}
```

For local TypeScript, use the installed VS Code release's supported SDK setting and the “TypeScript: Select TypeScript Version” command to select the workspace version. The [current source schema](https://github.com/microsoft/vscode/blob/main/extensions/typescript-language-features/package.json) and the target editor's release may differ. Where supported, merge `"js/ts.tsdk.path": "./node_modules/typescript/lib"`; older releases may use `typescript.tsdk`. Do not copy both keys blindly or assume the current main schema establishes support in the installed release. Resolve the actual package path in workspaces or non-node_modules installations. See [VS Code TypeScript](https://code.visualstudio.com/docs/typescript/typescript-transpiling).

Target file: `.vscode/extensions.json`. Append missing IDs to existing recommendations.

```json
{
  "recommendations": [
    "dbaeumer.vscode-eslint",
    "esbenp.prettier-vscode"
  ]
}
```

Use the [ESLint extension](https://github.com/microsoft/vscode-eslint) and [Prettier extension](https://github.com/prettier/prettier-vscode) documentation to verify local library resolution, workspace working directories, trust and save actions. Prefer local libraries rather than global fallbacks; confirm actual resolution and explicit-save behavior in the target editor. Recommendations alone do not install or activate extensions.

## Optional Git hooks and commit checks

Conventional Commits remains the preferred message style; automation is optional. Select lint-staged for staged checks, Husky for local hook dispatch and Commitlint only when automated message validation is useful. Do not add all tools merely to adopt lint/format preferences; preserve existing automation. The following recipes apply only to selected components.

Available local development packages: `husky`, `lint-staged`, `@commitlint/cli` and `@commitlint/config-conventional`, plus selected lint/format tools. Follow the selected release's [Husky setup](https://typicode.github.io/husky/get-started.html) in the target; preserve existing lifecycle commands when merging `prepare`. Do not copy generated `.husky/_` internals or deprecated bootstrap/install commands.

When staged checks are selected, required packages are `lint-staged` and the selected lint/format tools. Target file: `lint-staged.config.mjs`. Merge disjoint file groups into the existing config. Add framework extensions only when their lint/format support is configured.

```js
export default {
  '*.{js,cjs,mjs,jsx,ts,cts,mts,tsx}': ['eslint --fix', 'prettier --write'],
  '*.{json,jsonc,md,yml,yaml,css,scss,html}': 'prettier --write',
};
```

Remove unsupported extensions in the target. Exclude generated/lockfile paths through tool ignores; formatter-only generated files must also have appropriate ignores. [lint-staged](https://github.com/lint-staged/lint-staged) appends staged paths and restages results; do not add `git add`. Sequential arrays run lint fix before format; disjoint groups avoid concurrent writes. Preserve default backup and partially staged file protection. Typed lint can inspect more than staged files.

When automated commit checks are selected, required packages are `@commitlint/cli` and `@commitlint/config-conventional`. Target file: `commitlint.config.mjs`. Merge the conventional preset with existing project policy.

```js
export default { extends: ['@commitlint/config-conventional'] };
```

Follow [Commitlint configuration](https://commitlint.js.org/reference/configuration.html) and [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/). Examples: `feat: add search`, `fix(parser): handle empty input`, `feat!: change API`, with a `BREAKING CHANGE:` footer when appropriate. Scopes, branch policy and package manager are target decisions; no shared scope enumeration is imposed.

When local hooks are selected, required packages are `husky` and the tools invoked by each hook. Target files: user hook bodies in `.husky/`, after installing the selected supported Husky version. Select each hook independently; staged checks do not require commit-message or pre-push hooks. Merge commands into existing hooks. The following snippets use **npm only as an example**; use the target manager's documented local execution/script syntax and verify its missing-package behavior.

`.husky/pre-commit`:

```sh
npm exec --no -- lint-staged
```

`.husky/commit-msg` — validate the actual message file, preserving quoted argument handling:

```sh
npm exec --no -- commitlint --edit "$1"
```

`.husky/pre-push` — the target must provide real `typecheck` and `test` scripts:

```sh
npm run typecheck && npm run test
```

See [Commitlint local setup](https://commitlint.js.org/guides/local-setup.html). For selected hooks, test actual dispatch and relevant failure cases in the target: lint/format failure and partial staging for pre-commit, invalid messages for commit-msg, and type/test failure for pre-push. If tests do not exist, report that gap and decide the applicable hook policy explicitly; do not fabricate passing coverage.

Hooks can be skipped or absent and do not replace CI. When CI is used, it independently runs applicable format/lint/types/tests/builds; add commit-message checks over the target’s selected range only when that automation is selected. Define required history/new-branch behavior and immutable install policy in the target. Local hook success does not establish remote CI or branch protection.

## Target commands

Merge actual commands into target scripts and document working directories. These are roles, not scripts for this repository.

| Role | Usual implementation / condition |
| --- | --- |
| format | `prettier --write` with a reviewed file list during adoption |
| format:check | `prettier --check` over the intended project scope |
| lint | `eslint` over supported source/config paths |
| typecheck | `tsc --noEmit`, project-reference commands or framework checker |
| test | The target's real runner/suites; do not claim empty-suite coverage |
| build | The actual deliverable's compiler/bundler/framework command |
| prepare | Only when Husky is selected: supported setup merged with existing lifecycle behavior |

Record versions, exact scripts, selected settings and exclusions in README or the optional [tooling document](../templates/docs/tooling.md). Link task evidence when it exists and report task-specific results directly otherwise. Follow [version selection](adoption.md#version-and-support-policy).
