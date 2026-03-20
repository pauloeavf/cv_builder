# CV Builder — Project Instructions

This is a CV tailoring tool powered by Claude Code. It helps the user create tailored CVs and cover letters for specific job applications.

## How It Works

- All knowledge about the user lives in `knowledge/` (profile, experience, education, skills, preferences)
- Job descriptions are stored in `jobs/` as markdown files named `<company>_<role>.md`
- LaTeX templates in `templates/` define the visual layout
- Tailored output goes to `output/<company>_<role>/`

## Key Behaviors

1. **Always read the full `knowledge/` folder** before generating any CV or cover letter. Every file matters.
2. **Always read the target job description** to understand what to emphasize.
3. **Respect `knowledge/preferences.md`** — the user's tone, layout choices, and priorities must be preserved.
4. **Output to the correct directory**: `output/<company>_<role>/` matching the job file name.
5. **Use LaTeX templates** from `templates/` as the base structure. Adapt content, not layout.
6. **Never fabricate experience**. If a skill or experience seems relevant but isn't in `knowledge/`, ask the user: _"Do you have experience with X? It would strengthen this application."_
7. **Merge, don't overwrite** when updating knowledge files (e.g., via `/ingest` or `/add-knowledge`).

## Slash Commands

- `/ingest <path>` — Parse an existing CV into `knowledge/` files
- `/tailor <job-file>` — Generate a tailored CV for a job description
- `/cover-letter <job-file>` — Generate a tailored cover letter
- `/add-knowledge` — Interactively add/update knowledge entries
- `/compile [path]` — Compile LaTeX files to PDF

## File Naming Convention

Job files: `jobs/<company>_<role>.md` (lowercase, underscores)
Output dirs: `output/<company>_<role>/`

Example: `jobs/google_senior_swe.md` → `output/google_senior_swe/`
