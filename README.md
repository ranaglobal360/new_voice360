# Voice 360 — Product Framework

Static site. No build step, no dependencies. Open `index.html` in a browser or serve the folder.

## What's here

```
index.html            the framework itself — this is the file that changes most
support.js            runtime it needs; changes rarely
*.dc.html             screen sets the framework embeds (flow map, screen galleries,
                      dashboard, community home, board screens) — keep the exact
                      filenames, including the spaces and colons
docs/                 source PDFs + the Parliamentary screens deck (standalone HTML)
scraps/resthumbs/     grid thumbnails for the Resources → Images gallery
scraps/resview/       full-size originals, used by the lightbox and downloads
```

Keep the folder structure as-is — `index.html` refers to these paths relative to itself.

## Updating

Typical update touches **`index.html` only**. Replace that one file and commit.

Upload other folders only when told a new file was added:

| Changed | Replace |
|---|---|
| Framework content, layout, copy | `index.html` |
| A screen design | the matching `.dc.html` |
| A new or revised source PDF | that file in `docs/` |
| New screenshots in the gallery | the pair in `scraps/resthumbs/` + `scraps/resview/` |
| Nothing — it is stable | `support.js` |

If the User flow map or a screen gallery renders as an empty grey band, a `.dc.html` is missing or was renamed — the framework loads them by exact filename.

## GitHub Pages

Settings → Pages → deploy from branch, root of whatever folder this sits in. `index.html` is picked up automatically.
