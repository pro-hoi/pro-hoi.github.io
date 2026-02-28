# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a static academic project page for the paper **"Pro-HOI: Perceptive Root-guided Humanoid-Object Interaction"** — a robotics research paper on humanoid loco-manipulation deployed on a Unitree G1 robot. The site is hosted on GitHub Pages (`pro-hoi.github.io`).

## Development

No build step — this is a plain HTML/CSS/JS site. Preview locally with any static file server:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

To deploy, commit and push to the `main` branch; GitHub Pages serves it automatically.

## Structure

- `index.html` — single-page site; all content and inline styles live here
- `static/css/index.css` — custom styles (Bulma overrides, publication-specific classes)
- `static/js/index.js` — Bulma carousel/slider init and interpolation image preloader (largely boilerplate from Nerfies template)
- `static/videos/` — MP4/MOV files referenced inline in the HTML (`teaser_new.mp4`, `prohoi_comp.mp4`, plus experiment clips)
- `static/images/` — institution logos (`teleai.png`, `zju.png`, `ustc.png`, `shtech.png`) and paper figures (`pipeline.png`, etc.)
- `static/paper/HOI_RSS.pdf` — the paper PDF

## Key Conventions

- **Layout engine**: Bulma CSS (v0.9.x) — use Bulma utility classes (`is-max-desktop`, `columns`, `column`, `section`, etc.) for layout changes.
- **Video grid**: The experiment video section uses a custom CSS Grid (`.grid-container`, `.video-item`) defined inline in `index.html`, not Bulma's grid. Width is `60vw`, negatively offset with `margin-left: calc(50% - 30vw)`.
- **Hero section**: Fullscreen video background (`./static/videos/teaser_new.mp4`) with CSS filter (`blur/brightness/contrast`) and a dark overlay `div`. Institution logos are absolutely positioned bottom-right inside the hero.
- **Accent color**: `#e63946` (red) used for `.highlight-pro` spans in the title.
- **Fonts**: Google Sans (titles/authors), Noto Sans (body), Castoro — loaded from Google Fonts CDN.
- **Dependencies loaded from CDN**: jQuery 3.5.1, Academicons. Everything else is vendored in `static/`.
