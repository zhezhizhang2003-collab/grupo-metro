# Ralph — Grupo METRO Web
You are an autonomous coding agent. Follow these instructions exactly.

## Your Task (One Story Per Run)
1. Read `prd.json` in this directory
2. Read `progress.txt` (check Codebase Patterns section first)
3. Check you're on branch from PRD `branchName`. If not, `git checkout -b <branchName>` from main.
4. Pick the **highest priority** user story where `passes: false`
5. Implement that **single** user story
6. Run quality checks: `npm run build`
7. If checks pass, commit ALL changes: `git add -A && git commit -m "feat: [Story ID] - [Story Title]"`
8. Update `prd.json` to set `passes: true` for the completed story
9. APPEND progress to `progress.txt` (format below)
10. If ALL stories have `passes: true`, reply with: `<promise>COMPLETE</promise>`

## Progress Report Format
APPEND to progress.txt:
```
## [Date/Time] - [Story ID]
- What was implemented
- Files changed
- **Learnings for future iterations:**
  - Patterns discovered
  - Gotchas encountered
  - Useful context
---
```

If you discover reusable patterns, add them to `## Codebase Patterns` at top of progress.txt.

## Project: Grupo METRO Web

**Business:** Mehar Company SL — distribución de bebidas a restauración/supermercados en Tarragona.

### Stack
- Astro 6 (static site, `.astro` files)
- Tailwind CSS v4 (`@import "tailwindcss"`, `@theme` in CSS — no config file)
- Node >= 22.12.0

### Commands
- `npm run dev` — dev server localhost:4321
- `npm run build` — production build to ./dist/
- `npm run preview` — preview build

### Project Structure
```
public/logos/    ← PNG/SVG de marcas (200px, fondos transparentes)
public/logo.jpg  ← Logo Grupo METRO
public/catalogo-junio-2026.pdf
src/pages/       ← 5 páginas: index, catalogo, aviso-legal, privacidad, cookies
src/layouts/     ← Layout.astro (nav + slot + footer)
src/styles/      ← global.css (Tailwind + marquee animation)
```

### Codebase Patterns
- **Design:** Industrial Bold — negro/zinc-950 + ámbar (#f59e0b / amber-400)
- **Fonts:** Bebas Neue (display) + Inter (body), loaded from Google Fonts in `<head>`
- **Colors:** `bg-zinc-950`, `bg-black`, `text-amber-400`, `border-zinc-800`
- **Marquee:** CSS keyframes `translateX(-50%)`, array duplicado para loop infinito, `marquee-pause` en hover
- **Layout.astro:** Accepts `title` and `description` as Astro.props, renders full HTML document
- **Prose:** Tailwind prose with `prose-invert` for legal pages
- **Logo naming:** spaces→dashes, special chars removed — `Coca-Cola.svg`, `Estrella-Damm.png`

### Gotchas
- SVG logos preferred over PNG (vector = always sharp)
- Logo files in `public/logos/` are a mix of real PNG and SVG
- Mobile menu uses vanilla JS inline in Layout.astro
- PDFs in /public/ are served directly, not processed by Astro
- Tailwind v4 uses CSS-based config (`@theme`), not `tailwind.config.js`
- Spanish locale dates: `new Date().toLocaleDateString('es-ES', ...)`

### Company Data
- Razón social: Mehar Company SL
- CIF: B05412028
- Dirección: Polígono Francolí Parcela 15, Nave 5, Tarragona 43006
- WhatsApp: +34 600 781 881

## Quality Requirements
- Build MUST pass: `npm run build` with zero errors
- Do NOT commit broken code
- Keep changes focused and minimal
- Follow existing patterns

## Important
- Work on ONE story per iteration
- Commit after each completed story
- Read Codebase Patterns in progress.txt before starting
- SVG is always better than PNG for logos
