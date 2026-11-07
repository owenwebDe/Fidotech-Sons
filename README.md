# Fidotech & Sons Energy Nig Limited

Demo website for **Fidotech & Sons Energy Nig Limited** (RC 8375176) — solar
installation, electrical wiring, CCTV, equipment supply and general site contracts.
Angwa Tiv, Pyakasa — behind Lugbe, off Airport Road, Abuja FCT.

Built by [IconEdge Technologies LTD](https://github.com/owenwebDe).

## Running it

Static HTML. No build step, no dependencies to install.

```bash
# any static server, e.g.
npx serve .
```

Then open `http://localhost:3000`.

Deploying: point Vercel, Netlify or any static host at this folder — there is no
build step. `vercel.json` and `netlify.toml` are both included and only set cache
and security headers; neither is required for the site to work.

## What is in here

| Path | What it is |
|---|---|
| `index.html` | the page |
| `credits.html` | photograph credits and licences |
| `assets/app.css` | all styling |
| `assets/app.js` | motion layer — Lenis smooth scroll, GSAP ScrollTrigger, SplitText |
| `assets/glass.js` | liquid-glass refraction for the nav, the scroll cue and the rail buttons |
| `assets/hero3d.js` | the hero's WebGL solar field (Three.js, ES module) |
| `assets/img/` | photographs (WebP) |

Libraries load from CDN at pinned versions: GSAP 3.13.0, Lenis 1.1.18, Three.js 0.169.0.
Fonts are Bricolage Grotesque and Geist from Google Fonts.

## The look

Dark theme, square corners, one bright colour.

| Token | Value | Job |
|---|---|---|
| `--paper` | `#070A0E` | the ground |
| `--paper-2` | `#0C1118` | the raised supply band |
| `--paper-3` | `#151B24` | panels and image placeholders |
| `--ink` / `--ink-2` | `#F4F6F8` / `#8B96A4` | text and muted text |
| `--brand` | `#2F6FD0` | **ambient only** — the bloom, the bars, the solar field |
| `--accent` | `#22E0C8` | **everything bright** — buttons, the highlighted word, eyebrows, numbers, hovers |

Two rules hold this together and are worth keeping if you edit it:

1. **Nothing is rounded.** `--r` and `--r-lg` are both `0`, and no rule sets a
   radius. Buttons, cards, the bento panels, the icon chips, the arrows and the
   menu button are all square.
2. **The navy never carries small text.** At 4:1 on this ground it is a graphic
   colour. Anything the eye has to read at 12–14px uses cyan, which is 11.7:1.
   For the same reason the primary button takes black text, not white — white on
   cyan is 1.5:1 and unreadable.

The primary button has a specular sweep that crosses its face on hover; the hero
button and the phone action bar also run it on their own every eight seconds.

## The page

| Section | What it carries |
|---|---|
| Hero | the h1, the RC number, the two actions, the WebGL solar field |
| What we do | the five service lines, as a horizontal rail that runs on its own |
| What we supply | the dealer arm — six equipment lines as a bento |
| Installations | four photographs of finished work |
| How it runs | four steps, with the photograph changing as you scroll |
| The company | the registration, the address, the FCT-wide reach |
| Contact | WhatsApp, phone, email, address |

The services rail scrolls itself, speeds up with the page, pauses on hover and on
keyboard focus, and can be dragged. It also responds to the two arrow buttons.

The supply bento is two columns on a phone and four on a desktop. Panels 01 and 06
carry `.supply__item--wide` and span two columns at every width; the four narrow
panels drop their description below 1040px, which is what keeps the band about one
screen tall on a phone instead of six stacked blocks.

## Motion

The page honours `prefers-reduced-motion`. On a machine with that set — which includes
any Windows install with **Settings → Accessibility → Visual effects → Animation
effects** turned off — the page renders fully but still: no smooth scroll, no reveals,
and the hero shows one rendered frame of the solar field instead of animating it.

To preview the full motion on such a machine, add `?motion=on`:

```
http://localhost:3000/?motion=on
```

The WebGL hero also steps itself down automatically: on a machine with no GPU
(software rendering) or below ~30fps it renders a single frame and stops, so it
never stutters.

## Photographs are placeholders

**Every photograph in `assets/img/` is a licensed stand-in, not Fidotech's own work.**
They are credited in `credits.html` under CC BY / CC BY-SA licences, and all of them
were shot in Europe or America. Replace them with Fidotech's real job photographs
before this goes live as the company's site — that single change does more for the
page than anything else in this repo.

## Still to confirm with the client

- Logo and brand colours — the page currently uses a sun-and-bolt mark in navy and
  cyan, and a "Fidotech & Sons" wordmark
- Prices — neither the services nor the supply list carries a figure
- Which inverter, battery and panel brands they actually stock, if they want them named
- Year the company started trading (the page deliberately claims no founding year)
- Whether to show NEMSA or other registrations alongside the RC number
