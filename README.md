# Official LaTeX Template for Purdue Digital Twin Lab

This is the official LaTeX template for reports and publications from the [Purdue Digital Twin Lab](https://engineering.purdue.edu/digitaltwin). It provides consistent formatting, a branded header with the lab logo, and a structured multi-file layout.

## Using This Template

This repository is set up as a **GitHub template**. To create a new paper or report from it:

1. Click **"Use this template"** → **"Create a new repository"** at the top of this page.
2. Choose a name, visibility, and owner for your new repository, then click **"Create repository"**.
3. Clone your new repository locally:

   ```bash
   git clone https://github.com/<your-org>/<your-repo>.git
   cd <your-repo>
   ```

## Repository Structure

```text
.
├── main.tex            # Root document — edit title and authors here
├── commands.tex        # Package imports and custom commands
├── pdt_report.sty      # Lab style file (do not modify)
├── assets/
│   └── logo.png        # Lab logo used in page headers
├── contents/
│   ├── 0_abstract.tex
│   ├── 1_introduction.tex
│   ├── 2_related.tex
│   ├── 3_method.tex
│   ├── 4_experiment.tex
│   ├── 5_conclusion.tex
│   ├── 6_postscripts.tex
│   └── X_appendix.tex
└── Makefile
```

## Writing Your Paper

1. **Set your title and authors** in `main.tex`:

   ```latex
   \title{Your Paper Title}

   \author{
     Author One\thanks{Optional footnote.} \\
     College of Engineering, Purdue University \\
     \texttt{author1@purdue.edu}
     \And
     Author Two \\
     College of Engineering, Purdue University \\
     \texttt{author2@purdue.edu}
   }
   ```

   Use `\And` to let LaTeX break lines between authors, or `\AND` to force a line break.

2. **Write each section** in its corresponding file under `contents/`. Add or remove section files as needed, and update the `\input{...}` calls in `main.tex` accordingly.

3. **Add custom packages and commands** in `commands.tex`. The file is already pre-loaded with common packages for math, figures, tables, and pseudocode.

## Building the PDF

Requires a TeX distribution (e.g., [TeX Live](https://tug.org/texlive/) or [MiKTeX](https://miktex.org/)) with `latexmk` available.

```bash
# Build main.pdf
make

# Remove intermediate build files
make clean

# Remove all generated files including the PDF
make cleanall
```

The compiled `main.pdf` is placed in the repository root. Intermediate build files are written to `release/target/`.

## Requirements

- LaTeX2e with `latexmk`
- Packages: `geometry`, `fancyhdr`, `graphicx`, `natbib`, `hyperref`, `amsmath`, `booktabs`, `tabularray`, `algorithm`, `algpseudocode`, and others listed in `commands.tex`

## License

This template is licensed under the BSD 3-Clause License. See the [LICENSE](LICENSE) file for details.
