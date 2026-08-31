# Job application workspace

## Candidate evidence

Treat files in `sources/` and facts explicitly confirmed by the user as the only authoritative candidate evidence. Never invent experience, metrics, credentials, tools, employment dates, eligibility, or motivation.

## File layout

- Keep the current application's canonical DOCX/PDF resume pair in `output/present/`.
- Archive prior pairs under `output/history/<Company>/<Role>/`.
- Never overwrite a same-named historical file; use a date or version suffix when needed.
- Keep exactly one latest DOCX and one latest PDF for each application.
- Remove Office lock files beginning with `~$` only after confirming they are not active.

## Resume format

- Start from the candidate's supplied DOCX template or current resume.
- Keep the resume to one page unless the user specifies otherwise.
- Use the order `SUMMARY`, `WORK EXPERIENCE`, `PROJECT EXPERIENCE`, `EDUCATION`, `ADDITIONAL`.
- Preserve template geometry, typography, hierarchy, bullet treatment, alignment, and spacing unless redesign is requested.
- Approve the DOCX render first; export PDF only from the final DOCX and verify both renders.

## Tracking

- Treat existing spreadsheet headers as the complete schema.
- Update an existing matching row instead of creating a duplicate.
- Treat an end-to-end application request as authorization to update the tracker automatically.
- Populate supported fields such as application date, company, role, status, next action, referrer, job ID, and URL from the job page, JD, active context, current application files, and system date.
- Preserve formulas, validations, formatting, and unrelated rows.
- Leave unsupported fields blank.
