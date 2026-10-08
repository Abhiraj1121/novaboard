# NovaBoard OS

An interactive smartboard-style whiteboard and presentation workspace that runs in your browser from a single HTML file. No build step, no backend, no account.

**Live demo:** https://abhiraj1121.github.io/novaboard/

> Looking for the Windows / Linux desktop apps? See [README-DESKTOP.md](README-DESKTOP.md).

---

## What's new in 3.0

- **Futuristic material redesign:** layered glass surfaces, elevation, glow accents and an animated aurora home screen
- **Settings (home screen and board top bar):** organiser / school name, your name, tagline and profile picture; dark, light or system mode; 8 themes plus a custom accent colour; glass blur, corner roundness, interface size and animation controls; export / import / reset settings
- **11 new smart tools** (Tools menu): Live Poll, Scoreboard, Name Picker, Group Maker, Noise Meter, Lesson Agenda, QR Code, Unit Converter, Analog Clock, Protractor and Screen Shade
- **PDF pan & zoom:** with the Select arrow, drag empty space to move the page and pinch with two fingers (or Ctrl + wheel, or the ± buttons) after clicking Unlock PDF in the top bar (PDFs start locked) to zoom 50–600%; Shift + drag still box-selects
- All 2.x features (drawing, shapes, pages, PDF, widgets, auto-save, `.novaboard` files) are unchanged

## What's new in 2.0

- **Auto-save with crash recovery:** boards are saved continuously in your browser (IndexedDB) and restored if the page closes unexpectedly
- **`.novaboard` files:** save a whole workspace to a file and open it again later
- **Copy and paste:** copy selected objects and paste them on any page (Ctrl/Cmd + C / V)
- **Image upload and sticky notes**
- **PDF import progress overlay** and clearer save-status and error messages
- Boot sound and polish throughout

## AI Assistant (optional, free)

Open **Tools → AI Assistant** after adding a free API key in **Settings → AI**. Pick a provider:

- **Google Gemini:** create a key at <https://aistudio.google.com/apikey> (Google account, no card).
- **Groq:** create a key at <https://console.groq.com/keys> (no card).
- **OpenRouter:** create a key at <https://openrouter.ai/keys>. NovaBoard uses its `openrouter/free` router, which picks a free model that fits the request (about 20 requests a minute).

Free tiers are rate-limited, and the provider may keep or learn from requests, so avoid private student data. The assistant offers a chat, one-click quiz / lesson outline / key terms / discussion prompts added to the board as sticky notes, and page tools that send an image of the current page to explain it, summarize it, solve the math on it or read the handwriting. Keys are stored only in your browser and are never included in settings exports. Nothing is sent unless you use an AI feature.

## Live Share (one-way, no server)

Open **Tools → Live Share → Start sharing** to get a 6-character passcode. On any other device, open NovaBoard, choose **Join live board** on the home screen and type the code. The viewer sees the host's board update live and cannot draw. Boards travel directly between the two browsers (WebRTC via PeerJS); only the initial handshake uses PeerJS's free public broker, so both devices need internet. Some strict school or office networks block peer-to-peer connections. Anyone with the code can watch, so end the session when you are done.

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
| QR codes | qrcode.js 1.0 |
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
