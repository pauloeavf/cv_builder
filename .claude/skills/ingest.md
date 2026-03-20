---
name: ingest
description: Parse an existing CV into structured knowledge files
user_invocable: true
---

# /ingest — Import Existing CV

You are helping the user bootstrap their knowledge base by extracting structured information from an existing CV.

## Input
The user provides a path to their existing CV. Supported formats: DOC, DOCX, PDF, Markdown, LaTeX, plain text.

## Steps

1. **Read the file** at the provided path. For PDFs, use the Read tool which supports PDF files. For DOC and DOCX, use the Read tool which support those formats.

2. **Extract structured information** into these categories:
   - **Profile**: name, contact details, professional summary
   - **Experience**: each role with company, title, dates, location, and bullet points
   - **Education**: degrees, institutions, dates, highlights
   - **Skills**: categorized (languages, frameworks, tools, databases, methodologies, soft skills)

3. **Read existing knowledge files** in `knowledge/` to understand what's already there.

4. **Merge, don't overwrite**: If knowledge files already have content, merge the new information with existing entries. Never delete existing data.

5. **Present the extracted information** to the user in a clear summary and ask them to confirm or correct it before writing.

6. **Write the confirmed information** to the appropriate `knowledge/` files.

## Important
- Preserve the user's original phrasing for bullet points — don't rephrase unless asked.
- If something is ambiguous (e.g., unclear dates, vague role titles), ask the user to clarify.
- Flag any information that seems incomplete (e.g., a role with no bullet points).
