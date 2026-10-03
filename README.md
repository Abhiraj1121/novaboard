# NovaBoard OS

An interactive smartboard-style whiteboard and presentation workspace that runs in your browser from a single HTML file. No build step, no backend, no account.

**Live demo:** https://abhiraj1121.github.io/novaboard/

> Looking for the Windows / Linux desktop apps? See [README-DESKTOP.md](README-DESKTOP.md).

---

## What's new in 2.0

- **Auto-save with crash recovery:** boards are saved continuously in your browser (IndexedDB) and restored if the page closes unexpectedly
- **`.novaboard` files:** save a whole workspace to a file and open it again later
- **Copy and paste:** copy selected objects and paste them on any page (Ctrl/Cmd + C / V)
- **Image upload and sticky notes**
- **PDF import progress overlay** and clearer save-status and error messages
- Boot sound and polish throughout

## Features

- **Drawing tools:** ball pen, highlighter, calligraphy pen and neon pen, plus eraser, undo / redo and erase-all
- **Colors and widths:** preset swatches, custom color picker and a width slider
- **Shapes:** 2D (line, arrow, rectangle, rounded rectangle, ellipse, star) and 3D (cube, cylinder, sphere, pyramid)
- **Multi-page boards:** add, delete and drag-to-reorder pages from the thumbnail sidebar, each with its own background
- **PDF import and export:** open a PDF as slides, annotate it, and export the whole board back to PDF
- **Floating widgets:** timer / stopwatch, scientific calculator and laser pointer
- **Workspace comfort:** collapsible top bar, persistent clock, fullscreen mode and swappable left / right docks
- **Recent sessions** listed on the home screen

## Quick start

**Open it:** download `index.html` and double-click it in a modern browser (Chrome, Edge, Firefox or Safari). The web version loads its libraries from public CDNs, so it needs an internet connection. For a fully offline experience, use the [desktop app](README-DESKTOP.md).

**Host it:** upload `index.html` to any static host (GitHub Pages, Netlify, Cloudflare Pages). On GitHub Pages: *Settings → Pages*, pick your branch and the root folder, then save.

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

Everything stays on your device. Boards are auto-saved in your browser's IndexedDB, and the recent-sessions list uses `localStorage`. Nothing is uploaded anywhere. Clearing your browser data removes saved boards, so use **Save** to keep a `.novaboard` file or export to PDF for anything important.

## Browser support

Current versions of Chrome, Edge, Firefox and Safari. Mouse, touch screen and pen tablet all work for drawing.

## Contributing

Issues and pull requests are welcome. Please open an issue first to discuss large changes.

## License

Released under the [MIT License](LICENSE).

## Contact

**Cognix Studio**: contactcognixstudio@outlook.com
Website: https://abhiraj1121.github.io/novaboard/
