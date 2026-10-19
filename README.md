# Bead Bench

A bead pattern designer for bracelets, in a single HTML page.

- **Stitches:** loom, grid (square stitch) and flat peyote, plus rolled tubular peyote and bead crochet rope with a 3D rolled view
- **Drawing:** draw, fill, pick, erase, mirror, undo, clear, bead map
- **Colors:** 74 named bead colors, a color picker, recent colors, and a palette and pattern generator (ombré, stripes, chevron, diamonds and more)
- **Picture to pattern** in 8, 16 or 32 colors
- **Counts and charts:** bead counts with grams, a row-by-row word chart with checkmarks, and **Bead along** mode, which shows one big row at a time and keeps the screen awake
- **Print / export:** a printable US Letter PDF with the bead graph, row numbers down both sides, a word chart in the usual `Row 3 (R) (1C), (2A)` style, and a color key with optional bead numbers such as DB-0010. Bead crochet patterns also show the stringing repeat.
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

- Fonts load from Google Fonts and the PDF maker (jsPDF) loads from cdnjs. Offline, the page falls back to system fonts, and you can still save the PNG picture.
- Patterns live in `localStorage` under the origin you serve from. If you change the host or port, earlier patterns won't show up.

## GitHub Pages

`index.html` sits at the repo root, so Pages works with no build step:
Settings → Pages → Deploy from a branch → `main` / `(root)`.
