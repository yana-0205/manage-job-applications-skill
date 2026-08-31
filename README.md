# Manage Job Applications — an End-to-End Codex Skill

> Upload a job link or paste the JD, then give one instruction: **“Apply for this role.”**

From role analysis and eligibility screening to tailored documents, file management, and application tracking, this skill turns a fragmented application process into one repeatable workflow.

## What can one instruction do?

1. **Screen hard requirements first:** Check visa sponsorship, required years of experience, graduation cohort, education, language, work location, and other conditions that may determine whether the candidate can enter the hiring process.

2. **Break down the JD and ATS keywords:** Extract responsibilities, core requirements, tools, skills, domain terms, and repeated keywords. Separate mandatory requirements from preferences and improve the resume's relevance and discoverability for ATS screening without keyword stuffing or making unsupported claims.

3. **Score the match and decide whether the current resume is ready:** Map each important JD requirement to verified candidate evidence, report an overall match score out of 10, and recommend either `Use the existing resume` or `Create a new tailored resume` instead of rewriting every application by default.

4. **Create evidence-based application materials:** Apply professional resume-editing principles to the positioning, experience order, project emphasis, and bullet structure. Produce a tailored one-page resume and cover letter while preventing invented skills, metrics, or outcomes.

5. **Manage application files automatically:** Keep the current application's canonical DOCX/PDF files in `present/`, archive previous versions under `history/<Company>/<Role>/`, and clean up duplicate versions and temporary Office files.

6. **Maintain the application tracker automatically:** Detect previous applications, continue unfinished records, and populate the tracker's existing fields, including application date, company, role, status, next action, referrer, job ID, and job URL. Extract available values directly from the job link, JD, current application context, and system date without requiring a separate tracker prompt or asking the user to repeat known information.

## More than a resume-writing prompt

Most prompts stop at “rewrite my resume.” This skill manages the decisions, documents, and operational handoffs across the full application lifecycle:

`Job input → Duplicate check → Hard-requirement screen → JD/ATS analysis → Evidence mapping → Resume reuse decision → Document creation → DOCX/PDF render QA → File archiving → Tracker update`

It focuses on the parts generative AI often misses: deciding whether an application is worth pursuing, grounding every claim in real evidence, preserving verified metrics, checking the final rendered PDF, and leaving each application with clean, traceable files and records.

> One job link. One instruction. Complete analysis, submission-ready documents, and an updated application record.

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

## How to use it

The skill supports both **modular requests** and a **complete end-to-end application**. You do not need to describe the internal workflow or tell Codex which checks to run.

### Use any step independently

Attach a job link or paste the JD, then ask naturally:

```text
Analyse this job description.
```

```text
Check how well I match this role.
```

The match assessment includes an evidence-based overall score out of 10.

```text
What are the core responsibilities and ATS keywords for this role?
```

```text
Should I use my current resume or tailor a new one for this position?
```

```text
Tailor my resume for this role.
```

### Trigger the complete workflow with one prompt

```text
I want to apply for this role.
```

For an end-to-end request, Codex uses the skill to run the full workflow automatically: eligibility screening, JD and ATS analysis, a match score out of 10, resume reuse or tailoring decision, application-material creation, document QA, file management, and tracker maintenance. The final output includes the analysis, a submission-ready resume in both DOCX and PDF formats, a tailored cover letter, and an updated application record. No separate tracker request or repeated data entry is required.

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
