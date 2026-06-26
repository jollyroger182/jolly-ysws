# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

- `bun run dev` — start Vite dev server
- `bun run build` — production build (Vercel adapter)
- `bun run preview` — preview production build
- `bun run check` — type-check via `svelte-kit sync && svelte-check`
- `bun run lint` — `prettier --check . && eslint .`
- `bun run format` — `prettier --write .`

Package manager is bun (see `bun.lock`, `.npmrc`).

## Architecture

SvelteKit app deployed to Vercel (`@sveltejs/adapter-vercel`), styled with Tailwind CSS v4 via the `@tailwindcss/vite` plugin (no `tailwind.config` file — Tailwind v4 uses CSS-based config).

Svelte 5 **runes mode is forced on** for all project files via `vite.config.ts` (only `node_modules` are exempt). Write components with runes (`$state`, `$derived`, `$props`, etc.), not the legacy reactive syntax.

Routes live in `src/routes/` (standard SvelteKit filesystem routing). Shared code goes in `src/lib/` and is importable as `$lib/...`.
