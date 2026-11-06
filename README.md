# LaTeX Report Template

A LaTeX template for university assignments and technical reports, with English
and Swedish language settings, a configurable title page, mathematical
typesetting, code listings, and an IEEE-style bibliography.

## Requirements

- A LaTeX distribution such as TeX Live or MiKTeX, with the packages used by
  this project installed
- `latexmk`
- `biber` for bibliography processing

The default configuration uses pdfLaTeX. The optional font configuration uses
`fontspec`, which requires LuaLaTeX or XeLaTeX instead.

## Build

From the project directory, run:

```sh
latexmk main.tex
```

This creates `main.pdf` and stores auxiliary build files in `.build/`. To build
with an alternate engine, use one of:

```sh
latexmk -lualatex main.tex
latexmk -xelatex main.tex
```

Remove generated files with:

```sh
latexmk -C
```

## Getting Started

1. Edit the document metadata and sample text in `main.tex`. Update the course
	name, title, date, author list, abstract, and title-page image/note as
	appropriate.
2. Set `\swedishtrue` to use Swedish, or leave `\swedishfalse` for English.
3. Use the `\showimage`, `\shownote`, and `\showabstract` switches in
	`main.tex` to enable or disable those title-page elements.
4. Replace the example body, equations, figure, and appendix with your content.
5. Replace the sample entries in `references.bib` with your own references.
	Cite entries in the document with `\cite{key}`; the bibliography is printed
	near the end of `main.tex`.

The title-page layout is in `titlepage.tex`. Reusable packages and formatting
options are split into files in `options/`; enable or disable them by changing
the corresponding `\input` lines in `main.tex`. If you enable
`options/fonts.tex`, select LuaLaTeX or XeLaTeX and configure the font in that
file.

## Project Layout

| File | Purpose |
| --- | --- |
| `main.tex` | Document settings, option loading, and sample report content |
| `titlepage.tex` | Configurable title-page layout |
| `references.bib` | Bibliography database (contains example references) |
| `latexmkrc` | Selects pdfLaTeX and puts auxiliary files in `.build/` |
| `options/base.tex` | Page layout and common packages |
| `options/colors.tex` | Color definitions |
| `options/mathmatics.tex` | Math and units support |
| `options/captions.tex` | Caption formatting |
| `options/code.tex` | Source-code listing style |
| `options/fancy.tex` | Headers and footers |
| `options/references.tex` | `biblatex` configuration and bibliography source |
| `options/appendix.tex` | Appendix support |
| `options/commands.tex` | Custom document commands |
| `options/fonts.tex` | Optional font configuration; requires LuaLaTeX or XeLaTeX |
| `options/extras.tex` | Optional additional settings |

The document currently contains placeholder prose, a sample figure, and example
citation keys. Replace these before submitting or publishing your report.