# Photo Timeline

Lay photos out on a timeline by the date they were taken, mark periods with Gantt-style bands and special days with event markers, and save the whole thing as an image.

## Try it

**[Open Photo Timeline → petravanta.github.io/photo-timeline](https://petravanta.github.io/photo-timeline/)**

1. **Add photos.** Each one lands on the timeline at the date its camera recorded (or, without one, when the file was last changed).
2. **Move them.** Drag a photo to another date or another track. On a phone, tap a photo to select it and then drag it, or hold it for a moment to pick it up straight away. The selection bar under the timeline moves it a day at a time too.
3. **Mark what happened.** **+ Band** adds a period, like a trip or a season; drag it to move it or drag an end to change its days. **+ Event** adds a flag for a special day, with a line across every track.
4. **Save as image** downloads a PNG (or opens the share sheet on a phone), at the width, sharpness and colors you pick.

## What it does

- **As many timelines as you like.** The picker in the header switches between them; *+ New timeline* starts another (a trip, a year, a child's first years). Each has its own name, tracks, photos, bands and events, and its own display settings under *Settings*, where you can also delete it.
- **One or more photo tracks.** **+ Track** adds another row, for a different person, camera or theme. Each track has its own name, color and photo height, and can spread overlapping photos apart or let them overlap.
- **Fits the screen.** By default photos are sized so the tracks share the window's height and a crowded track shrinks until its photos fit across. The time axis fits the width, and its labels switch between hours, days, months and years as you zoom. Photos that would overlap are spread out around their dates, and a stem joins each one to its exact date.
- **Keyboard and screen readers.** Select something on the timeline and use the arrow keys to move it (Shift for a week, up and down for another track) and Enter to edit it. Everything on the timeline is also listed under it, with an Edit button.
- Light and dark themes, the shared **All apps** link and theme switch, and a phone-first layout, as the [shared standards](https://github.com/petravanta/general/blob/main/STANDARDS.md) describe.

## Your data

Nothing is uploaded. The timeline is kept in your browser (`localStorage`) and the photos in its IndexedDB, shrunk to 1600 pixels on the longest side. **Settings → Export backup** downloads every timeline, photos included, as one JSON file, and **Import backup** merges one back in, following the *User data* section of the shared standards. Google Drive sync is not built yet.

## Running it

It is a single static file, `index.html`, with no build step and no built-in data. Serve the folder (`python3 -m http.server`) and open it. GitHub Pages serves it from `main`, root folder.
