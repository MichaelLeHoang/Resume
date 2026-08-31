# Resume

My one-page software engineering and AI resumes, written in LaTeX and optimized
for readable PDF output and ATS parsing. Both variants share one content source,
so experience, projects, skills, and education stay synchronized.

## Build

Install a TeX distribution such as [MacTeX](https://www.tug.org/mactex/) or
[TeX Live](https://www.tug.org/texlive/), then compile from the repository root:

```bash
mkdir -p standard external

pdflatex -interaction=nonstopmode -halt-on-error -jobname=Resume -output-directory=standard resume.tex
pdflatex -interaction=nonstopmode -halt-on-error -jobname=Resume -output-directory=standard resume.tex

pdflatex -interaction=nonstopmode -halt-on-error -jobname=resume -output-directory=external resume_external.tex
pdflatex -interaction=nonstopmode -halt-on-error -jobname=resume -output-directory=external resume_external.tex
```

The second pass finalizes PDF metadata and hyperlinks. The generated file is
`standard/Resume.pdf` or `external/resume.pdf`, depending on the entry point.
The external-application variant places Education directly below the contact
header. Separate directories are required on case-insensitive filesystems.

If a minimal TeX Live installation reports that `fullpage.sty` is missing,
install the package bundle before compiling:

```bash
sudo tlmgr install preprint
```

## Repository structure

- `resume.tex` — canonical resume content, formatting, links, and default order
- `resume_external.tex` — external-application entry point with Education first
- `.gitignore` — generated LaTeX files and local tooling exclusions

Generated build artifacts, including `resume.pdf`, are intentionally excluded
from version control.

## Template credit

The LaTeX structure is based on the
[sb2nov resume template](https://github.com/sb2nov/resume), originally authored
by Jake Gutierrez and distributed under the MIT License.
