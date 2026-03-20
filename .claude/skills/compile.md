---
name: compile
description: Compile LaTeX files to PDF
user_invocable: true
---

# /compile — Compile LaTeX to PDF

You are compiling LaTeX files into PDFs.

## Input
The user may provide:
- A specific `.tex` file path
- A job name (e.g., `google_swe`) to compile all files in `output/google_swe/`
- Nothing — compile the most recently modified `.tex` files in `output/`

## Steps

1. **Determine which files to compile**:
   - If a specific path is given, compile that file.
   - If a job name is given, find all `.tex` files in `output/<job_name>/`.
   - If nothing is given, find the most recently modified `.tex` files in `output/`.

2. **Compile using pdflatex**:
   ```bash
   pdflatex -interaction=nonstopmode -output-directory=<dir> <file.tex>
   ```
   Run twice to resolve references if needed.

3. **Check for errors**: If compilation fails, read the `.log` file, diagnose the issue, and either fix it or report it to the user.

4. **Clean up auxiliary files**: Remove `.aux`, `.log`, `.out` files after successful compilation.

5. **Report results**: Tell the user which PDFs were generated and their paths.

## Troubleshooting
- If `pdflatex` is not installed, suggest: `sudo apt install texlive-latex-base texlive-latex-recommended texlive-latex-extra`
- If fonts are missing, suggest installing `texlive-fonts-recommended`
- Common errors: missing packages, unescaped special characters (`&`, `%`, `#`, `_`)
