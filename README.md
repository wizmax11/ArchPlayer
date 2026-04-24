<div align="center">

<img src="archplayer-logo.svg" width="72" height="72" alt="ArchPlayer Logo">

# ArchPlayer

**A minimal, local-first video player. One HTML file. No install. No server.**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=flat-square)](LICENSE)
[![HTML](https://img.shields.io/badge/Built%20with-HTML%2FCSS%2FJS-7eb8f7?style=flat-square)]()
[![No dependencies](https://img.shields.io/badge/Dependencies-None-6ee7b7?style=flat-square)]()
[![Single file](https://img.shields.io/badge/Size-Single%20File-a78bfa?style=flat-square)]()

[Download](https://github.com/YOUR_USERNAME/archplayer/releases/latest) · [Live Demo](https://YOUR_USERNAME.github.io/archplayer) · [Report a Bug](https://github.com/YOUR_USERNAME/archplayer/issues)

</div>

---

## What is ArchPlayer?

ArchPlayer is a sleek, browser-based video player that runs entirely from a single HTML file. Drop it in a folder, open it in your browser, and play any video at native quality — no installation, no backend, no account required.

Everything is self-contained: the UI, the subtitle engine, the keyboard shortcuts. It uses your browser's native video decoder, so there is zero quality loss or transcoding.

---

## Features

- **Native quality playback** — no encoding or compression, your file plays as-is
- **Drag and drop** — drop a video file directly onto the player to open it
- **External subtitle support** — load `.srt` or `.vtt` files, adjust sync delay in real time
- **Playback speed control** — 0.25x to 2x, switchable on the fly
- **Picture in Picture** — pop the video into a floating overlay window
- **True fullscreen** — with auto-hiding controls and no UI chrome
- **Volume control** — slider with mute toggle and reactive icon
- **Info panel** — shows filename, resolution, duration, and file size
- **Keyboard shortcuts** — full keyboard control (see below)
- **Zero dependencies** — pure HTML, CSS, and vanilla JavaScript

---

## Getting Started

**Option 1 — Download the file directly:**

1. Download [`ArchPlayer.html`](https://github.com/YOUR_USERNAME/archplayer/releases/latest)
2. Open it in Chrome, Firefox, Edge, or any modern browser
3. Drop a video onto the player or click "Open file"

**Option 2 — Clone the repo:**

```bash
git clone https://github.com/YOUR_USERNAME/archplayer.git
cd archplayer
# open ArchPlayer.html in your browser
```

No build step. No `npm install`. Just open the file.

---

## Supported Formats

ArchPlayer supports any format your browser can decode natively:

| Format | Chrome | Firefox | Edge | Safari |
|--------|--------|---------|------|--------|
| MP4 (H.264) | ✓ | ✓ | ✓ | ✓ |
| MP4 (H.265/HEVC) | ✓* | — | ✓* | ✓ |
| WebM (VP8/VP9) | ✓ | ✓ | ✓ | ✓ |
| WebM (AV1) | ✓ | ✓ | ✓ | — |
| MKV | ✓ | — | ✓ | — |
| OGG | ✓ | ✓ | ✓ | — |

*Requires hardware decoder support.

**Subtitle formats:** `.srt`, `.vtt`

---

## Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `Space` | Play / Pause |
| `F` | Toggle fullscreen |
| `←` | Rewind 10 seconds |
| `→` | Forward 10 seconds |
| `↑` | Volume up |
| `↓` | Volume down |
| `M` | Toggle mute |
| `S` | Toggle subtitles |
| `P` | Picture in Picture |

---

## Customization

ArchPlayer is designed to be easy to tweak. Open `ArchPlayer.html` in any text editor and find the `<style>` block at the top.

### Change the accent color

Find the `:root` block and update `--accent`:

```css
:root {
  --accent: #7eb8f7;    /* default: soft blue */
  /* try: #c084fc (purple), #34d399 (green), #fb923c (orange) */
}
```

### Change subtitle size and style

Find the `.subtitle-text` rule:

```css
.subtitle-text {
  font-size: 22px;      /* increase for bigger text, e.g. 26px or 30px */
  font-weight: 500;     /* 300 = light, 400 = normal, 600 = bold */
  color: #ffffff;       /* subtitle color */
  line-height: 1.65;    /* line spacing */
}
```

### Move subtitles higher or lower

Find the `.subtitle-overlay` rule:

```css
.subtitle-overlay {
  bottom: 80px;   /* increase to move subtitles higher, decrease to lower */
}
```

### Change default playback speed

In the HTML, find the speed menu items and mark your preferred default as `active`:

```html
<div class="speed-item" data-val="1.25">1.25x</div>
<div class="speed-item active" data-val="1">1x</div>  <!-- change "active" to your preferred speed -->
```

Then in the JavaScript, add near the top:

```javascript
video.playbackRate = 1.25;   // set your preferred default rate
speedBtn.textContent = '1.25x';
```

### Change progress bar color

```css
.progress-fill {
  background: var(--accent);  /* inherits accent color */
  /* or set a fixed color: background: #ff6b6b; */
}
```

### Adjust control bar height and padding

```css
.controls-wrap {
  padding: 0 20px 16px;   /* top right bottom — increase bottom for more breathing room */
}
```

---

## Project Structure

```
archplayer/
├── ArchPlayer.html          # The player — the whole thing
├── archplayer-logo.svg      # Main logo (120px)
├── archplayer-favicon.svg   # Favicon (32px)
├── index.html               # Showcase website
├── LICENSE
└── README.md
```

---

## Philosophy

ArchPlayer follows a simple rule: **one file, nothing hidden**.

There is no build system to configure, no package to update, no telemetry. The entire source is readable in a text editor. You can audit it in under ten minutes. Fork it, strip it, or build on top of it — the license lets you do anything.

---

## Contributing

Pull requests are welcome. Keep changes focused and avoid adding external dependencies. The goal is to keep the player as a single portable file.

1. Fork the repository
2. Create a branch: `git checkout -b feature/your-feature`
3. Make your changes in `ArchPlayer.html`
4. Open a pull request with a short description of what changed and why

For bugs or feature requests, open an [issue](https://github.com/YOUR_USERNAME/archplayer/issues).

---

## License

MIT — do whatever you want. See [LICENSE](LICENSE) for the full text.

---

<div align="center">
Made with care. Runs anywhere.
</div>
