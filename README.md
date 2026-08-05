# Resume

My one-page software engineering and AI resume, written in LaTeX and optimized
for readable PDF output and ATS parsing.

## Build

Install a TeX distribution such as [MacTeX](https://www.tug.org/mactex/) or
[TeX Live](https://www.tug.org/texlive/), then compile from the repository root:

```bash
pdflatex -interaction=nonstopmode -halt-on-error resume.tex
pdflatex -interaction=nonstopmode -halt-on-error resume.tex
```

The second pass finalizes PDF metadata and hyperlinks. The generated file is
`resume.pdf`.

If a minimal TeX Live installation reports that `fullpage.sty` is missing,
install the package bundle before compiling:

```bash
sudo tlmgr install preprint
```

## Repository structure

- `resume.tex` — resume content, formatting, and links
- `.gitignore` — generated LaTeX files and local tooling exclusions

Generated build artifacts, including `resume.pdf`, are intentionally excluded
from version control.

## Template credit

The LaTeX structure is based on the
[sb2nov resume template](https://github.com/sb2nov/resume), originally authored
by Jake Gutierrez and distributed under the MIT License.
