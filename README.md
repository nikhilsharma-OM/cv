# Nikhil Sharma — CV (LaTeX)

A LaTeX CV matching the design of [nikhilsharma.info](https://nikhilsharma.info): Fraunces (serif headings) + Hanken Grotesk (body), oxblood accent, hairline rules. No photo.

## Compiling

Requires **XeLaTeX** (needed for `fontspec`, since this uses the actual Fraunces/Hanken Grotesk font files bundled in `fonts/`). Compile twice for the outline/bookmarks to settle:

```
xelatex main.tex
xelatex main.tex
```

## Using this in Overleaf

**Option A — one-time upload (works on any Overleaf account):**
1. Zip this whole folder (`main.tex`, `fonts/`).
2. On Overleaf: New Project → Upload Project → select the zip.
3. Set the compiler to **XeLaTeX**: Menu (top-left) → Settings → Compiler → XeLaTeX.

**Option B — synced with this GitHub repo (requires Overleaf premium for GitHub sync):**
1. On Overleaf: New Project → Import from GitHub → select this repo.
2. Set the compiler to XeLaTeX as above.
3. Future edits pushed to GitHub can be pulled into the Overleaf project (or vice versa) via Overleaf's GitHub sync panel.

## Editing conventions

The file is organized by `% ============ SECTION ============` banners, in CV order: Research, Education, Teaching, Conferences & Presentations, Service & Awards, Industry Experience, Skills & Training.

- **Add a publication:** copy one `\pubentry{year}{status badge}{title}{authors}{description}` line. Leave a field empty (`{}`) to omit it (e.g. no badge for a working paper).
- **Add a talk / teaching / service row:** copy one `\rowentry{when}{title}{body}` line.
- **Update the job market paper / statuses:** just edit the relevant `\pubentry` call — status badges are freeform text (e.g. `Major Revision · Journal Name`).
- **Restyle:** colors are defined once near the top (`ink`, `muted`, `line`, `accent`) — change `accent` to restyle the whole document's highlight color.

## Fonts

`fonts/` contains static instances (via `fonttools varLib.instancer`) of the Google Fonts variable files for Fraunces and Hanken Grotesk, matching the weights used on the website. These are licensed under the SIL Open Font License and travel with the project so it compiles identically anywhere (no need to rely on Overleaf having them pre-installed).
