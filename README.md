# Dhanashala — landing page

A single-page marketing site for **Dhanashala**, built from the five-stage vision
document. The layout grammar (split hero → expandable business-unit cards →
"latest" list with save buttons → six-category benefits → closing CTA) follows
the bp careers page you referenced; the visual language is Dhanashala's own,
sampled from the supplied logo.

## Files

```
C:\web\
  index.html      the whole site — HTML + CSS + JS, no build step
  assets\         logo files cut from the supplied PNG
```

Open `index.html` directly in a browser. Nothing to install, nothing to compile.

## Brand

Colours were sampled from the logo artwork, not from the reference site:

| Token | Hex | Source |
|---|---|---|
| Primary emerald | `#0C7F35` | leaf midtone |
| Deep green / ink | `#07301A` | dark leaf + outline |
| Gold accent | `#F0B000` | sun disc / cradle |
| Gold for text | `#8A5E00` | darkened so numerals clear 4.5:1 |
| Warm paper | `#F7F5EE` | section background |
| Muted ink | `#5C7060` | captions — 4.9:1 on paper, 5.3:1 on white |

Type: **Outfit** (display) + **Source Sans 3** (body), from Google Fonts. The
wordmark in the logo is a bold geometric sans, so Outfit was chosen to sit
beside it rather than compete.

### Logo assets

The supplied file is a **stacked** lockup (emblem / rule / wordmark / tagline).
The header needs a horizontal one, so the following were cut from it with the
alpha channel preserved:

- `dhanashala-emblem.png` — the mark alone (582×414)
- `dhanashala-lockup-compact.png` — mark + wordmark, **no tagline** (used in header)
- `dhanashala-lockup-horizontal.png` — mark + wordmark + tagline
- `dhanashala-lockup-horizontal-white.png` — same, knocked out to white (footer)
- `dhanashala-tagline.png`, `dhanashala-tagline-gold.png` — the tagline
- `dhanashala-rule.png` — the gold divider bar
- `icon-512.png`, `apple-touch-icon.png`, `favicon-32.png`

## What is real and what is not

This page makes no invented claims. Specifically:

- **Stage statuses are visible and honest.** Stages 1–2 are marked *Available
  now*, stage 3 *In development*, stages 4–5 *Planned*. Change these in the
  markup if the real status differs.
- **Cohort rows are samples** and are labelled as such with a dashed note
  directly above the list. Replace with your live intake.
- **The expiry demo is a demonstration** of the stage-4 rule, not live portal
  data. The countdown is anchored to page load and will reach zero after 2d 14h.
- **No fake metrics, testimonials or partner logos** — none were invented, so
  the page reads quieter than most landing pages. That is deliberate.
- `hello@dhanashala.example` is a placeholder address. **Replace it before
  launch.** `.example` is a reserved TLD.

## Sections

1. **Header** — sticky, compact horizontal lockup
2. **Hero** — split: dark green promise panel + ivory "five stages" rail
3. **Why this exists** — your B.Tech account, against the three real problems
4. **Five stages** — accordion; each row expands to "what this stage is" and
   "what you walk away with", with a status chip
5. **Next cohorts** — sample programme rows with localStorage-persisted save
6. **What you get** — six benefit categories, three sub-items each
7. **Listings that close themselves** — dark band + interactive expiry demo
8. **Early access** — email capture (front-end only)
9. **Footer**

## Things that need wiring up before launch

- The early-access form is front-end only. Point the `submit` handler at your
  backend or a form service.
- Cohort save state lives in `localStorage` under `dhanashala.saved`. Swap for
  real accounts.
- The expiry countdown is hard-coded to a 2d 14h window in the inline script.
  In the portal this should be computed from each listing's `expires_at`.
- Google Fonts load from the network. Self-host them if the site must work
  fully offline.

## Accessibility and behaviour

- One `<h1>`; heading outline verified with no skipped levels
- Accordion rows are real `<button>`s with `aria-expanded` / `aria-controls`
  and explicit accessible names; chevron rotates 180° when open
- `scroll-padding-top` + `scroll-margin-top` so anchors clear the sticky header
- Skip link, visible focus rings, real labels on the email input
- `prefers-reduced-motion` disables the countdown interval and transitions
- Tested at 390, 900, 1080, 1440 px — no horizontal overflow at any width
- Body text meets WCAG AA (4.5:1) on every background; contrast computed and
  the palette adjusted to achieve it

## Reference

Layout rhythm borrowed from `careers.bp.com/customers-products`. No bp
colours, fonts, copy or imagery were copied — the reference supplied the
structure, the logo supplied the paint.
