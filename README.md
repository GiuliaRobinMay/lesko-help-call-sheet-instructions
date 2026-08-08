# Lesko Help — Call Sheets

A member guide to building call sheets, built as a **paginated document** in
the Lesko Help house style.

## Contents

- `index.html` — the whole thing. Self-contained: all CSS and JS inline, no
  external requests, no build step, no dependencies.

## How it works

The guide is 13 short pages, shown one at a time — not one long scroll.

- **Page 01** cover
- **Page 02** contents — eleven questions, each linking to its answer
- **Pages 03–13** one answer per page

Navigation:

| Control | What it does |
| --- | --- |
| Contents rows | jump to that page |
| `☰ Contents` in the top bar | back to the index from anywhere |
| Prev / Next at the foot | move a page, labelled with the destination |
| `↑ Contents` / `↑ Top` | back up |
| Floating `↑` | appears after 400px of scroll |
| `←` `→` keys | previous / next page |
| `Esc` | back to contents |

Each page has a `#p01`…`#p13` hash, so pages are linkable and the browser
back button works. Printing expands every page with page breaks between them.

The contents list is generated at runtime from the pages themselves, reading
each `<article>`'s `data-q` (the question) and `data-nav` (the short label).
Add or remove an `<article class="sheet">` and the index, the page numbering
and the prev/next labels all follow automatically.

## Brand

Colours sampled directly from the Lesko Help document series:

| Token | Value | Use |
| --- | --- | --- |
| `--cream` | `#F9F6EB` | the sheet |
| `--band` | `#F4EBD4` | callouts, alternating table rows |
| `--navy` | `#0E1A2A` | card borders, table headers, buttons |
| `--ink` | `#2A3548` | body text |
| `--red` | `#E63946` | italic serif emphasis, mono labels, numbers |
| `--yellow` | `#FDC82F` | badges, chips, the `?` |
| `--blue` `--green` | `#2B3FA0` `#4FA84F` | suits, tints, semantics |

Card-suit tints (`--tint-blue/yellow/red/green`) fill the numbered cards, same
as the printed documents. Serif for display with red italic emphasis, sans for
body, mono for labels and running heads.

**Light only** — no dark mode, by request. The page paints its own background
so it holds on any host.

## The Problem Clarifier (page 06)

An interactive form whose questions are the seven clarifying questions from
page 05. Answering them generates a ready-to-paste request in three formats:

1. **AI Researcher** — a full prompt using the team's 14-column structure,
   plus an instruction not to invent contact details
2. **Questions Channel** — a short post
3. **Read out in class** — a script with the problem / ZIP / state checklist

### Privacy guard

The free-text fields are scanned for phone numbers, email addresses, Social
Security numbers, street addresses and card numbers. On a hit it names what it
found and **disables the copy button** until the text is removed. ZIP code and
city are treated as safe and never flagged.

The street-address check requires a capitalised street name, so ordinary
phrases like "2 bedroom apartment" or "3 new drive belts" don't trip it.

Everything is client-side; no data leaves the browser.

## Editing

| Change | Where |
| --- | --- |
| Colours | the `:root` block at the top of `<style>` |
| Add / remove / reorder a page | the `<article class="sheet">` elements — the index follows |
| A page's index question | that article's `data-q` |
| A page's prev/next label | that article's `data-nav` |
| The 14 columns | the `#p08` table, and the `COLUMNS` string in the script |
| Clarifier questions | the `<form id="clarifier">` markup |
| Generated wording | `buildAI()`, `buildPost()`, `buildClass()` |

Page numbers in the running feet are written into the markup; if you reorder
pages, update the `.pg` values and the `id`s to match.
