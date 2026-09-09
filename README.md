# Nikhil Sharma — CV (LaTeX)

Two versions of the same CV content, in different formats:

| File | Format | Compiler |
|---|---|---|
| `main.tex` | Matches [nikhilsharma.info](https://nikhilsharma.info): Fraunces + Hanken Grotesk, oxblood accent, hairline rules | XeLaTeX (needs `fonts/`) |
| `main-bw.tex` | Classic black & white academic CV: Times serif, bold caps section headers with a rule, no color | pdflatex (no extra fonts needed) |

Both have no photo and identical content — pick whichever format you want for a given submission.

## Compiling

```
# colored version
xelatex main.tex
xelatex main.tex

# black & white version
pdflatex main-bw.tex
pdflatex main-bw.tex
```

(Compile twice so the outline/bookmarks settle.)

## Using this in Overleaf

**Option A — one-time upload (works on any Overleaf account):**
1. Zip the file(s) you need: `main.tex` + `fonts/` for the colored version, or just `main-bw.tex` for the black & white version.
2. On Overleaf: New Project → Upload Project → select the zip.
3. Set the compiler: Menu (top-left) → Settings → Compiler → **XeLaTeX** for `main.tex`, or leave as **pdfLaTeX** for `main-bw.tex`.
4. If you upload both versions into one Overleaf project, set which file is "Main document" (also in Settings) to choose which one compiles.

**Option B — synced with this GitHub repo (requires Overleaf premium for GitHub sync):**
1. On Overleaf: New Project → Import from GitHub → select this repo.
2. Set the compiler/main document as above.
3. Future edits pushed to GitHub can be pulled into the Overleaf project (or vice versa) via Overleaf's GitHub sync panel.

## Editing conventions

Both files are organized by `% ============ SECTION ============` banners, in CV order: Research, Teaching, Education, Conferences & Presentations, Service & Awards, Industry Experience, Skills & Training, References.

- **Add a publication:** copy one `\pubentry{year}{status}{title}{authors}{description}` line. Leave a field empty (`{}`) to omit it (e.g. no description for most working papers).
- **Add a talk / teaching / service / reference row:** copy one `\rowentry{when}{title}{body}` line.
- **Update a paper's status:** edit the relevant `\pubentry` call — status text is freeform (e.g. `Major Revision · Journal Name`).
- Making a change to one version does **not** update the other — edit both `main.tex` and `main-bw.tex` if the change should apply everywhere (e.g. a new talk, a status update).
- **Restyle the colored version:** colors are defined once near the top of `main.tex` (`ink`, `muted`, `line`, `accent`).

## Fonts (colored version only)

`fonts/` contains static instances (via `fonttools varLib.instancer`) of the Google Fonts variable files for Fraunces and Hanken Grotesk, matching the weights used on the website. These are licensed under the SIL Open Font License and travel with the project so it compiles identically anywhere. `main-bw.tex` doesn't need these — it uses the standard `times` package.
