## Phase goal

Build a hilariously over-the-top static HTML comedy page that validates the SABS pipeline end-to-end. The page features absurdist corporate-parody humor with dashboard-style markup, bold non-default typography, intentional color choices, and an interactive button with randomized outcomes. Zero external dependencies — everything loads from local files only.

### Stories in scope
- US-01 — Absurd comedy landing page
- US-02 — Interactive comedy button

### Done-when (observable)

#### US-01 criteria
- [x] `index.html` exists in project root and contains `<!DOCTYPE html>` declaration and `<html>` tag [US-01]
- [x] Page contains at least 3 distinct `<section>` or heading-delimited content blocks with humor text (verifiable: grep finds >= 3 `<section` or `<h2` tags) [US-01]
- [x] CSS is applied via `<style>` block or linked `.css` file with at least 10 rule declarations (verifiable: count CSS rules in source) [US-01]
- [x] Page renders without JavaScript errors on load (Playwright: no uncaught exceptions during page.goto) [US-01]
- [x] At least one section contains dashboard-style markup — a `<table>` or grid of elements displaying numeric or status values with labels (verifiable: grep finds `<table` or elements with data-label/data-value attributes within a section) [US-01]
- [x] Page uses a non-default font — CSS contains at least one `font-family` declaration that is not solely a generic family keyword (verifiable: grep for `font-family` in CSS) [US-01]
- [x] Page uses at least 3 distinct non-black/white color values in CSS (verifiable: count unique `color`, `background-color`, or `background` hex/rgb/hsl values) [US-01]

#### US-02 criteria
- [x] A `<button>` element exists and is visible in the viewport on page load (Playwright: button is visible without scrolling) [US-02]
- [x] Clicking the button changes the `textContent` of at least one non-button DOM element (Playwright: element text before click !== element text after click) [US-02]
- [x] Source code defines at least 5 distinct outcome strings or objects (verifiable: grep/count array or object entries in JS) [US-02]
- [x] Button click handler is registered via `addEventListener`, not inline `onclick` attribute (verifiable: grep for `addEventListener` and absence of `onclick=` in HTML) [US-02]
- [x] Button outcome text is inserted via `textContent`, `innerText`, or DOM text node — not `innerHTML` (verifiable: grep confirms no `innerHTML` usage in JS) [US-02]

#### Structural criteria
- [x] No external dependencies — page loads without network requests to CDNs or external APIs (Playwright: no failed network requests on load, no `<script src="http` or `<link href="http` in source) [phase]
- [x] `README.md` includes a one-liner on what the page is and how to open it [phase]
- [x] `AGENTS.md` reflects the static HTML page structure introduced in this phase [phase]

### Golden principles (phase-relevant)
- Quality checks are enforced: `no-silent-pass`, `no-bare-except`, `error-path-coverage`, `agents-consistency`
- Button outcomes MUST be rendered via `textContent` or equivalent safe DOM API, never `innerHTML`
