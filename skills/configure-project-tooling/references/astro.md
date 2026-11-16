# Astro additions

Optional: select only for Astro packages. Apply [common tooling](tooling.md) once and follow [adoption](adoption.md). Choose currently supported compatible releases; no Astro, parser or tool version is fixed here.

## Lint and format

Required packages for the selected layer: `eslint-plugin-astro` and `prettier-plugin-astro`, plus common tooling. Check engines, peers, documented parser support and current preset exports in the [lint plugin guide](https://ota-meshi.github.io/eslint-plugin-astro/user-guide/) and [formatter plugin documentation](https://github.com/withastro/prettier-plugin-astro).

Target file: existing `eslint.config.mjs`. Add the import and insert the preset after common rules, before final eslint-config-prettier; retain existing overrides.

```js
import astro from 'eslint-plugin-astro';

// Merge these entries into the existing array before formatting.
const astroEntries = [...astro.configs.recommended];
```

Spread `astroEntries` into the existing exported array, or use `...astro.configs.recommended` directly as array entries for releases documenting that export. The preset owns Astro parsing. Keep ordinary typed rules scoped to real `.ts`/`.tsx`/`.mts`/`.cts` projects; do not apply them indiscriminately to `.astro` or virtual scripts. If extending type-import checks into Astro frontmatter, establish documented TypeScript parser forwarding for the selected parser/plugin combination and verify both frontmatter and frontmatter-free files in the target. Do not retain a historical parser workaround without current support evidence. Framework checking and ordinary typed lint are distinct.

Target file: the existing Prettier configuration. Merge the plugin and override while preserving other plugins and options.

```json
{
  "plugins": ["prettier-plugin-astro"],
  "overrides": [
    { "files": "*.astro", "options": { "parser": "astro" } }
  ]
}
```

Keep the common singleQuote/trailingComma preferences. Tailwind formatting is conditional; follow its current plugin ordering and project-path requirements when selected.

Target files: ESLint global ignores and `.prettierignore`. Add generated `.astro` output (`**/.astro/**`); retain real generated output paths. When staged checks are selected, target `lint-staged.config.mjs`: merge a disjoint `'*.astro': ['eslint --fix', 'prettier --write']` group after confirming both tools support Astro. Do not duplicate processing in another group.

## TypeScript and commands

Target file: the Astro package's `tsconfig.json`. Merge the [official strict preset and generated declarations](https://docs.astro.build/en/guides/typescript/), preserving aliases, JSX settings and existing includes/excludes.

```json
{
  "extends": "astro/tsconfigs/strict",
  "include": [".astro/types.d.ts", "**/*"],
  "exclude": ["dist"]
}
```

This is an Astro-package starting point, not a monorepo-root replacement. Required framework packages include `astro`, local `typescript` and the checker required by the selected Astro release, such as `@astrojs/check`. Use documented sync/generation steps. `astro check` checks framework types; `astro build` produces output and is not a substitute for typechecking. Verify actual runtime/browser behavior separately where affected.

## Editor and composition

Target `.vscode/extensions.json`: append `astro-build.astro-vscode`. Target `.vscode/settings.json`: merge an `[astro]` language object with `"editor.defaultFormatter": "esbenp.prettier-vscode"` when using the selected local Prettier plugin. Confirm formatter activation, local resolution and ESLint `.astro` probing/validation in the installed extensions; use [Astro editor guidance](https://docs.astro.build/en/editor-setup/). Preserve existing language selectors.

When React is present, follow the [React composition gate](react.md#astro-and-react). Keep Astro parsing on `.astro`, React JSX rules on React modules, common rules once and formatting conflict disabling last. Confirm the current official integration and the entire peer/engine combination rather than assuming individually supported layers compose.

For the common [source filename lint rule](tooling.md#source-filename-linting), add `**/*.astro` to its files list after this Astro parser layer is configured. Keep the rule on physical files and verify frontmatter-free components too. Preserve dynamic route contracts such as `[slug].astro` and `[...slug].astro`; document exact rule-specific exceptions if required. Page renames may change URLs. Adapters, deployment, auth, aliases, workspace names and branches remain target decisions.
