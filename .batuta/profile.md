# Batuta profile — lyra-ds/starter-vite

Stack: Vite / React / TypeScript; Vitest and ESLint; pnpm@11.18.0
Methodology: tests-after; Conventional Commits; feature branches and PRs to main
Test: pnpm test
Build: pnpm build
Install: pnpm install --frozen-lockfile
Lint: pnpm lint && pnpm format:check
Execution: sequential
Worktree: medium+
Worktree-home: cache
Template: templates/react.md

## Conventions

- Follow the repository AGENTS.md and the published Lyra contracts; never invent component APIs.
- Preserve the existing white-label brand tokens, local fonts and framework conventions.
- Treat Lyra as the owner of component appearance and behavior; do not add local substitutes.
- Keep changes scoped and verify the repository CI commands before integration.

## Project map

Refreshed from local source on 2026-10-14.

`package.json` and pnpm-lock.yaml pin the application tools and Lyra peers.
`src/main.tsx` mounts React and imports shared styles and fonts once.
`src/` owns the single-page application source.
`src/brand.css` owns the four existing white-label variables.
`src/components/` holds local application compositions.
`src/components/starter-home.tsx` is the disposable starter demonstration.
Public UI primitives come from @lyra-ds/react.
Existing colocated tests exercise rendered React behavior.
`public/` holds static assets referenced from the site root.
`index.html` owns the Vite HTML entry point.
`vite.config.ts` configures React, Vitest and the deployment base.
The demo retains its existing GitHub Pages base path.
`vitest.setup.ts` configures DOM testing support.
Vitest uses jsdom and Testing Library.
Query by role/label and use real Lyra components in tests.
`eslint.config.mjs` owns TypeScript, hooks and refresh checks.
`tsconfig.json` owns strict typing and its bounded source include list.
`.prettierignore` excludes generated frontend artifacts.
`.github/workflows/` owns required lint/test/build and publication automation.
`AGENTS.md` owns public API and brand conventions.
Do not add local component appearance that belongs in Lyra.
Do not hand-edit dist/ or node_modules/.
Regenerate lockfiles through the pinned package manager only.
Build first-party assets with the current Vite configuration.
`WORK.md` and .batuta/ own conducting state and task evidence.
