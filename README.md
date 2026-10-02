# NovaBoard OS

An interactive whiteboard and presentation workspace that runs in your browser from a single HTML file. No build step, no backend, no account.

**Live demo:** https://abhiraj1121.github.io/novaboard/

> Looking for the Windows / Linux desktop apps? See [README-DESKTOP.md](README-DESKTOP.md).

---

## Features

- **Drawing tools:** ball pen, highlighter, calligraphy pen and neon pen, plus eraser, undo / redo and erase-all
- **Colors and widths:** preset swatches, custom color picker and a width slider
- **Shapes:** 2D (line, arrow, rectangle, rounded rectangle, ellipse, star) and 3D (cube, cylinder, sphere, pyramid) with a rotate handle
- **Multi-page boards:** add, delete and drag-to-reorder pages from the thumbnail sidebar, each with its own background
- **PDF import and export:** open a PDF as slides, annotate it, and export the whole board back to PDF
- **Floating widgets:** timer / stopwatch, scientific calculator and laser pointer
- **Workspace comfort:** collapsible top bar, persistent clock, fullscreen mode and swappable left / right docks
- **Recent sessions:** boards are listed on the home screen and stored locally in your browser

## Quick start

### Option 1: Open the file

1. Download `novaboard.html`.
2. Double-click it to open in a modern browser (Chrome, Edge, Firefox or Safari).

The web version loads its libraries from public CDNs, so it needs an internet connection the first time. For a fully offline experience, use the [desktop app](README-DESKTOP.md).

### Option 2: Host it

Upload `novaboard.html` (renamed to `index.html`) to any static host, such as GitHub Pages, Netlify or Cloudflare Pages.

**GitHub Pages:** go to *Settings → Pages*, choose your branch and the root folder, and save.

## Tech stack

| Purpose | Library |
| --- | --- |
| UI | React 18 (UMD) + Babel Standalone |
| Styling | Tailwind CSS |
| Drawing canvas | fabric.js 5.3 |
| PDF import | pdf.js 3.11 |
| PDF export | jsPDF 2.5 |
| Fonts | Space Grotesk, JetBrains Mono |

## Your data

Everything stays on your device. Session info is saved in your browser's `localStorage` under the key `novaboard.sessions.v1`. Nothing is uploaded anywhere. Clearing your browser data removes your saved sessions, so export important boards to PDF.

## Browser support

Current versions of Chrome, Edge, Firefox and Safari. A mouse, touch screen or pen tablet all work for drawing.

## Contributing

Issues and pull requests are welcome. Please open an issue first to discuss large changes.

## License

Released under the [MIT License](LICENSE).

## Contact

**Cognix Studio**: contactcognixstudio@outlook.com
Website: https://abhiraj1121.github.io/novaboard/
