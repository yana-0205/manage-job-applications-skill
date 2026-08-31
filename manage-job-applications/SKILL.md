---
name: manage-job-applications
description: Manage evidence-based job applications from duplicate detection and hard-eligibility screening through JD analysis, resume reuse decisions, truthful ATS tailoring, cover-letter drafting, DOCX/PDF visual QA, safe file versioning, and application tracking. Use when the user wants to analyse a job description, decide whether to apply, tailor or reuse a resume, prepare application materials, organise resume history, or update an application tracker.
---

# Manage Job Applications

Treat the workspace `AGENTS.md` and user instructions as authoritative. Preserve verified candidate facts and never invent experience, metrics, credentials, tools, motivations, or eligibility.

Read `references/quality-checklist.md` before delivering application materials.

## Run the gates in order

### 1. Establish the application identity

Extract the company, role, location, recruitment market, stable job or requisition ID, and canonical URL. Strip tracking parameters from URLs.

If any item is missing, continue unless it blocks duplicate detection, eligibility, language, or file placement. Ask only for material missing information.

### 2. Check for an existing application

If a tracker exists, inspect it before analysing fit or changing files. Check in this order:

1. exact stable job or requisition ID;
2. exact canonical URL;
3. same company and materially identical role title.

If a match is already marked submitted, stop unless the user explicitly asks to reapply, refresh materials, or correct the record. If it is unfinished, continue the existing application and update the same row. Resolve ambiguous matches before creating a duplicate.

### 3. Screen hard eligibility

Evaluate requirements that could prevent entry into the hiring process:

- seniority and years of experience;
- graduation cohort or student status;
- degree, licence, certification, or regulated qualification;
- work authorisation, citizenship, clearance, sponsorship, location, relocation, travel, or shifts;
- mandatory language or technical experience;
- employment type and other explicit entry conditions.

Distinguish requirements from preferences. Classify every material gate as `meets`, `uncertain`, or `does not meet`, and lead with the overall conclusion.

If a material gate clearly fails, explain the likely screening consequence and pause before replacing current application files or drafting new documents. Continue only after the user acknowledges the mismatch and asks to proceed.

## Analyse fit with an evidence map

Extract the JD's core outcomes, responsibilities, repeated terms, tools, methods, domain vocabulary, and seniority signals. Map each important requirement to candidate evidence as:

- `strong evidence`;
- `adjacent or transferable evidence`;
- `unsupported`.

Keep hard eligibility separate from general fit. Use exact JD terminology only when it truthfully describes the evidence. If the user requests a score, explain it briefly and never let the number obscure a hard-gate failure.

For a short JD-analysis request, report:

1. eligibility conclusion;
2. core responsibilities;
3. ATS keywords;
4. strongest evidence matches;
5. gaps and unsupported requirements;
6. resume-positioning implications.

## Decide whether to reuse the current resume

Inspect the current resume when available.

Recommend `Use the existing resume` only when its positioning, evidence selection, responsibility coverage, supported ATS terminology, and layout already fit closely enough that changes would be negligible.

Recommend `Create a new tailored resume` when the target function, domain, summary, evidence priority, responsibility coverage, keywords, or layout needs a material change.

State the recommendation first, followed by two to four JD-grounded reasons and the most important risk or change.

## Plan the resume before writing

Choose a one-line role-specific positioning statement. Rank verified evidence by relevance and create a bullet-level evidence ledger. For every proposed bullet, record its source and classify its closure as:

- quantified scope or output;
- quantified result;
- verified delivery or decision milestone;
- qualitative exception because no reliable quantity exists.

Prefer this structure:

`Candidate-owned action + business context + supported scope or method + result or decision value`

Make individual ownership clear. Give every number context. Preserve strong verified metrics when they remain relevant. Do not add weak numbers merely to quantify a sentence.

Use this section order unless the workspace specifies another market-appropriate structure:

1. `SUMMARY`
2. `WORK EXPERIENCE`
3. `PROJECT EXPERIENCE`
4. `EDUCATION`
5. `ADDITIONAL`

Keep professional employment separate from projects. Tailor the summary, evidence order, bullet emphasis, and skills vocabulary to the JD without keyword stuffing.

## Draft a complementary cover letter

Create a cover letter only when requested or when the workspace workflow explicitly includes one.

Use a concise progression:

1. professional positioning and specific motivation;
2. one insight or interest grounded in verified experience;
3. working style and transferable capability supported by one or two factual anchors;
4. connection to the role, intended contribution, and restrained close.

Do not paraphrase the resume line by line. Include at least one grounded sentence about professional judgement, working preference, or why the work matters to the candidate. Reject claims that could be pasted unchanged into most applicants' letters.

## Manage files safely

Read the workspace's file policy before changing application files. Inventory current and historical materials and inspect modification times.

For a new application, archive the previous canonical resume pair before adding the new pair. Keep one current DOCX and one matching PDF per application. Treat `Final`, `Updated`, `Revised`, dated, and version-suffixed files as versions, not separate applications.

Never:

- overwrite a historical file silently;
- delete an ambiguous file;
- treat Office lock files beginning with `~$` as resumes;
- move or replace another market's or application's current files;
- archive temporary render or conversion artifacts.

Prefer stable filenames such as `<Candidate>_<Company>_<Role>.docx` and the matching `.pdf`.

## Produce and verify documents

Use the candidate's existing resume or provided DOCX template as the visual source of truth. Preserve its page geometry, typography, hierarchy, alignment, bullet treatment, and spacing unless the user asks for redesign.

Complete and visually approve the DOCX first. Export the PDF only from that exact final DOCX; never rebuild the PDF independently. After every DOCX change, regenerate and recheck the PDF.

Render and inspect every page. Confirm:

- the requested page limit is satisfied;
- there is no clipping, overlap, blank page, orphan heading, or broken bullet;
- spacing, dates, punctuation, fonts, margins, and alignment are consistent;
- the page is neither cramped nor conspicuously underfilled;
- DOCX and PDF have identical content, order, pagination, and line breaks.

If the resume is underfilled, restore stronger verified evidence before changing spacing. If it overflows, remove low-priority content before shrinking typography or margins.

## Update the tracker precisely

Edit a tracker only when requested or when the agreed workflow includes tracking. Inspect headers, formats, formulas, validations, and row conventions first. Treat existing headers as the complete schema.

Fill only values supported by the active JD, conversation, and current application files. Use the current system date for an application-date field. Leave unknown cells blank, preserve unrelated rows and formulas, and update an existing row instead of adding a duplicate.

## Report completion

Lead with the application decision or fit conclusion. Link the final deliverables, summarise the targeting choices, identify intentionally omitted unsupported requirements, and state whether files or the tracker changed.

For substantive resume revisions, provide a concise diff under `Added`, `Removed`, and `Rewritten`.
