# AGENTS.md

Guidance for AI agents (and humans) working in this repository — a minimal
Vite + React template for [Lyra Design System](https://lyra-ds.dev).

## Lyra DS documentation

- Docs: https://lyra-ds.dev
- Machine-readable component contracts: https://lyra-ds.dev/llms.txt
- Packages: [`@lyra-ds/react`](https://www.npmjs.com/package/@lyra-ds/react)
  (components, `ThemeProvider`, `useTheme`) and
  [`@lyra-ds/styles`](https://www.npmjs.com/package/@lyra-ds/styles)
  (CSS, imported once in `src/main.tsx`).
- **Never invent Lyra component APIs.** When unsure about a prop or variant,
  check llms.txt or the docs first — the published contracts are the source
  of truth.

## Commands

- `pnpm dev` — dev server · `pnpm build` — type-check + production build
- `pnpm test` — Vitest (jsdom) · `pnpm lint` — ESLint (typescript-eslint)
- `pnpm format` / `pnpm format:check` — Prettier
- CI runs lint, format check, tests, and build on every push and PR.

## Conventions

- TypeScript strict; single-page React app mounted in `src/main.tsx`;
  styles and fonts are imported there, once.
- Static assets live in `public/` and are referenced from the site root
  (`/lyra-mark.svg`), not imported.
- Style: no semicolons, single quotes — Prettier enforces it; run
  `pnpm format` before committing.
- Tests: Vitest + Testing Library; query by role/label, never mock
  `@lyra-ds/react`.
- White-label branding happens through exactly four CSS variables
  (`--brand`, `--brand-contrast`, `--brand-radius`, `--brand-font`) —
  see `src/brand.css`. Don't restyle Lyra components ad hoc; derive from
  the brand tokens. The baseline Lyra look means no `data-brand`
  attribute at all — never set it without defining `--brand`.
- `src/components/starter-home.tsx` is disposable demo content — template
  users delete it (see README "After cloning").
