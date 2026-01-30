# 🎉 happybirthdayanuj

A celebratory web page to wish Anuj a happy birthday — a responsive webpage that plays songs, shows photos in a slideshow, and includes interactive features to make the celebration fun and sharable.

This README explains what the project contains, the key features, how to install and run it locally, and how to add songs and photos.

---

## Table of contents

- [About](#about)
- [Features](#features)
- [Demo / Preview](#demo--preview)
- [Project structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Install & Run](#install--run)
  - [Option A — Open as a static site (quick)](#option-a---open-as-a-static-site-quick)
  - [Option B — Run with a local server (recommended)](#option-b---run-with-a-local-server-recommended)
  - [Option C — Node / npm project (if repo already uses npm)](#option-c---node--npm-project-if-repo-already-uses-npm)
- [How to add songs & photos](#how-to-add-songs--photos)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## About

This repository contains the assets and code for a birthday web page for Anuj which showcases multiple songs and photo galleries/slideshows alongside interactive controls to play, pause, shuffle, and view images full-screen. The page is intended to be easy to deploy (static hosting or simple Node server) and customizable.

---

## Features

- Multiple songs / audio tracks with a simple player:
  - Play / Pause
  - Next / Previous track
  - Shuffle and repeat (optional)
  - Volume control
  - Track list display
- Photo gallery / slideshow:
  - Manual navigation and auto-play slideshow
  - Fullscreen viewing
  - Captions for photos
  - Transition effects (fade/slide)
- Responsive layout — works on mobile and desktop
- Keyboard controls (left/right for slideshow, space for play/pause) — if implemented
- Download or share photos (optional)
- Simple message or guestbook area (optional) for visitors to leave wishes
- Accessibility considerations (alt tags, readable buttons) recommended
- Offline-friendly: static files so can be hosted on GitHub Pages, Netlify, Vercel, etc.

---

## Demo / Preview

If you have a live deployment (GitHub Pages or other), add the demo link here:

Example:
https://Gamingtech568.github.io/happybirthdayanuj

(Replace with your actual URL)

---

## Project structure (recommended)

A typical simple structure for this kind of project:

- index.html             — main webpage
- css/
  - styles.css
- js/
  - player.js
  - slideshow.js
- assets/
  - songs/
    - song1.mp3
    - song2.mp3
  - photos/
    - photo1.jpg
    - photo2.jpg
- README.md

Adjust paths if your repo uses a different layout.

---

## Prerequisites

- A modern web browser (Chrome, Firefox, Edge, Safari)
- For running a local server: Node.js and npm (optional but recommended)
- (Optional) `npx` to run quick static servers like `serve` or `http-server`

---

## Install & Run

Choose one of the following options depending on how you want to run the site.

### Option A — Open as a static site (quick)
1. Clone the repository or download ZIP and extract.
2. Open `index.html` in your browser:
   - Double-click the file, or
   - Right-click -> Open With -> your browser

Note: Some browsers restrict local file access for audio or fetch requests. If the audio or images do not load properly when opened directly, use Option B below.

### Option B — Run with a local static server (recommended)
This avoids local file restrictions and more closely matches deployment.

Using npx (no install required):
```bash
# from project root
npx serve .        # serve (install prompt if not present)
# or
npx http-server .  # simple http-server
```

Or install `serve` globally:
```bash
npm install -g serve
serve .
```

Then open http://localhost:3000 (or the port shown) in your browser.

### Option C — Node / npm project (if repo already uses npm)
If your repo includes a package.json with scripts, use:
```bash
# install dependencies (if any)
npm install

# start the dev server (example script names)
npm run dev
# or
npm start
```

If you want to add a lightweight script to package.json to serve the static site:
```json
{
  "scripts": {
    "start": "serve -s .",
    "dev": "npx http-server . -p 8080"
  }
}
```

---

## How to add songs & photos

Recommended folders:
- Put songs in `assets/songs/` (MP3 or OGG recommended)
- Put photos in `assets/photos/` (JPG, PNG, or WebP)

Naming & metadata:
- Use human-friendly file names like `01-happy-birthday.mp3`, `family-2025.jpg`
- Add captions or a JSON file with metadata if you want captions, photographer credits, or ordering:
  - `assets/photos/photos.json`
  - `assets/songs/songs.json`

Example `songs.json`:
```json
[
  { "file": "assets/songs/01-happy-birthday.mp3", "title": "Happy Birthday", "artist": "Artist Name" },
  { "file": "assets/songs/02-surprise.mp3", "title": "Surprise Track", "artist": "Band" }
]
```

Example `photos.json`:
```json
[
  { "file": "assets/photos/photo1.jpg", "caption": "Anuj with friends (2019)" },
  { "file": "assets/photos/photo2.jpg", "caption": "Cake time!" }
]
```

How to update the UI:
- If your player reads a JSON manifest, add the entry there.
- If filenames are hard-coded in `index.html` or JS, update the arrays in `js/player.js` or `js/slideshow.js`.

Permissions:
- Make sure files are not blocked by CORS when hosted; for static hosting this is usually fine.

---

## Troubleshooting

- No audio plays:
  - Many browsers block autoplay with sound. Click a Play button or interact with the page to allow audio.
  - Check the console (F12) for errors about missing files or blocked requests.
- Images don't show:
  - Verify photo paths and file names (case-sensitive on most servers).
  - If opening `index.html` directly, try running a local server instead.
- Controls not responding:
  - Ensure `js` files are loaded (check <script> paths in `index.html`).
  - Open developer console to view any runtime errors.

---

## Contributing

1. Fork the repo
2. Create a feature branch: `git checkout -b feature/your-feature`
3. Commit your changes: `git commit -m "Add some feature"`
4. Push: `git push origin feature/your-feature`
5. Create a pull request describing your changes

Ideas:
- Add more player features (equalizer, crossfade)
- Add a message board that saves wishes
- Improve accessibility (ARIA labels, focus management)
- Add tests and CI (linting)

---

## License

Add your preferred license here (e.g., MIT). Example:

MIT © [Your Name]

---

## Contact

If you need help or want me to tailor this README to the exact contents of the repository (list actual songs, photos, or include screenshots), tell me and I can:
- Inspect the repository to extract exact asset lists and file paths, then update the README accordingly, or
- Create a minimal package.json / server script for you.

Enjoy celebrating Anuj! 🎂🎶📸
