# NovaBoard OS: Desktop Apps

Offline desktop builds of [NovaBoard OS](README.md) for Windows and Linux, packaged with Electron. All libraries and fonts are bundled, so no internet connection is needed.

## Downloads

| Platform | File | Notes |
| --- | --- | --- |
| Windows 10 / 11 (64-bit) | `NovaBoard-OS-Setup-1.0.0.exe` | Setup wizard installer |
| Linux, any distro (64-bit) | `NovaBoard-OS-1.0.0-x86_64.AppImage` | Portable, no install |
| Debian / Ubuntu / Mint (64-bit) | `NovaBoard-OS-1.0.0-amd64.deb` | Installs to the app menu |
| Source project | `novaboard-source.zip` | For developers |

---

## Windows

1. Run `NovaBoard-OS-Setup-1.0.0.exe`.
2. If Windows shows **"Windows protected your PC"**, click **More info → Run anyway**. The installer is not code-signed yet, so SmartScreen shows an "Unknown publisher" warning.
3. Follow the wizard: accept the license, choose the install folder, and finish. Desktop and Start Menu shortcuts are created.
4. Tick **Launch NovaBoard OS** on the last page to start the app.

**Uninstall:** *Settings → Apps → NovaBoard OS → Uninstall*. Your boards and settings are kept unless you remove them yourself.

## Linux: AppImage

```bash
chmod +x NovaBoard-OS-1.0.0-x86_64.AppImage
./NovaBoard-OS-1.0.0-x86_64.AppImage
```

On Ubuntu 22.04 and newer, you may need FUSE:

```bash
sudo apt install libfuse2
```

If the AppImage fails to start because of sandbox restrictions, run it with `--no-sandbox`.

## Linux: Debian / Ubuntu (.deb)

```bash
sudo apt install ./NovaBoard-OS-1.0.0-amd64.deb
```

Then launch **NovaBoard OS** from your app menu. To remove it:

```bash
sudo apt remove novaboard-os
```

---

## Keyboard shortcuts

| Key | Action |
| --- | --- |
| `F11` | Toggle fullscreen |
| `Ctrl` + `Shift` + `F12` | Toggle developer tools |

## Build from source

Requirements: Node.js 18 or newer. Building the Windows installer on Linux or macOS also needs Wine.

```bash
unzip novaboard-source.zip -d novaboard-os
cd novaboard-os
npm install
npm run dist                                 # Windows installer (NSIS)
npx electron-builder --linux AppImage deb    # Linux packages
```

Output goes to the `dist/` folder.

### Project layout

```
main.js          Electron entry point
app/index.html   NovaBoard OS (offline version)
app/vendor/      Bundled React, fabric.js, pdf.js, jsPDF, Tailwind CSS, fonts
build/           Icons and installer artwork
installer.nsh    Custom Windows installer steps
LICENSE.txt      License shown in the Windows installer
package.json     App and electron-builder configuration
```

## Troubleshooting

- **SmartScreen blocks the installer:** use *More info → Run anyway*. A code-signing certificate removes this warning.
- **AppImage won't open:** make sure it is executable and `libfuse2` is installed.
- **Blank window on Linux:** try launching from a terminal to see error output, and add `--no-sandbox` if needed.
- **Antivirus flags the installer:** unsigned installers can trigger false positives. Report it and add an exception.

## Privacy

The app runs fully offline and makes no network requests. Boards, drawings and imported PDFs stay on your device.

## License

Released under the [MIT License](LICENSE). The Windows installer displays the end-user terms in `LICENSE.txt`.

## Contact

**Cognix Studio**: contactcognixstudio@outlook.com
Website: https://abhiraj1121.github.io/novaboard/
