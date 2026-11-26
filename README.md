# ECNU Beamer Presentation Template

An academic Beamer (LaTeX) presentation template for East China Normal University. The cover uses the university seal, and the theme is loaded with `\usetheme{ECNU}`. Lexend and Inter fonts are bundled.

## Upstream and attribution

This ECNU Beamer template is a modified version of the original template published by FreeU-group. [Original GitHub project](https://github.com/FreeU-group/thu_template)

- [Upstream compiled PDF](https://github.com/FreeU-group/thu_template/blob/main/slide.pdf)
- [Locally compiled archive of the original theme](slide-Tsinghua.pdf)

## Features

- **ECNU standard red** (Pantone 201 C, `#A41F35`)
- Automatic **section divider** pages with decorative rules
- **Smooth navigation bar** header (section dots) + page-number footer
- Full **biblatex / Biber** citation support (footnote style)
- Built-in styles for **code listings**, **TikZ diagrams**, **tables**, **multi-column layouts**, and **placeholder boxes**
- **XeLaTeX** + **fontspec** pipeline — works on Windows, macOS, and Linux
- CJK support out of the box (Microsoft YaHei / SimSun fallback)

## Quick Start

### Prerequisites

| Tool       | Minimum version | Notes                              |
|:-----------|:----------------|:-----------------------------------|
| TeX Live   | 2023+           | or MiKTeX 2023+                    |
| XeLaTeX    | bundled         | comes with TeX Live / MiKTeX       |
| Biber      | bundled         | for bibliography processing        |
| latexmk    | bundled         | optional but recommended           |

### Build

```bash
# Option 1: latexmk (recommended — auto-runs biber)
latexmk slide.tex

# Option 2: manual
xelatex  slide.tex
biber    slide
xelatex  slide.tex
xelatex  slide.tex
```

### File Structure

```
ecnu_beamer_template/
├── slide.tex           # Main presentation source
├── beamerthemeECNU.sty # Beamer theme
├── slide.pdf           # Compiled example
├── .latexmkrc          # latexmk config (XeLaTeX mode)
├── README.md           # This file
├── fonts/
│   ├── Inter/          # Inter font family (.ttf/.otf)
│   └── Lexend/         # Lexend font family (.ttf)
├── pic/                # Images & logos
│   └── ECNU_LOGO.png
└── ref/
    └── refs.bib        # Bibliography database
```

## Customisation

### Change Author / Title

Set the author and title near the top of `slide.tex`. Update the title and supervisor in the cover block as well.

```latex
\newcommand{\authorname}{Your Name}
\title[Short Title]{Your Presentation Title}
\newcommand{\institutename}{East China Normal University}
\date{\today}
```

### Change Colours

The theme and the example slides share the `ECNURed` colour defined in `beamerthemeECNU.sty`.

```latex
\definecolor{ECNURed}{RGB}{164,31,53}
```

### Add Your Own Figures

Place images in `pic/` and reference them:

```latex
\includegraphics[width=0.8\textwidth]{my-figure.png}
```

### Placeholder for Draft Slides

```latex
\placeholder{Figure to be added later}
```

### Add References

Add entries to `ref/refs.bib`, then cite in slides:

```latex
This was shown by prior work.\footfullcite{vaswani2017attention}
```

## Template Contents (Examples Included)

| Slide type              | What it demonstrates                          |
|:------------------------|:----------------------------------------------|
| Title page              | Logo, author, institute, supervisor            |
| Outline                 | Numbered section list                          |
| Text + citations        | Footnote-style references via biblatex         |
| Research question        | Coloured block environment                     |
| Two-column + TikZ       | Side-by-side layout with inline diagram        |
| Mathematical formulation| Display math with underbrace annotations       |
| Algorithm steps          | Nested enumerate with colour accents           |
| Results table            | booktabs + multirow professional table         |
| Ablation table           | Compact comparison table                       |
| Heatmap visualisation    | TikZ-generated pseudo-heatmap                  |
| Flowchart                | TikZ node-based flowchart with decision node   |
| Code listing             | Python code with syntax highlighting           |
| Columns + placeholder    | Draft-mode placeholder box                     |
| Multi-column             | Two-column itemize with summary block          |
| Conclusion               | Contributions + future directions              |
| Thank-you page           | Contact info                                   |
| References               | Full bibliography page                         |

## License

This template is provided as-is for academic use. See the [university visual identity guidelines](https://www.ecnu.edu.cn/wzcd/xxgk/xxbs.htm) for use of the ECNU logo.
