# Manage Job Applications — an End-to-End Codex Skill

> Upload a job link or paste the JD, then give one instruction: **“Apply for this role.”**

From role analysis and eligibility screening to tailored documents, file management, and application tracking, this skill turns a fragmented application process into one repeatable workflow.

## What can one instruction do?

1. **Screen hard requirements first:** Check visa sponsorship, required years of experience, graduation cohort, education, language, work location, and other conditions that may determine whether the candidate can enter the hiring process.

2. **Break down the JD and ATS keywords:** Extract responsibilities, core requirements, tools, skills, domain terms, and repeated keywords. Separate mandatory requirements from preferences and improve the resume's relevance and discoverability for ATS screening without keyword stuffing or making unsupported claims.

3. **Decide whether the current resume is ready:** Map each important JD requirement to verified candidate evidence, assess the match, and recommend either `Use the existing resume` or `Create a new tailored resume` instead of rewriting every application by default.

4. **Create evidence-based application materials:** Apply professional resume-editing principles to the positioning, experience order, project emphasis, and bullet structure. Produce a tailored one-page resume and cover letter while preventing invented skills, metrics, or outcomes.

5. **Manage application files automatically:** Keep the current application's canonical DOCX/PDF files in `present/`, archive previous versions under `history/<Company>/<Role>/`, and clean up duplicate versions and temporary Office files.

6. **Maintain the application tracker:** Detect previous applications, continue unfinished records, and update the existing tracker schema without creating duplicate rows or damaging formulas and formatting.

## More than a resume-writing prompt

Most prompts stop at “rewrite my resume.” This skill manages the decisions, documents, and operational handoffs across the full application lifecycle:

`Job input → Duplicate check → Hard-requirement screen → JD/ATS analysis → Evidence mapping → Resume reuse decision → Document creation → DOCX/PDF render QA → File archiving → Tracker update`

It focuses on the parts generative AI often misses: deciding whether an application is worth pursuing, grounding every claim in real evidence, preserving verified metrics, checking the final rendered PDF, and leaving each application with clean, traceable files and records.

> One job link. One instruction. A complete, evidence-based application workflow.

## Install

Copy the skill folder into your Codex skills directory:

```bash
cp -R manage-job-applications ~/.codex/skills/
```

Restart Codex if the skill does not appear immediately.

## Project setup

Create a job-application workspace containing:

```text
job-applications/
├── AGENTS.md
├── records-of-applications.xlsx       # optional
├── sources/                           # verified resumes and evidence
└── output/
    ├── present/
    └── history/
```

Use [`examples/AGENTS.md`](examples/AGENTS.md) as a starting point. Add your own resume source files and, if you want strict visual consistency, a DOCX resume template. Do not commit private candidate data to a public repository.

## Example prompts

```text
Analyse this JD and tell me whether I meet the hard requirements before tailoring anything.
```

```text
I want to apply for this role. Decide whether my current resume can be reused, then prepare the application materials.
```

```text
Tailor my resume to this JD, keep it to one page, and show me an evidence map before drafting.
```

```text
Clean up duplicate resume versions and update my application tracker without changing unrelated rows.
```

## Design principles

1. Eligibility before optimism.
2. Evidence before keywords.
3. One canonical editable document before PDF export.
4. Rendered output, not source text, determines whether a document is finished.
5. File operations are scoped, reversible where possible, and never cross application boundaries silently.

## Privacy

The repository contains no real resume, contact details, employment history, application tracker, or candidate-specific generation script. Keep those in your private workspace.

## License

MIT — see [`LICENSE`](LICENSE).
