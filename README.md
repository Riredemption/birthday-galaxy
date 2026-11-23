# 3D Particle Birthday Card

A single-page, no-build interactive birthday card. Hand gestures drive 3D particles, a birthday cake, a photo sphere, photo layout changes, blessing messages, and a poster generator.

Live demo: <https://riredemption.github.io/birthday-galaxy/?v=2>

## Features

- 3D particle countdown, fireworks, birthday text, and a particle cake
- Open your palm on the first cake stage to blow out the candles and enter the photo sphere
- Four photo sphere layouts: sphere, heart, wall, timeline
- Timeline layout auto-plays photos in chronological order
- Pinch to grab a photo, move your hand closer/farther to zoom
- Upload photos and edit the date and caption of each one
- Mark highlight photos, reorder, delete, import/export configuration
- Custom greeting lines and orbiting blessing messages
- Poster generator with selectable templates, backgrounds, styles, and resolution
- Mouse/touch fallback and an automatic demo mode

## Run Locally

Open `index.html` directly, or serve it locally (recommended for camera access):

```bash
python -m http.server 8780
```

Then visit:

```text
http://127.0.0.1:8780/index.html
```

## Gestures

| Gesture | Action |
|---|---|
| Open palm | Start the flow; blow out candles; enter the photo sphere |
| Fist | Return from the photo sphere to the cake |
| Pinch | Grab a photo |
| Victory sign | Switch photo layout |
| Move closer/farther | Zoom the grabbed photo |

Camera access requires HTTPS or `localhost`, and the browser must be allowed to use the camera.

## Buttons

- **Photos**: upload photos, edit date/caption, set highlights, reorder, delete
- **Layout**: manually switch photo layouts
- **Poster**: open the poster editor, choose template/background/style, export PNG
- **Demo**: run the automatic presentation flow
- **Settings**: edit greeting lines, orbiting blessings, and sound effects

## Poster Templates

- Star ring cosmos
- Heart memories
- Film timeline
- Magazine cover
- Constellation links

Backgrounds: built-in nebula, blurred photo, or custom upload.

## Personalization

All user-facing text, brand colors, and photos live in the page and are editable through the UI:

1. **Settings** — greeting lines (up to 12 characters each) and orbiting blessings
2. **Photos** — upload images, then edit date, caption, highlight, and order
3. **Poster** — title, template, background, style, then download

Photos are stored in browser `localStorage`; use **Export/Import configuration** to move or back up a setup.

## Photo Guidelines

- Format: JPG, PNG, or WebP
- Shape: portrait 3:4 works best (for example 1080x1440); square also works, landscape images get cropped
- Size: about 2 MB per image or less, 6-12 images total for stable frame rates
- To hard-code photos into the repository, place them in `photos/` as `01.jpg`, `02.jpg`, ... and update the default configuration

## Compatibility Notes

- Best on current Chrome, Edge, or other Chromium-based browsers
- WeChat's in-app browser blocks camera access: the page shows a notice and falls back to buttons
- iOS Safari supports the buttons and touch flow; gesture tracking support varies
- On mobile, rendering DPR is capped, the hand model switches to the lite variant, and inference is throttled; if frame time stays high, resolution drops one more step automatically
- MediaPipe assets are loaded from a CDN, so an internet connection is required for gestures

## Tech

- HTML Canvas 2D rendering
- MediaPipe Hands for gesture tracking
- Web Audio for sound effects
- Canvas-based poster export

## Deploy with GitHub Pages

1. Push this repository to GitHub
2. Open `Settings` → `Pages`
3. Source: `Deploy from a branch`
4. Branch: `main`, folder: `/ (root)`
5. Save and wait for the site URL

## License

MIT
