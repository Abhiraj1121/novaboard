# NovaBoard OS: Desktop Apps (v2.0.0)

Offline desktop builds of [NovaBoard OS](README.md) for Windows and Linux, packaged with Electron. All libraries and fonts are bundled, so no internet connection is needed.

## Downloads

| Platform | File | Notes |
| --- | --- | --- |
| Windows 10 / 11 (64-bit) | `NovaBoard-OS-Setup-2.0.0.exe` | Setup wizard installer |
| Linux, any distro (64-bit) | `NovaBoard-OS-2.0.0-x86_64.AppImage` | Portable, no install |
| Debian / Ubuntu / Mint (64-bit) | `NovaBoard-OS-2.0.0-amd64.deb` | Installs to the app menu |
| Source project | `novaboard-desktop-source.zip` | For developers |

---

## Windows

1. Run `NovaBoard-OS-Setup-2.0.0.exe`.
2. If Windows shows **"Windows protected your PC"**, click **More info → Run anyway**. The installer is not code-signed yet, so SmartScreen shows an "Unknown publisher" warning.
3. Follow the wizard: accept the license, choose the install folder, and finish. Desktop and Start Menu shortcuts are created.
4. Tick **Launch NovaBoard OS** on the last page to start the app.

**Uninstall:** *Settings → Apps → NovaBoard OS → Uninstall*. Your boards are kept unless you remove them yourself.

## Linux: AppImage

```bash
chmod +x NovaBoard-OS-2.0.0-x86_64.AppImage
./NovaBoard-OS-2.0.0-x86_64.AppImage
```

On Ubuntu 22.04 and newer you may need FUSE (`sudo apt install libfuse2`). If it fails to start because of sandbox restrictions, run it with `--no-sandbox`.

## Linux: Debian / Ubuntu (.deb)

```bash
sudo apt install ./NovaBoard-OS-2.0.0-amd64.deb
```

Launch **NovaBoard OS** from your app menu. To remove it: `sudo apt remove novaboard-os`.

---

## Good to know

- **Smartboard mode:** start fullscreen with `novaboard-os --fullscreen` (on Windows, add `--fullscreen` to the shortcut's target).
- **Auto-save:** boards are saved continuously inside the app's own data folder, so updating or reinstalling keeps them. On close, the app asks the page for one last save before exiting.
- **Save files:** *Save* opens a native dialog (starting in Documents) and writes a `.novaboard` file you can back up or move to another computer.
- **One window at a time:** a second launch focuses the existing window instead of opening a copy.
- **Debugging:** set the environment variable `NOVA_DEBUG=1` and press `F12` for DevTools.

## Build from source

Requirements: Node.js 18 or newer (internet needed once for `npm install`). Building the Windows installer on Linux or macOS also needs Wine, so a Windows PC is easiest for that.

```bash
unzip novaboard-desktop-source.zip -d novaboard-desktop
cd novaboard-desktop
npm install
npm test            # quick self-test
npm start           # builds the offline bundle and opens the app
npm run dist:win    # Windows installer
npm run dist:linux  # AppImage + .deb
```

Output goes to `dist/`.

### Project layout

```
src/index.html   NovaBoard OS source (web app)
scripts/         build-web.js (offline bundler) and selftest.js
main.js          Electron main process (secure nova:// origin, strict CSP, save dialogs)
preload.js       Safe bridge between the page and the desktop shell
lib/paths.js     URL-to-file mapping with path-traversal protection
build/           Icons and installer artwork
LICENSE.txt      License shown in the Windows installer
package.json     App and electron-builder configuration
```

## Troubleshooting

- **SmartScreen blocks the installer:** use *More info → Run anyway*. A code-signing certificate removes this warning.
- **AppImage won't open:** make sure it is executable and `libfuse2` is installed.
- **Blank window on Linux:** launch from a terminal to see errors, and try `--no-sandbox`.
- **Antivirus flags the installer:** unsigned installers can cause false positives. Report it and add an exception.

## Privacy

The app runs fully offline with a strict content-security policy and makes no network requests. Boards, drawings and imported PDFs stay on your device.

## License

Released under the [MIT License](LICENSE).

## Contact

**Cognix Studio**: contactcognixstudio@outlook.com
Website: https://abhiraj1121.github.io/novaboard/
