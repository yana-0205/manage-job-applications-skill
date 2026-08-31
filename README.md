# Manage Job Applications — a Codex Skill

An evidence-first workflow for turning a job description into a realistic application decision, a tailored one-page resume, an optional cover letter, and a clean application record.

This is not a resume-writing prompt. It is a reusable operating workflow with explicit gates for:

- duplicate-application detection;
- hard-eligibility screening before fit scoring;
- evidence-to-JD mapping and ATS terminology;
- resume reuse versus retailoring decisions;
- truthful, bullet-level evidence checks;
- DOCX-first authoring and rendered PDF QA;
- safe versioning and application tracking.

## Why I built it

Job applications tend to fail in the handoffs between analysis, writing, file management, and tracking. A resume can sound polished while missing a hard requirement, losing verified metrics, creating duplicate files, or producing a broken second PDF page. This skill treats the application as one controlled workflow instead of a series of disconnected prompts.

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
