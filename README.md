# SYSTEM EXIT: IT Dev Team

**End of an Era** — a single-file static landing page for an IT dev team farewell: terminal / git UI, optional audio, typed boot overlay, alumni story carousel, and an in-page RSVP confirmation flow. Primary copy is **Indonesian** (`lang="id"`).

---

## What’s inside

| Area | Description |
|------|-------------|
| **Intro** | Audio on/off gate, then a typed boot overlay (`#boot-screen`) |
| **Hero** | `images/hero.png` background animation + `images/headline.png` |
| **Story** | Git-style “commit” window + faux `event_config.json` (when / where / map) |
| **Alumni** | Swiper carousel — 8 slides with WebP portraits under `images/alumnis/` |
| **RSVP** | **Confirm Attendance** opens a 1s loading modal, then a thank-you modal with banner, message, and quote (no external link) |
| **Effects** | Floating ember particles (disabled when `prefers-reduced-motion: reduce`) |

### Audio

| Track | When it plays |
|-------|----------------|
| `sounds/backsound.mp3` / `.ogg` | After boot finishes, **only** if the visitor chose **Ya, aktifkan suara** |
| `sounds/system_sound.mp3` / `.ogg` | Asset on disk for boot SFX; wire in `index.html` if you want sound during the boot overlay |

Browsers require a user gesture before audio; the intro prompt satisfies that for BGM.

### RSVP flow

1. Visitor clicks **Confirm Attendance** (`#btn-rsvp`).
2. Loading modal: `> processing farewell.sh...` (~1 second).
3. Thank-you modal: `images/alumnis/alumnis.webp`, thank-you copy, farewell quote, **Tutup** (or click backdrop / **Escape**).

Edit copy in the `#rsvp-thanks-modal` block and RSVP-related strings in the `<script>` section of `index.html`.

---

## Repository layout

```
end-of-an-era/
├── index.html              # All markup, embedded CSS, and JS
├── README.md
├── images/
│   ├── hero.png
│   ├── headline.png
│   └── alumnis/
│       ├── alumnis.webp    # RSVP thank-you banner
│       ├── anto.webp
│       ├── wiwit.webp
│       ├── cahyo.webp
│       ├── ridho.webp
│       ├── adam.webp
│       ├── azzy.webp
│       ├── syakur.webp
│       └── wafiy.webp
└── sounds/
    ├── backsound.mp3
    ├── backsound.ogg       # Secondary <source> for broader codec support
    ├── system_sound.mp3
    └── system_sound.ogg    # Optional secondary <source> for boot SFX
```

---

## Tech stack

- **HTML + CSS + JavaScript** — no build step
- **[Swiper](https://swiperjs.com/) 11** — CSS + JS from jsDelivr (alumni carousel, loop + autoplay)
- **[Google Fonts](https://fonts.google.com/)** — Montserrat, Fira Code

---

## Run locally

Use any static server so assets and audio load correctly (avoid opening `index.html` as `file://`):

```bash
cd end-of-an-era
npx --yes serve .
```

Alternatives: `python3 -m http.server 8080` or VS Code “Live Server”.

---

## Deploy (static hosting)

Upload the **`end-of-an-era`** folder contents (or the whole folder as site root) to **GitHub Pages**, **Cloudflare Pages**, **Netlify**, or any static host. Site root must be the directory that contains `index.html` next to `images/` and `sounds/`.

---

## Before publishing

1. **Event** — Edit date, location, and `map_url` in the JSON-style block inside `index.html`.
2. **Alumni** — Update names, taglines, roles, stories, and `images/alumnis/*` paths if files change (one slide per `<article class="swiper-slide">`).
3. **RSVP** — Adjust thank-you title, body text, quote, and `alumnis.webp` in `#rsvp-thanks-modal`; change loading label in `#rsvp-loading-modal` if needed.
4. **Audio** — Replace or add files under `sounds/`; keep `<source>` paths in sync. To play boot SFX during the overlay, add a `<audio id="boot-sound">` and call it from `runBootSequence()` when `bgmEnabled` is true.
5. **Boot text** — Edit the boot line strings in the `<script>` at the bottom of `index.html`.
6. **Accessibility** — Keep meaningful `alt` text on images when you swap photos; RSVP modals use `role="dialog"` and `aria-*` attributes.

---

## Browser support

Modern evergreen browsers (Chrome, Firefox, Safari, Edge). CSS animations and `prefers-reduced-motion` are used; ember animation is toned down when reduced motion is requested.

---

## License

Add a license when you open the repository (e.g. MIT), especially if others will fork the design.
