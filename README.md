# N2 Media · Sales Pitch Deck

Cinematic sales-pitch deck for **N2 Media Cultural Creative Co., Ltd. (恩次方文化創意)**.

A self-contained static site — pure HTML, CSS, and JavaScript. No build step, no dependencies to install.

---

## Quick start

### View locally
Just open `index.html` in any modern browser. That's it.

If you prefer a local server (recommended — some browsers restrict local file access):
```bash
npx serve .
# or
python3 -m http.server 8000
```
Then visit `http://localhost:8000`.

### Deploy to GitHub Pages
1. Push this folder to a GitHub repo (any name, e.g. `n2-media-pitch-deck`).
2. In the repo: **Settings → Pages**.
3. Source: **Deploy from a branch**.
4. Branch: `main` / Folder: `/ (root)`.
5. Click **Save**. Your site goes live in ~1 minute at:
   `https://<your-username>.github.io/<repo-name>/`

### Deploy to Vercel / Netlify
Drag this folder into either dashboard. Both auto-detect static sites — no configuration needed.

---

## File structure

```
.
├── index.html          # The deck. All styles & content inline.
├── deck-stage.js       # Custom <deck-stage> web component (slide nav + scaling)
├── assets/
│   ├── *.png           # Cinematic photography (numbered 01–17)
│   ├── optimized/      # WebP versions used by the live deck for faster loading
│   ├── logos/          # Client/partner logos (slide 11b)
│   └── photos/         # Additional photography library (not currently wired in)
└── README.md
```

---

## Navigation

- **← / →** arrow keys — previous / next slide
- **Spacebar** — next slide
- **Tap left/right thirds** on mobile — previous / next
- Slide counter sits in the bottom-right corner

---

## Editing the deck

The deck is a single HTML file with all styles inline. To change content:

1. Open `index.html` in your editor (VS Code, Cursor, Claude Code, Codex, etc.)
2. Each slide is a `<section>` element inside `<deck-stage>`. They're commented (`<!-- 01 · COVER -->`, `<!-- 02 · OFFER -->`, etc.)
3. Edit text directly inside the section.
4. Save → refresh browser.

### Swapping photos
Photos are set via inline `background-image: url('assets/optimized/...')` declarations. Change the filename to swap. Keep the original PNGs in `assets/` as source-quality backups, then export a matching WebP into `assets/optimized/` for the live deck.

### Swapping client logos (slide 11b)
Logos live in `assets/logos/`. The slide 11b `.logo-grid` block has 14 `<div class="logo-cell"><img ...></div>` entries — replace the `src` attribute with the logo filename you want.

### Tweaks panel
Press the Tweaks toggle (visible in dev) to adjust accent color, background, font, grain, and saturation live. Settings persist to `localStorage`.

---

## Tech notes

- Built with the custom `<deck-stage>` web component (in `deck-stage.js`) — handles slide navigation, viewport-fit scaling, and keyboard input.
- Fixed slide canvas: **1920 × 1080**. Component scales it to fit any viewport.
- Print-ready: `Cmd/Ctrl+P` outputs one PDF page per slide.
- Fonts loaded from Google Fonts: Noto Serif TC, Noto Sans TC, Bodoni Moda.
- No JS frameworks. No bundler. Just files.

---

## License

Proprietary — © N2 Media Cultural Creative Co., Ltd. All rights reserved.
