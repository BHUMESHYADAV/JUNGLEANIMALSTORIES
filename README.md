# Jungle Animal Stories — Android and offline ready

This folder contains the complete static website. `index.html` comes from the supplied source file. Local story media, animal pictures and sounds, the donation QR image, interactive map, encyclopedia, coloring book, and the games are included.

## Publish with GitHub Pages

1. Upload the **contents** of this folder to the root of a GitHub repository (or to the folder configured as the Pages publishing source). Keep file and folder names intact.
2. In GitHub, open **Settings → Pages**, select the branch and folder containing `index.html`, and save.
3. Open the published HTTPS URL once while online. The service worker downloads the site shell and bundled local files for later offline use. The initial download is about 82 MB.
4. To deploy updates, upload the changed files and increment `CACHE_NAME` in `service-worker.js`. Visitors receive the new cache as a safe update and can tap **Update available — reload**.

All internal links use relative paths and work when the repository is published under a project path such as `https://username.github.io/repository/`.

## Install on Android

1. Open the HTTPS GitHub Pages address in Chrome on Android and allow the initial visit and offline download to finish.
2. Use Chrome’s **Install app** prompt/button, or the menu’s **Install app** / **Add to Home screen** option.
3. Launch **Jungle Stories** from the home screen. The main page and bundled local games, images, sounds, and music are available after caching, including offline.

The included manifest and 192 px / 512 px icons provide install metadata. This is an installable website (PWA), not a Play Store APK or AAB.

## Offline limits

- Stories, local translations, speech narration supported by installed device voices, music/sounds, map, encyclopedia, coloring book, and bundled games work offline after their files are cached.
- Google Analytics cannot transmit events while offline; there is no offline analytics upload queue.
- Donations cannot be submitted offline. UPI payment requires a supported payment app and connectivity. The QR image and donation screen itself are bundled locally.
- Google Translate’s external script requires connectivity; language translations already included in the page remain local.
- Browser storage quotas vary by device. If the browser refuses to cache a large file, the service worker continues caching other files and reports skipped assets to the browser console.

## Project files

- `index.html` — supplied website plus installation, offline status, and service worker registration.
- `manifest.webmanifest` — Android/browser install metadata.
- `service-worker.js` — versioned cache, local asset precache, offline navigation fallback, and safe activation.
- `icons/` — app icons generated from the existing site artwork.
- Remaining HTML/media files — existing site pages and local content.