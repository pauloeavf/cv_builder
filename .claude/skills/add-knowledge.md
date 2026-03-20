---
name: add-knowledge
description: Interactively add or update entries in the knowledge base
user_invocable: true
---

# /add-knowledge — Manage Knowledge Base

You are helping the user add or update information in their knowledge base.

## Steps

1. **Ask what to update** (if not specified): Present the knowledge categories:
   - `profile.md` — Contact info & summary
   - `experience.md` — Work experience
   - `education.md` — Education & certifications
   - `skills.md` — Technical & soft skills
   - `preferences.md` — Tone, layout, priorities

2. **Read the target file** to see its current contents.

3. **Collect the new information** from the user through conversation.

4. **Merge with existing content**: Add new entries without removing or overwriting existing ones unless the user explicitly asks to replace something.

5. **Write the updated file** and show the user what changed.

## For Experience Entries
Help the user write strong bullet points:
- Start with action verbs
- Quantify impact where possible
- Focus on outcomes, not just duties
- Offer to rephrase if the user provides rough descriptions

## For Skills
- Ask the user to categorize new skills or suggest categories
- Avoid listing skills the user isn't comfortable being asked about in interviews

## Important
- Always show the user what will be written before saving.
- Never delete existing content unless explicitly asked.
