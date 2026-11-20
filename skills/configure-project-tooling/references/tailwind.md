# Tailwind CSS tooling

Apply only when the target uses Tailwind CSS. Follow [adoption](adoption.md) and preserve existing parser, formatting and framework configuration. This reference does not introduce Tailwind into an unrelated project.

Follow the target's applicable project instructions for ongoing styling preferences. This tooling integration configures canonical-class checks and does not create authoring instructions or require another skill. Account for [Tailwind source detection](https://tailwindcss.com/docs/detecting-classes-in-source-files) when reviewing class-helper coverage.

## Canonical-class linting

The editor diagnostic `tailwindcss(suggestCanonicalClasses)` corresponds to the IntelliSense setting `tailwindCSS.lint.suggestCanonicalClasses`. For ESLint/CI, select `better-tailwindcss/enforce-canonical-classes` from `eslint-plugin-better-tailwindcss`; it provides automatic fixes. See the [rule documentation](https://github.com/schoero/eslint-plugin-better-tailwindcss/blob/main/docs/rules/enforce-canonical-classes.md). Canonicalization requires a supported Tailwind v4 combination; the documented capability starts at v4.1.15. This is a capability floor, not a pinned dependency recommendation. Check selected-release support, engines, peers and advisories before installation. Do not enable it for Tailwind v3 or force an unrelated upgrade.

Target file: existing `eslint.config.mjs`. Merge the import and spread `tailwindEntries` into the exported Flat Config array after applicable parser/framework entries and before final formatting conflict disabling. Required local development packages: compatible `eslint`, `eslint-plugin-better-tailwindcss` and the target's existing `tailwindcss`; TSX also requires the configured `typescript-eslint` parser. This example scopes an existing JSX/TSX project; keep JSX parsing enabled in its parser configuration.

```js
import betterTailwindcss from 'eslint-plugin-better-tailwindcss';

const tailwindEntries = [
  {
    files: ['**/*.{jsx,tsx}'],
    plugins: { 'better-tailwindcss': betterTailwindcss },
    settings: {
      'better-tailwindcss': {
        entryPoint: 'src/styles/global.css',
      },
    },
    rules: {
      'better-tailwindcss/enforce-canonical-classes': 'error',
    },
  },
];
```

Replace `src/styles/global.css` with the actual Tailwind CSS entry stylesheet. Resolve `entryPoint` and, when needed, `cwd` per package using the documented [settings](https://github.com/schoero/eslint-plugin-better-tailwindcss/blob/main/docs/settings/settings.md); do not lint a customized theme against an accidental default configuration. Register the plugin once per matching scope. Extend file coverage only with a supported [language parser integration](https://github.com/schoero/eslint-plugin-better-tailwindcss#quick-start); an Astro/HTML glob alone supplies no parser. Check the documented selectors cover actual attributes and class helpers.

Enable this rule individually rather than adopting all stylistic rules. Keep class sorting and wrapping with the existing Prettier setup, including `prettier-plugin-tailwindcss` when selected; sorting does not enforce canonical names. Review overlapping shorthand, important-position and variable-syntax rules before combining them. Treat fixes as reviewable changes, especially around theme values and variants. Leave root-font-size assumptions unset unless established for the target. Use documented plugin APIs only; do not import Tailwind internals into target configuration.

Keep the editor diagnostic until lint coverage is established. If duplicate diagnostics are unwanted, optionally merge `"tailwindCSS.lint.suggestCanonicalClasses": "ignore"` into the existing `.vscode/settings.json` only for a VS Code target with Tailwind CSS IntelliSense and working ESLint coverage. This editor-only setting does not configure CI. See [IntelliSense settings](https://github.com/tailwindlabs/tailwindcss-intellisense#extension-settings).

## Target verification and completion

In the adopting project, check that an inline arbitrary display property such as `[display:flex]` is reported and fixed to `flex`, and that the canonical form passes. Check actual custom-theme values, variants, class helpers and selected framework files; confirm CLI/CI and editor resolve the same stylesheet. Review affected rendered behavior and fix diffs. Do not assume exact editor/linter parity across different versions or project resolution.

Record the selected rule, severity, stylesheet, covered files/helpers, intentional exceptions and actual verification in the existing target tooling document or task evidence. Report unsupported combinations and uncovered syntax explicitly; retain editor guidance if CLI support is unavailable. Do not claim these checks ran while editing this Markdown-only source repository.
