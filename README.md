# Lesko Help — Call Sheets instruction page

A single-page guide for Lesko Help members on what a call sheet is, how to get
one, and how to work it.

## Contents

- `index.html` — the whole page. Self-contained: all CSS and JS are inline,
  no external requests, no build step. Open it in a browser or publish it as-is.

## What's on the page

1. **What a call sheet is** — plain-language definition, built from ZIP code +
   one problem.
2. **The golden rule** — one problem, one call sheet. Never combine.
3. **Step 1 — Get clear on your problem.** Contains the **Problem Clarifier**,
   an interactive form: answering the questions builds a ready-to-paste request
   in three formats (AI Researcher prompt, Questions Channel post, class
   script).
4. **Step 2 — Three ways to get a call sheet.** Call Sheet Classes, the AI
   Researcher app, the Questions Channel — with a recommended order for using
   all three.
5. **The 14 columns** a complete call sheet contains, matching the column set
   the team already uses.
6. **Step 3 — Check it before you call.** AI verification pass.
7. **Step 4 — Work the list.** Call prep, the four questions to ask on every
   call, and a call-log template.
8. **Step 5 — Do it again.** Repetition as the method.
9. **Protecting yourself** — what never to post, avatars, scam red flags.
10. **Bookmarking** your questions.
11. **Disclaimer** — AI can make mistakes; bring problems to a class.

## The privacy guard

The Problem Clarifier scans the free-text fields for phone numbers, email
addresses, Social Security numbers, street addresses and card/account numbers.
If it finds any, it shows a warning naming what it found and **disables the
copy button** until the text is removed. ZIP code and city are treated as safe
and are never flagged.

Everything runs client-side. No data leaves the browser.

## Editing

Common changes and where to make them:

| Change | Where |
| --- | --- |
| Colors | the `:root` token blocks at the top of the `<style>` |
| The 14 columns | the `#columns` table, and the `COLUMNS` string in the script |
| Clarifier questions | the `<form id="clarifier">` markup |
| Qualifier chips | the `#f-quals` chip list |
| Generated wording | `buildAI()`, `buildPost()`, `buildClass()` in the script |

The page ships light and dark palettes defined as tokens, so it renders
correctly whichever theme a member's device is set to.
