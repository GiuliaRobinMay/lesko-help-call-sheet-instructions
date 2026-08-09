# Lesko Help — Your Call Sheet

A single page for LeskoHelp members: what a call sheet is, why it matters, and the
three ways to get one. Same playful playing-card design as the Grant Roadmap and
Onboarding apps.

Open `index.html` in a browser. No build step, no server, no dependencies.

## Scope — please keep it this way

This page is **only about the call sheet itself**. It deliberately does not cover:

- **How to build a call sheet.** Members learn that in the Call Sheet Classes and the
  AI Workshops. Explaining it here would confuse people and duplicate the classes.
- **How to make the calls, or how to apply.** Those are separate sections of the
  onboarding.
- **What columns a call sheet should contain.** Also class material.

There is no request builder or application form on this page. If a member wants help
writing their request, the answer is to join a class, ask in the Questions Channel, or
use the AI Researcher — not to fill in a form here.

## What's on the page

| # | Card | What it covers |
|---|------|----------------|
| 01 | 📋 What a call sheet is | A list of places to contact, built from ZIP + state/city + one problem |
| 02 | ⭐ Why it matters so much | Built for you, help is local, turns "where do I start" into a list |
| 03 | ☝️ One problem = one call sheet | Never combine problems, with a good and a bad example |
| 04 | 🎯 Know what you're asking for | Seven questions to get clear, and the three things to bring |
| 05 | 🗺️ Three ways to get your call sheet | Class · AI Researcher · Questions Channel — try all three |
| 06 | 🙋 Asking for your call sheet | Never share personal details, don't be shy, avatars are fine, bookmark it |
| 07 | 🔁 Keep going | Come back, ask again, there's no limit |

Then a closing note that AI can make mistakes, and to bring anything that looks wrong
to a grant coach in a class.

A back-to-top button appears once a member has scrolled. There is no jump menu — the
page is short enough to read straight through, and a menu at the top read as clutter.

## Links used

All buttons point at the existing spaces in the community:

- Call Sheet Classes — `/spaces/24440881/events`
- Lesko AI Researcher — `/spaces/24461105/page`
- Questions Channel — `/spaces/11054387/feed`

They appear inside the "three ways" card and again as three buttons at the foot of the
page: Call Sheet Class (red) and Questions Channel (blue) side by side, with Ask the AI
(green) centred on its own row underneath.

## Design

Shared LeskoHelp house style, matching the Grant Roadmap and Onboarding apps:

- Paper `#faf6ec`, ink `#0e1a2b`, and the four suit colours —
  blue `#2c3fa0`, red `#e63946`, yellow `#fdc830`, green `#4fa84f`
- Georgia serif headings, mono labels, hard 2px borders with offset shadows,
  cards tilted a fraction of a degree
- Big yellow `?` marks in the background, emoji as section markers
- Works down to small phones; respects `prefers-reduced-motion`

### Two things worth copying back to the sibling apps

- `overflow-x:hidden` has to be on **`html`** as well as `body`, or the background
  `?` marks push a horizontal scrollbar. The other apps share this CSS.
- The file declares `<meta charset="utf-8">` so the emoji survive a host that serves
  no charset. Netlify sets the header, but nothing else guarantees it.

Also note: a button size modifier must not be called `.small` — `.step-txt .small`
already owns that name and wins on specificity, which silently turns the button into a
full-width block with muted text. It is called `.btn-sm` here.

## Files

```
index.html     the whole page
netlify.toml   static hosting, no build
EMBED.md       how to put it on a Mighty Networks page
```
