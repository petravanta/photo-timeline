# Notes for coding agents

Follow the shared standards in https://github.com/petravanta/general/blob/main/STANDARDS.md (hub link, theme switch, shared look, user data). Take patterns from there, not from the other apps. This file only adds what's specific to Photo Timeline.

- The app is `index.html` with no build step. Serve the folder (`python3 -m http.server`) to run it.
- There is no built-in knowledge, so there is no `data/` folder. If the app ever ships presets (track or band templates, say), they go in `data/` as the standards describe.
- The timeline is one canvas drawn by `draw()`. The screen and the saved image both go through it, so change it once and both follow. `layout()` decides where everything goes and knows nothing about scrolling; the screen canvas is only as wide as the view and redraws on scroll, which keeps it inside Safari's canvas size limit.
- Colors on the canvas come from CSS tokens (`--c-<color>` for the picker colors) read by `readTokens()`, and redraw when `data-theme` changes. Add a color by adding its token in all three theme blocks and its key to `COLORS`.
- The document (`photoTimeline.data` in `localStorage`) follows the standards' *User data* shape: `tracks`, `photos`, `bands` and `events` records with `id` and `u`, and `deleted`. Photo files live in IndexedDB (`photo-timeline` / `images`), keyed by photo id; a backup carries them as data URLs under `images`.
- Dates are local wall-clock strings, as cameras record them: photos `YYYY-MM-DDTHH:MM:SS`, bands and events `YYYY-MM-DD` (a band's `end` day is included). Parse them with `parseLocal()`, never `new Date(string)`, which reads a bare date as UTC.
