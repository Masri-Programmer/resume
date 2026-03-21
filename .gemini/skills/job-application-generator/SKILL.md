---
name: job-application-generator
description: Tailors your resume and generates a matching cover letter based on a job description. Use when a user provides a job description and wants to generate tailored application documents.
---

# Job Application Generator

This skill automates the process of tailoring your professional resume and writing a high-impact cover letter for a specific job opening.

## Workflow

When you receive a job description from the user, follow these steps:

### 1. Preparation
Identify the company name from the job description. If not clearly stated, ask the user or use a placeholder.

### 2. Tailor Resume
- **Source:** Read the base resume from `@index.html`.
- **Instruction:** Use the guidelines in `references/resume_prompt.md`.
- **Action:** Analyze the job description against the base resume. Identify key ATS keywords and apply the STAR method.
- **Output:** Generate the updated HTML code.
- **Save:** Save the file to `/jobs/resumes/[company-name].html`.

### 3. Generate Cover Letter
- **Source:** Use the tailored resume (from Step 2) and the original job description.
- **Instruction:** Use the guidelines in `references/cover_letter_prompt.md`.
- **Action:** Write a concise (under 300 words) cover letter highlighting the VILT-Stack expertise and addressing the top 3 requirements.
- **Output:** Generate the cover letter text in Markdown format.
- **Save:** Save the file to `/jobs/cover_letters/YYYY-MM-DD_[company-name].md`.

### 4. Final Review
Present the results to the user:
1. Link to the new tailored resume.
2. The full text of the cover letter.
3. A brief strategy note explaining the tailoring choices.

## References

- [resume_prompt.md](references/resume_prompt.md): Detailed instructions for ATS optimization and STAR method.
- [cover_letter_prompt.md](references/cover_letter_prompt.md): Guidelines for writing a persuasive, non-robotic cover letter.
