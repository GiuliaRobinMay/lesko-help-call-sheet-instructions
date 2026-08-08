# Lesko Help — Your Call Sheet

A single-page guide for LeskoHelp members: what a call sheet is, how to get one, and
what to do with it. Same playful playing-card design as the Grant Roadmap and
Onboarding apps.

Open `index.html` in a browser. No build step, no server, no dependencies.

## What's on the page

| # | Card | What it covers |
|---|------|----------------|
| 01 | 📋 What a call sheet is | A list of places to phone, built from ZIP code + one problem |
| 02 | ☝️ One problem = one call sheet | The golden rule, with a good and a bad example |
| 03 | 🎯 Get clear before you ask | The seven questions to answer first |
| 04 | ✍️ Let us write your request | **The tool** — see below |
| 05 | 🗺️ Three ways to get your call sheet | Class · AI Researcher · Questions Channel |
| 06 | ✅ What a good call sheet has | The 14 columns, asked for 25 organizations |
| 07 | 🔍 Check it before you call | AI gets phone numbers wrong ~1 in 3 times |
| 08 | ☎️ What to say when you call | Four questions, plus a call log |
| 09 | 🔁 Then do it again | Repetition is the method |
| 10 | 🔒 Keeping yourself safe | What never to post, avatars, scam red flags |

A **quick-jump card** sits under the header so members can go straight to what they
need instead of scrolling, and a back-to-top button appears once they've scrolled.

## The tool — "Let us write your request for you"

Card 04 is interactive. A member answers the same seven questions from card 03, and the
page builds their request in three formats, switched by tabs:

- **🤖 For the AI** — the full prompt, using the team's 14-column structure, with an
  added instruction not to invent phone numbers, emails or links
- **💬 For the Questions Channel** — a short, tidy post
- **🎤 To say in class** — a script with the problem / ZIP / state checklist

### The privacy guard

Before anything can be copied, the free-text answers are checked for phone numbers,
email addresses, Social Security numbers, street addresses and card numbers. If one
turns up, the page says what it found and **disables the copy button** until it's
removed. ZIP code and city are treated as safe and never flagged.

The street check requires a capitalised street name, so everyday phrases like
"2 bedroom apartment" or "3 new drive belts" don't trip it.

Everything runs in the member's own browser. Nothing is sent anywhere.

## Adding the video

The recording isn't wired up yet. When you have the URL, open `index.html`, find
`VIDEO_URL` near the top of the `<script>` at the bottom, and paste it in:

```js
var VIDEO_URL = "";   // YouTube, Vimeo, Loom, Wistia or a direct .mp4
```

Share links are converted into a player automatically. Left empty, the slot shows a
placeholder that links through to a live Call Sheet Class, so the page never looks
broken while you're still recording.

## Links used

All buttons point at the existing spaces in the community:

- Call Sheet Classes — `/spaces/24440881/events`
- Lesko AI Researcher — `/spaces/24461105/page`
- Questions Channel — `/spaces/11054387/feed`
- Call & Application Classes — `/spaces/24366189/events`

## Design

Shared LeskoHelp house style, matching the Grant Roadmap and Onboarding apps:

- Paper `#faf6ec`, ink `#0e1a2b`, and the four suit colours —
  blue `#2c3fa0`, red `#e63946`, yellow `#fdc830`, green `#4fa84f`
- Georgia serif headings, mono labels, hard 2px borders with offset shadows,
  cards tilted a fraction of a degree
- Big yellow `?` marks in the background, emoji as section markers
- Works down to small phones; respects `prefers-reduced-motion`

## Files

```
index.html     the whole app
netlify.toml   static hosting, no build
EMBED.md       how to put it on a Mighty Networks page
```
