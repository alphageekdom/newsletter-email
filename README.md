# A|G Realty — Investor Briefing Email

A bulletproof HTML email designed as Issue 01 of a fictional quarterly
investor briefing from A|G Realty. Built as a self-contained portfolio
piece demonstrating editorial design, typographic hierarchy, and
cross-client email compatibility.

## Live Preview

https://ag-realty.netlify.app

## Design Approach

Hybrid editorial / finance aesthetic — dual-font typography (Instrument
Serif display + Poppins body), numbered section structure inspired by
quarterly print publications, and a restrained cyan-on-navy palette.

## Tech Stack

- XHTML 1.0 Transitional (doctype with strict DTD)
- Inline hex styling for client-wide compatibility
- VML fallbacks for Outlook gradient backgrounds and CTA buttons
- Ghost tables with `<!--[if mso]>` conditionals
- 600px responsive shell collapsing to 480px / 100% at breakpoints
- No JavaScript, no external CSS, no build step

## Tested Clients

- Gmail (web, iOS, Android)
- Apple Mail (macOS, iOS)
- Outlook 365 (web, Windows 2016+)
- Yahoo Mail

## Structure

Single `index.html` file with `img/` folder. Plain-text fallback in
`index.txt`. No framework, no preprocessor — just raw HTML and CSS
with MSO conditionals.

## Running Locally

Open `index.html` directly in a browser. No build step required.
