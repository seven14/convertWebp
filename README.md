# WebP → PNG

A small, single-page web app that converts WebP images to PNG, entirely in your browser. Files never leave your device. There is no server, upload, or account.

**Live:** `https://<yourusername>.github.io/` *(update this link once it's published)*

## Features

- **Drag and drop, file picker, or paste.** Use any of the three to add images. You can add several files at once.
- **Lossless output.** Transparency (the alpha channel) is preserved.
- **Batch download.** Save one PNG at a time, or save all of them as a single ZIP.
- **File details.** Each file shows its original WebP size, the PNG size, its dimensions, and whether it has transparency.
- **Light and dark themes.** The page follows your system setting.
- **Works on phones and desktops.**

## How it works

The browser decodes each WebP with `createImageBitmap` (or `<img>` as a fallback). The app draws the image onto a `<canvas>` and re-encodes it with `canvas.toBlob('image/png')`. ZIP files are built in the browser with [JSZip](https://stuk.github.io/jszip/).

## Usage

1. Open the page.
2. Drop `.webp` files onto the drop zone, click **Choose files**, or paste an image.
3. Click **Save PNG** on a file, or **Save all as ZIP**.

## Notes

- **PNG files are usually larger than the WebP originals.** PNG is lossless and WebP is often lossy, so this is normal.
- **Animated WebP files are converted to a single PNG.** Only the first frame is kept.
- **Supported browsers.** The app works in any current version of Chrome, Edge, Firefox, or Safari.

## Hosting on GitHub Pages

1. Put `index.html` in your `<yourusername>.github.io` repository. Use the repo root, or a subfolder such as `webp-to-png/`.
2. Commit and push. GitHub Pages publishes the site within a minute or two.
3. Check **Settings → Pages** to confirm the site deploys from the `main` branch.

The app needs no build step or dependencies to install. It loads two resources from CDNs:

- **Fonts** from Google Fonts. If they don't load, the page uses system fonts instead.
- **JSZip** from cdnjs. ZIP export is disabled if it doesn't load.

## Running locally

Open `index.html` directly in a browser. Or serve the folder:

```sh
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Files

```
index.html   # the whole app: markup, styles, and script
README.md
```

## License

MIT. Change this if you prefer a different license.
