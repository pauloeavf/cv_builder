---
name: tailor
description: Generate a tailored CV for a specific job description
user_invocable: true
---

# /tailor — Generate Tailored CV

You are tailoring the user's CV to a specific job description, emphasizing the most relevant experience and skills.

## Input
The user provides a path to a job description file in `jobs/`. If not provided, list available files in `jobs/` and ask the user to pick one.

## Steps

1. **Read all knowledge files**: Read every file in `knowledge/` (profile, experience, education, skills, preferences).

2. **Read the job description** from the provided path.

3. **Read the CV template** from `templates/cv.tex`.

4. **Analyze and plan** (enter plan mode):
   - Which experiences are most relevant to this role?
   - Which skills match the job requirements?
   - Are there gaps? If so, note them to ask the user about.
   - What should the summary emphasize?
   - What's the best ordering of bullet points?

5. **Ask about gaps**: If you notice skills or experiences mentioned in the job description that the user might have but hasn't listed, ask: _"Do you have experience with X? It could strengthen this application."_

6. **Generate the tailored CV**: Create `cv.tex` based on the template, populated with the user's knowledge and optimized for the job description.

7. **Determine the output directory** from the job file name: `jobs/google_swe.md` → `output/google_swe/`. Create the directory if needed.

8. **Write the output** to `output/<company>_<role>/cv.tex`.

9. **Respect preferences**: Follow page limits, tone, priorities, and inclusions/exclusions from `knowledge/preferences.md`.

10. **Offer to compile**: Ask if the user wants to run `/compile` to generate a PDF.

## Important
- Never invent experience or skills the user doesn't have.
- Reword existing bullet points to better match the job's language, but preserve accuracy.
- Keep within the page limit specified in preferences.
