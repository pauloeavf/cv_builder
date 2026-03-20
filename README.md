# CV Builder

A CV tailoring tool powered by Claude Code. Generates tailored CVs and cover letters for specific job applications using your knowledge base and LaTeX templates.

## Prerequisites

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) CLI installed
- LaTeX distribution installed (`sudo apt install texlive-latex-base texlive-latex-recommended texlive-latex-extra texlive-fonts-recommended`)

## Quick Start

### 1. Cold Start — Import Your Existing CV

Place your existing CV in `data/` and run:

```
/ingest data/my_cv.pdf
```

This parses your CV and populates the `knowledge/` files. Review and confirm the extracted information.

### 2. Add a Job Description

Save the job description as a markdown file in `jobs/`:

```
jobs/google_swe.md
jobs/stripe_backend_engineer.md
```

Use the format `<company>_<role>.md` (lowercase, underscores).

### 3. Tailor Your CV

```
/tailor jobs/google_swe.md
```

This reads your knowledge base, analyzes the job description, and generates a tailored `cv.tex` in `output/google_swe/`.

### 4. Generate a Cover Letter

```
/cover-letter jobs/google_swe.md
```

Generates a matching cover letter in the same output directory.

### 5. Compile to PDF

```
/compile google_swe
```

Compiles all `.tex` files in the output directory to PDF.

### 6. Update Your Knowledge

```
/add-knowledge
```

Interactively add or update your profile, experience, skills, or preferences.

## Project Structure

```
knowledge/     — Your profile, experience, education, skills, preferences
templates/     — LaTeX templates for CV and cover letter
jobs/          — Job descriptions (one file per application)
output/        — Generated tailored CVs and cover letters
data/          — Your source CV files for ingestion
```

## Customization

Edit `knowledge/preferences.md` to control:
- Tone (formal, professional, conversational)
- Page limits
- Which sections to prioritize
- Content to always include or exclude
