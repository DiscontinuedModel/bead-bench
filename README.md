# Bead Bench

A bead pattern designer for bracelets, in a single HTML page.

- **Stitches:** loom, grid (square stitch) and flat peyote, plus rolled tubular peyote and bead crochet rope with a 3D rolled view
- **Drawing:** draw, fill, pick, erase, mirror, undo, clear, bead map
- **Colors:** 74 named bead colors, a color picker, recent colors, and a palette and pattern generator (ombré, stripes, chevron, diamonds and more)
- **Picture to pattern** in 8, 16 or 32 colors
- **Counts and charts:** bead counts with grams, and a row-by-row chart with checkmarks
- **Extras:** light and dark themes, and a guided tour in English with an Arabic option

Patterns are saved in the browser's local storage, so each device keeps its own. **My patterns → Save this pattern as a picture** makes a PNG of the chart and color key that you can view, print or text like any photo. The pattern data is stored inside the PNG, so **Open a saved pattern** loads it back on any device. **Back up all patterns** saves every pattern in one `.json` file.

## Run with Docker

```sh
docker compose up -d --build
```

Then open http://localhost:8080.

Without Compose:

```sh
docker build -t bead-bench .
docker run -d --name bead-bench -p 8080:80 --restart unless-stopped bead-bench
```

## Notes

- Fonts load from Google Fonts. Offline, the page falls back to system fonts.
- Patterns live in `localStorage` under the origin you serve from. If you change the host or port, earlier patterns won't show up.

## GitHub Pages

`index.html` sits at the repo root, so Pages works with no build step:
Settings → Pages → Deploy from a branch → `main` / `(root)`.
