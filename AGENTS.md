# AGENTS.md

This folder is the Simsim launch page: a standalone, single-file marketing page (`index.html`).

The parent folder's Astryx rules (no `<div>`, AppShell, token-only styling) do NOT apply here.
Plain HTML/CSS/JS, GSAP + ScrollTrigger from jsDelivr, Phosphor icons, Google Fonts.

## Design system: `PATTERN.md` (Full-bleed Grid with Dividers)
- Use only the colours, fonts and radius declared in `PATTERN.md`: ink `#0a0a0a`, surface `#fff`, muted `#737373`,
  hairline `#e5e5e5`, and the foreground alphas 0.04 / 0.06 / 0.08 / 0.10. Geist + Geist Mono, radius 0, no shadows.
- Agreed exception: IBM Plex Sans Arabic (Arabic glyphs, which Geist lacks) and Aref Ruqaa (handwriting inside demo documents only).
- Layout contract: 6 full-height column hairlines (2 below 768px), 1200px content, 96px section padding,
  divider between sections, and the diagonal-stripe band used once (the hero).
- One primary CTA per section. The nav uses a text link, not a button.
- UI transitions are 200ms or less. The product demos (hero extraction loop, pinned pipeline, seed wordmark) are content and keep their timing.
- Right and wrong are shown in monochrome: strikethrough with ✕ for wrong, ✓ for right. No red or green.

## Content
- All copy, demo fields, comparison cases and benchmark numbers live in the `CONTENT` section of the script.
- Anything not yet confirmed carries `class="ph-draft"` + `data-draft="..."`. Open the page with `?draft` to outline them.
- Waitlist forms post JSON to `CONFIG.waitlistEndpoint`; while it is empty, submissions are simulated.
