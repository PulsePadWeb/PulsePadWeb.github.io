# Pulsepad — standalone soundboard

**1,798 sounds. One folder. No network required.** This edition includes every sound file, the artwork, fonts, JavaScript, and CSS locally. It does not load media, data, analytics, fonts, or application code from another website.

## Open it now

1. Extract the **ready-to-open** ZIP completely.
2. Double-click `index.html` in the extracted folder. Chrome, Edge, and Firefox are supported.
3. Keep `catalog.js`, `audio/`, and `media/` beside `index.html`. Opening the HTML directly from inside the ZIP may not work; extract it first.

No installation, account, API key, server, or internet connection is needed for local playback. Favorites and recently played sounds are saved in your browser on that device.

## Host it anywhere

Upload **all contents** of the ready-to-open folder to any ordinary static-file host (for example, an existing website's directory, Nginx, Apache, a static object-storage website, or a generic static-hosting provider). Keep the relative folder structure unchanged. There are no server endpoints or runtime services. It also works under a subdirectory.

On a hosted URL, the card's share button copies a direct link to that sound. When opened as a local file, a copied link points to your own extracted folder; to share it with someone else, host the folder or send them the package.

For faster hosted delivery, enable **gzip or Brotli** compression for HTML, CSS, and JavaScript on your host. The package includes an optional zero-dependency Python server with gzip and MP3 byte-range support:

```bash
python3 serve.py --port 8080
```

Open `http://127.0.0.1:8080/` afterward. Python 3.9+ is needed only for this optional server, not for double-click playback. The first sound row is pre-rendered, and the complete local `catalog.js` loads separately after the interface is usable.

## Rebuild from source (optional)

The source ZIP has the same 1,798 MP3s in `public/audio/`. With Node.js 20+ installed:

```bash
npm install
npm run check
npm run verify
npm run build
```

The complete ready-to-open site is generated in `dist/`. The build emits a classic browser script rather than an ES-module entry point so it can run from `file://` without a local web server. `npm run verify -- --dist` checks the generated site. `audio-sha256.txt` lists hashes for all sound files, relative to the ready-to-open folder.

## Motion and accessibility

Animated hero particles, drifting orbits, responsive sound-pad tilt, hover glints, play ripples, reactive waveforms, favorites bursts, and player motion are included. Nonessential movement honors the operating system's **Reduce motion** setting.

## Catalog and rights

This is a static snapshot of the **Myinstants US Sound Effects** category collected on September 27, 2026, with 1,798 unique clips. The package does not contact that website at runtime. Rights to redistribute each user-submitted recording have **not** been independently verified; review permissions before publishing the collection to a public audience. Typeface and software license notices are included in `licenses/`.
