# A|G Realty — The 2026 Investor Briefing

![Full desktop view of the email](screenshots/desktop.jpeg)

A bulletproof HTML email designed as Issue 01 of a fictional quarterly investor briefing from A|G Realty. Built as a self-contained portfolio piece demonstrating editorial design thinking, typographic hierarchy, and cross-client email engineering — where every styling decision has to survive Gmail, Apple Mail, and Outlook simultaneously.

**Live preview:** [ag-realty.netlify.app](https://ag-realty.netlify.app)

## Case study

The piece uses a hybrid editorial / finance aesthetic — dual-font typography (Instrument Serif for display, Poppins for body), a numbered section structure borrowed from quarterly print publications, and a restrained cyan-on-navy palette.

The masthead opens with a quote-as-standfirst — *"The markets that will hold through 2026 aren't the ones moving loudest — they're the ones moving steadiest"* — anchoring the editorial voice before any section content lands. What started as a separate pull-quote section was folded into the masthead late in development; what started as three numbered content rows (Portfolio / Asset Types / Performance) was consolidated into two (Portfolio absorbing the four-category asset list, Performance retaining the three-up stat grid). Both decisions killed a section each. The right move over padding for length.

![Masthead detail — wordmark, serif headline, italic-serif standfirst, attribution](screenshots/masthead.jpeg)

The signature typographic moment is the three-up performance grid: oversized italic serif numerals (`5–9%` / `12` / `Q1`) in cyan over navy, divided by thin teal vertical rules. On mobile the layout inverts — the vertical rules disappear and horizontal ones take their place, separating each stacked stat.

![Performance stat grid — three-up italic serif numerals on navy with cyan vertical dividers](screenshots/stat-grid.jpeg)

## Technical approach

- **XHTML 1.0 Transitional** with VML + Office namespaces for Outlook rendering parity
- **MSO conditional stylesheets** for Outlook font fallbacks (Georgia substituting Instrument Serif)
- **Bulletproof structure**: presentation tables, inline styles, VML fallbacks on every gradient surface (top banner, footer) and the primary CTA's `<v:roundrect>`
- **Responsive cascade**: 600px container → 480px at ≤600px → 100% at ≤480px, with utility classes (`.dw`, `.db`, `.stack-gap`, `.stat-grid-col`) handling column stacking and divider-to-border transitions on mobile
- **Dual-branch CTA pattern**: MSO branch renders via VML; non-MSO branch is a styled `<a>` with a `.cta-lift` hover wrapped in `@media (hover: hover)` — progressive enhancement that surfaces on the Netlify preview and degrades silently everywhere email clients render

![Full mobile view at 390px — stat grid stacked vertically, columns collapsed](screenshots/mobile.jpeg)

## Accessibility & craft

- WCAG AA contrast — caption slate darkened to `#4a6a7a`, footer gradient endpoint muted to `#1a7a90` so white text stays legible across the full gradient
- Meaningful alt text on all images; explicit `width` / `height` attributes for Outlook layout
- CAN-SPAM compliance: physical postal address, unsubscribe link, sender identification
- Plain-text fallback in `index.txt`

## Tested clients

Gmail (web, iOS, Android) · Apple Mail (macOS, iOS) · Outlook 365 (web) · Yahoo Mail

## Tech stack

No framework, no preprocessor, no build step. A single `index.html` at repo root, email assets in `img/`, plain-text fallback in `index.txt`, documentation screenshots in `screenshots/`.

## Running locally

```sh
open index.html
```
