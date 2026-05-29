# Changelog

## 2026-05-29

- Packaged a GitHub-ready Harbin Institute of Technology undergraduate thesis LaTeX template.
- Set the example entry to `fontset=windows,type=bachelor,campus=harbin`.
- Made `thesis.tex` auto-fallback from `fontset=windows` to `fontset=fandol` when Windows CJK fonts are unavailable, so Overleaf can compile without manual font edits.
- Added a lightweight `main.tex` wrapper so Overleaf projects that default to `main.tex` can compile without changing the root file.
- Kept the innovation-achievement page as an optional file but disabled it by default in `thesis.tex`.
- Tightened chapter-number/title spacing in the table of contents to match the `第1章  绪论` format.
- Set Harbin-campus bachelor section and subsection spacing to exactly half a body line above and below.
- Removed extra blank source paragraphs before displayed formulas in the bundled writing guideline sample.
- Added `\hititemparagraph{标题}{正文}` for numbered paragraphs with bold titles, Songti body text, and a four-Chinese-character gap.
- Adjusted `longtable` default row spacing to improve table readability.
- Added README, git ignore rules, and upstream attribution notice.
