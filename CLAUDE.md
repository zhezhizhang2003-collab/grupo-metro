# Grupo METRO Web — CLAUDE.md

## Project

Web informativa para Grupo METRO (Mehar Company SL), distribuidora de bebidas a restauración y supermercados en Tarragona.

## Stack
- Astro 6 + Tailwind CSS v4
- Node >= 22.12.0

## Commands
- `npm run dev` → localhost:4321
- `npm run build` → ./dist/

## Design System (Professional Light/Dark Hybrid)

### Section Alternation
1. **Hero** — Dark (`#0a0c1e` gradient)
2. **Quiénes Somos** — White (`#ffffff`) with shadow cards
3. **Marcas** — Light gray (`#f7f7fb`) with dot pattern, static grid
4. **Catálogo CTA** — Brand red (`#d9445a`) solid
5. **Contacto** — White (`#ffffff`)
6. **Footer** — Dark navy

### Palette
| Role | Color |
|------|-------|
| Red accent | `#d9445a` (brand-red) |
| Blue accent | `#5856c0` (brand-blue) |
| Dark surface | `#0a0c1e` (color-dark) |
| Dark alt | `#0f1130` (color-dark-alt) |
| Dark card | `#151838` (color-dark-card) |
| Light surface | `#ffffff` (color-light) |
| Light alt | `#f7f7fb` (color-light-alt) |
| Light card | `#f0f0f6` (color-light-card) |
| Light border | `#e0e1ec` (color-light-border) |
| Text dark | `#11142a` (color-text-dark) |
| Text muted | `#5c5f78` (color-text-muted) |

### Typography
- Display: Oswald (headings, uppercase, tracking-tight)
- Body: Inter

### What NOT to use
- No blur-3xl orbs
- No pulse-ring animations
- No marquee/carousel
- No green WhatsApp buttons (use red)
- No mock-window UI elements
- No bg-zinc-* or bg-black classes (use CSS variables)

### What TO use
- `.reveal` class for scroll-triggered fade-in (works with IntersectionObserver)
- Section alternation: light → dark → light → dark
- White cards with `shadow-[var(--shadow-md)]` on light backgrounds
- Geometric SVG line accents instead of blur orbs
- Static grids of brand logos (not carousels)
- 5 nav links: Inicio, Catálogo, Quiénes Somos, Marcas, Contacto

## Files
```
src/pages/       — index, catalogo, aviso-legal, privacidad, cookies
src/layouts/     — Layout.astro (nav + footer + JSON-LD + mobile script)
src/styles/      — global.css (Tailwind @theme + utilities)
public/logos/    — Brand logo files (SVG preferred, PNG fallback)
```

## Company Data
- Mehar Company SL · CIF B05412028
- Polígono Francolí Parcela 15, Nave 5, Tarragona 43006
- WhatsApp: +34 600 781 881
