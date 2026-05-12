# SYSTEM EXIT: IT Dev Team

**End of an Era** — a single-file static landing page for an IT dev team farewell: terminal / git UI, optional BGM, boot sequence, and an alumni story carousel. Primary copy is **Indonesian** (`lang="id"`).

---

## What’s inside

| Area | Description |
|------|-------------|
| **Intro** | Audio on/off gate, then a typed boot overlay |
| **Hero** | `images/hero.png` background animation + `images/headline.png` |
| **Story** | Git-style “commit” window + faux `event_config.json` (when / where / map) |
| **Alumni** | Swiper 11 slider — WebP portraits under `images/alumnis/` |
| **RSVP** | WhatsApp CTA (replace placeholder in `index.html`) |

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
    └── backsound.ogg       # Secondary <source> for broader codec support
```

---

## Tech stack

- **HTML + CSS + JavaScript** — no build step
- **[Swiper](https://swiperjs.com/) 11** — CSS + JS from jsDelivr
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

1. **RSVP** — Set the real link: search for `wa.me/NOMOR_WHATSAPP_LU` in `index.html`.
2. **Event** — Edit date, location, and `map_url` in the JSON-style block.
3. **Alumni** — Update names, taglines, roles, stories, and `images/alumnis/*` paths if files change.
4. **Boot text** — Edit the boot line strings in the `<script>` at the bottom of `index.html`.
5. **Accessibility** — Keep meaningful `alt` text on images when you swap photos.

---

## Browser support

Modern evergreen browsers (Chrome, Firefox, Safari, Edge). CSS animations and `prefers-reduced-motion` are used; ember animation is toned down when reduced motion is requested.

---

## License

Add a license when you open the repository (e.g. MIT), especially if others will fork the design.
