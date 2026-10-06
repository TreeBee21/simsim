# AGENTS.md

This folder is the Simsim marketing site: plain static pages, no build step.
- `index.html` home page (hero demo, hard cases, benchmarks, pinned pipeline, security, waitlist)
- `use-cases.html` banking, insurance, procurement and government workflows
- `site.css` shared styles for every page, `config.js` shared settings (waitlist endpoint)
- `vercel.json` turns on clean URLs (`/use-cases`)

The parent folder's Astryx rules (no `<div>`, AppShell, token-only styling) do NOT apply here.
Plain HTML/CSS/JS, GSAP + ScrollTrigger from jsDelivr, Phosphor icons, Google Fonts.

## Design system: `PATTERN.md` (Full-bleed Grid with Dividers)
- Use only the colours, fonts and radius declared in `PATTERN.md`: ink `#0a0a0a`, surface `#fff`, muted `#737373`,
  hairline `#e5e5e5`, and the foreground alphas 0.04 / 0.06 / 0.08 / 0.10. Geist + Geist Mono, radius 0, no shadows.
- Agreed exceptions: IBM Plex Sans Arabic (Arabic glyphs, which Geist lacks), plus Aref Ruqaa and Caveat for handwriting inside demo documents only.
- Layout contract: 6 full-height column hairlines (2 below 768px), 1200px content, 96px section padding,
  divider between sections, and the diagonal-stripe band used once (the hero).
- One primary CTA per section. The nav uses a text link, not a button.
- UI transitions are 200ms or less. The product demos (hero extraction loop, pinned pipeline, seed wordmark) are content and keep their timing.
- Right and wrong are shown in monochrome: strikethrough with ✕ for wrong, ✓ for right. No red or green.

## Positioning
- "Any document, read like an expert." Simsim sells the work getting done, not OCR: extraction is the beachhead,
  agents then do expert work downstream (credit memos, underwriting files, tender evaluations, statistics releases).
- Niche: high-stakes financial services and related work: banking (loan origination, trade finance),
  insurance (underwriting, claims), procurement (tender evaluation, spend) and government (official statistics).
- Pick use cases that need judgment and scarce expertise (analyst work). Avoid ones that if-then rules can do,
  such as certificate or compliance checks: the founder rejected supplier due diligence for that reason.
- The $1 software : $16 labour framing is for investors, not this site.
- Arabic is the proof point, not the headline: "We built Simsim on Arabic, one of the hardest scripts to read."
- No invoices in the hero (seen as a solved trope). The demo cycles an income statement with notes and a chart,
  then an Arabic bank statement; agent findings are rows with `flag: true` in `CONTENT.demo`.

## Content
- All copy, demo fields, comparison cases and benchmark numbers live in the `CONTENT` section of the script.
- Anything not yet confirmed carries `class="ph-draft"` + `data-draft="..."`. Open the page with `?draft` to outline them.
- Waitlist forms on every page post JSON to `waitlistEndpoint` in `config.js`; while it is empty, submissions are simulated.
