# CrystalPrompt

A voice-activated teleprompter that runs in the browser and installs as an app (PWA).

- Your script floats over the live camera feed, close to the lens.
- It listens as you speak and keeps the next word on the reading line. It waits when you pause, catches up when you skip ahead, and finds your place when you repeat a sentence. Tap any word to jump there.
- Record takes with camera and mic, play them back, and download them as MP4 or WebM. The prompter text is not recorded into the video.
- Adjustable text size, width, background darkness and reading line, mirrored preview, flipped text for beam-splitter rigs, camera and mic choice, up to 4K, and a steady-speed scroll mode.

## Use it

Open the GitHub Pages link for this repo (Settings → Pages shows it), allow the camera and microphone, and press **Install app** (or use the browser's install icon). On iPhone or iPad, tap Share, then Add to Home Screen.

Voice tracking uses the browser's built-in speech recognition, which works in Chrome, Edge and Safari and needs an internet connection. Firefox doesn't support it, so the app switches to steady-speed scrolling there. Everything else, including recording, works offline once the app has loaded once.

Takes live only in the open tab until you download them.

## Keyboard

| Key | Action |
| --- | --- |
| R | Start or stop recording |
| V or Space | Voice tracking on/off (or pause scrolling in steady mode) |
| ↑ / ↓ | Move back or forward one word |
| Home | Back to the top |
| E | Edit script |
| S | Settings |
| Esc | Close panels |

## Develop

No build step. Serve the folder over http and open it:

```sh
python3 -m http.server 8000
```

Then visit http://localhost:8000. Camera access needs `localhost` or https.

When you change `index.html`, bump `VERSION` in `sw.js` so installed copies pick up the update. Pushing to `main` deploys to GitHub Pages through `.github/workflows/pages.yml`.
