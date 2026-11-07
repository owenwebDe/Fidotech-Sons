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

## The page

| Section | What it carries |
|---|---|
| Hero | the h1, the RC number, the two actions, the WebGL solar field |
| What we do | the five service lines, as a horizontal rail that runs on its own |
| What we supply | the dealer arm — six equipment lines on the dark band |
| Installations | four photographs of finished work |
| How it runs | four steps, with the photograph changing as you scroll |
| The company | the registration, the address, the FCT-wide reach |
| Contact | WhatsApp, phone, email, address |

The services rail scrolls itself, speeds up with the page, pauses on hover and on
keyboard focus, and can be dragged. It also responds to the two arrow buttons.

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

- Logo and brand colours — the page currently uses a sun-and-bolt mark in blue and
  amber, and a "Fidotech & Sons" wordmark
- Prices — neither the services nor the supply list carries a figure
- Which inverter, battery and panel brands they actually stock, if they want them named
- Year the company started trading (the page deliberately claims no founding year)
- Whether to show NEMSA or other registrations alongside the RC number
