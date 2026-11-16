# React additions

Optional: select for React source. Apply [common TypeScript tooling](tooling.md) once. React does not mandate a particular build tool, test runner or project architecture here. No Next.js-specific guide or configuration is supplied.

## TypeScript and runtime

Consult [React TypeScript guidance](https://react.dev/learn/typescript). Use `react` and, for React DOM applications, `react-dom`, with compatible type declarations such as `@types/react` and `@types/react-dom` when required. Select versions through the common adoption policy.

Target file: the React package's existing `tsconfig.json`. Merge only when the build/framework uses the automatic JSX runtime:

```json
{
  "compilerOptions": {
    "jsx": "react-jsx"
  }
}
```

Preserve framework-specific JSX requirements. Browser DOM libraries/globals apply only to browser code; React can execute elsewhere. Preserve module resolution, aliases and project references. A bundler's transpilation is not TypeScript checking.

## Lint intentions

Optional React lint packages: `eslint-plugin-react`, `eslint-plugin-react-hooks` and, for DOM JSX, `eslint-plugin-jsx-a11y`, alongside common tooling. Check current maintained releases, engines/peers and documented Flat Config exports before choosing them. A plugin named here is not a reason to force incompatible peers or downgrade to EOL tools.

Target file: existing `eslint.config.mjs`. Merge the selected releases' documented presets and scoped overrides before final eslint-config-prettier. Read the author documentation rather than assuming all presets share an export shape or file scope.

| Intended behavior | Documented integration to evaluate | Scope |
| --- | --- | --- |
| JSX/component correctness | [React plugin](https://github.com/jsx-eslint/eslint-plugin-react) recommended Flat Config | React JSX/TSX |
| Automatic JSX transform | React plugin JSX-runtime preset | Only the selected automatic runtime |
| Hook call order and dependencies | [React Hooks plugin](https://react.dev/reference/eslint-plugin-react-hooks) recommended config | React modules, including plain TS custom-hook files |
| Semantic DOM/ARIA checks | [JSX accessibility plugin](https://github.com/jsx-eslint/eslint-plugin-jsx-a11y) recommended config | DOM JSX/TSX; map custom components deliberately |
| Avoid unintended conditional output | React `jsx-no-leaked-render`, with documented coercion/ternary options | JSX/TSX where suitable |
| Static TS props checking | Disable React `prop-types` only for TSX when TypeScript supplies the contract | Preserve JS component checks |

Use the installed React version for plugin behavior, such as documented `settings.react.version: 'detect'`. Do not disable whole presets to conceal a project mismatch. Hooks compiler diagnostics do not imply React Compiler has been installed or enabled. Static accessibility checks do not establish full accessibility.

If staged checks are selected, common globs already include `.jsx` and `.tsx`; do not add overlapping groups. Common VS Code language selectors cover React modules. No extra React formatter or mandatory React editor extension is required. Tailwind remains optional.

## Target verification

Use the actual target's typecheck, test and build commands. Component tests may use a supported runner, React Testing Library and an appropriate DOM environment; none is a mandatory shared tool choice. Test visible behavior, semantic queries, interaction and state changes, with cleanup configured as needed. DOM emulation does not establish real-browser, visual or assistive-technology behavior. Report absent suites honestly.

## Astro and React

Follow the current [official Astro React integration](https://docs.astro.build/en/guides/integrations-guide/react/). Required integration package when selected: `@astrojs/react`, with compatible Astro, React, React DOM and tooling. Merge the documented integration into the target's existing Astro config; preserve its TypeScript and JSX requirements.

Keep common rules once, Astro parsing on `.astro`, React JSX/accessibility on `.jsx`/`.tsx`, Hooks on relevant React modules, and final formatting conflict disabling. React rules on modules do not inspect Astro templates. Verify the whole engine/peer/parser/integration combination and actual affected rendering/hydration in the target. Separate successes do not prove the combination works. If support is unavailable, stop that dependent integration, report exact constraints and supported alternatives, and continue independent work.

Apply the common [source filename lint rule](tooling.md#source-filename-linting) to React modules using the configured JSX/TypeScript parser. Deployment, auth, workspace names, branch policy, React Native and server architecture are not common defaults.
