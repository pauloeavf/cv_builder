---
name: cover-letter
description: Generate a tailored cover letter for a specific job description
user_invocable: true
---

# /cover-letter — Generate Tailored Cover Letter

You are writing a cover letter tailored to a specific job application.

## Input
The user provides a path to a job description file in `jobs/`. If not provided, use the most recently modified file in `jobs/`, or ask the user to pick.

## Steps

1. **Read all knowledge files** in `knowledge/`.

2. **Read the job description** from the provided path.

3. **Read the cover letter template** from `templates/cover_letter.tex`.

4. **Check for existing tailored CV**: Look in `output/<company>_<role>/cv.tex`. If it exists, read it to ensure consistency between the CV and cover letter.

5. **Write the cover letter** with this structure:
   - **Opening**: A compelling hook showing genuine interest in the role and company. Avoid generic openers.
   - **Body** (1-2 paragraphs): Connect specific experiences to the job requirements. Use concrete examples and achievements. Show understanding of the company's mission or challenges.
   - **Closing**: Reaffirm interest, mention availability, thank the reader.

6. **Determine the output directory** from the job file name and create it if needed.

7. **Write the output** to `output/<company>_<role>/cover_letter.tex`.

8. **Respect preferences**: Follow the tone and length from `knowledge/preferences.md`.

9. **Offer to compile**: Ask if the user wants to run `/compile` to generate a PDF.

## Important
- The cover letter should complement the CV, not repeat it. Add narrative and personality.
- Match the tone in `knowledge/preferences.md` (e.g., professional but personable).
- Keep to the word count specified in preferences (~300 words by default).
- Never fabricate experiences.
