# TASKS — teacher-lesson-plans

> Status: Draft · Version: 0.1.0 · Last updated: 2026-06-28 · Owner: TBD (maintainer) · Lane: donated

## How these tasks map to Elyos

Each task below becomes an Elyos **Task JSON** validated against
`packages/schema/src/schemas.ts`. Field mapping:

- `id` — stable slug ID from the tables (e.g. `teacher-lesson-plans-template-001`).
- `title` — the table's Title.
- `project` — `teacher-lesson-plans`.
- `type` — one of `code | research | writing | data | design-spec | maintenance` (per table).
- `lane` — `donated` for all current tasks (no funded escrow). A funded task would add
  `fundedBudgetUsd` (required by the schema's conditional).
- `priority` — `high | medium | low`.
- `domain` — array, e.g. `["education","oer","k12","open-content"]`.
- `riskTier` — `low | medium | high`. **Default `low`**; **`medium`** for any sensitive-subject plan
  (health, safety, sexuality, religion, contested civic/history) — those require subject-expert sign-off.
  No `high`-tier content is planned (credentialed-advice content is out of scope).
- `urgent` — boolean; `false` for all current tasks.
- `deliverable` — `pr | dataset | document | translation`. Lesson plans + checklists + docs →
  `document`; tooling/exporters/validators → `pr`; localized plans → `translation`. We never emit
  `dataset` (we don't publish source data).
- `tokenEstimate` — `small | medium | large` (the Size column).
- `status` — `open | in-progress | review | delivered | done`; all start `open`.
- `context`, `objective`, `acceptanceCriteria[]`, `resources[]`, `output` — per task.
- `requestor` — **TO BE SECURED** until a partner (teacher/school/repository) is confirmed.
- `verifiedNeed` — **`false`** until a named partner agrees to adopt/use contributions. The *general*
  need is real; the *per-plan delivery* need is unproven until then.
- `outputLicense` — **`CC-BY-4.0`** for lesson-plan content and docs **by default**; `CC-BY-SA-4.0`
  when a plan wraps share-alike sources; `MIT` for code (validators/exporters/tooling).

---

## Milestone M0 — Foundation & cold-start

| ID | Title | Type | Size | Risk | Deliverable | Depends on | Reviewer |
| --- | --- | --- | --- | --- | --- | --- | --- |
| teacher-lesson-plans-template-001 | Canonical lesson-plan schema + authoring template | writing | small | low | document | — | Pedagogy/standards |
| teacher-lesson-plans-reviewer-002 | Name/secure pedagogy/standards reviewer (blocking gate role) | research | small | low | document | — | Maintainer |
| teacher-lesson-plans-license-003 | OER license gate checklist + composed-license rule | design-spec | small | medium | document | — | License |
| teacher-lesson-plans-standards-004 | Standards-alignment model + framework-license policy | design-spec | small | medium | document | template-001 | License, Pedagogy/standards |
| teacher-lesson-plans-udl-005 | Accessibility/UDL + age-appropriateness checklists | design-spec | small | low | document | template-001 | Pedagogy/standards |
| teacher-lesson-plans-validator-006 | Schema validator + golden fixtures (CI) | code | small | low | pr | template-001 | Technical |
| teacher-lesson-plans-outreach-007 | Partner/repository outreach + pilot shortlist | research | small | low | document | — | Steward |
| teacher-lesson-plans-pilot-008 | One pilot lesson plan, end-to-end (both gates) | writing | medium | low | document | template-001, reviewer-002, license-003, standards-004, udl-005, validator-006, outreach-007 | License, Pedagogy/standards |

**Acceptance criteria — key tasks**

- **template-001 (canonical schema + template)**
  - [ ] Canonical model documents every field: title, gradeBand, subject, durationMinutes,
        objectives[], standards[] {framework, code, descriptor?, alignmentRationale,
        descriptorLicenseOk}, materials[], priorKnowledge[], procedure[] {phase, minutes, teacherDoes,
        studentsDo}, formativeChecks[], differentiation {support[], extension[], languageSupports[],
        udlNotes}, accessibility {plainLanguage, altTextPresent, structureNotes}, answerKey?,
        sources[] {title, author, url, license{id,url,permitsDerivatives,shareAlike,nonCommercial,snapshotRef}, attributionText},
        outputLicense, provenance, sensitiveSubject {flag, reason, framing}.
  - [ ] Markdown + YAML front-matter authoring template covers all of the above with inline guidance.
  - [ ] Template states explicitly that the deliverable is a plan, not the source OER, and defaults
        the content license to CC-BY-4.0 (CC-BY-SA-4.0 when wrapping share-alike sources).
  - [ ] At least one filled-in worked skeleton included.
  - [ ] DCO sign-off; any committed tooling passes `pnpm build && pnpm test && pnpm lint`.

- **license-003 (OER license gate + composed-license rule)**
  - [ ] Enumerates accepted licenses (CC0, PD, CC-BY, CC-BY-SA), the NC quarantine policy, and
        excluded categories (ND, all-rights-reserved, unstated/ambiguous → EXCLUDE).
  - [ ] Objective criterion: PASS only if `permitsDerivatives: true` is set from a **cited clause/URL**;
        missing/unparseable evidence = EXCLUDE (no default-allow).
  - [ ] Records `permitsDerivatives` / `shareAlike` / `nonCommercial` booleans + the citing clause, and
        a license snapshot (committed copy + SHA-256 + Wayback URL).
  - [ ] Defines the **composed-license rule** (plan license = most restrictive compatible across
        sources; SA → CC-BY-SA; NC → quarantined NC tier, never blended/relicensed).
  - [ ] Produces a committed PASS/FLAG/EXCLUDE artifact per source.

- **standards-004 (alignment model + framework-license policy)**
  - [ ] Defines machine-readable alignment (framework + stable code + rationale), emittable as
        CASE/LRMI `alignmentObject` later.
  - [ ] Framework-license policy: descriptor text reproduced **only** within the framework's verified
        license terms with the required notice (CCSS, NGSS handled specifically); default is code+link.
  - [ ] Forbids fabricated alignments: a plan with no honest alignment ships **unaligned and labelled**.

- **pilot-008 (end-to-end pilot plan)**
  - [ ] All sources passed license-003 (committed artifacts; attribution blocks present; composed
        license computed).
  - [ ] Pedagogy/standards reviewer signed off: objectives sound, age-appropriate, alignment correct,
        teachable in stated time, answer key correct, UDL/differentiation present.
  - [ ] Schema-valid; reading level within grade band; metadata valid; links resolve.
  - [ ] Exported to Markdown (canonical) + print PDF/HTML.
  - [ ] **Taught by a pilot teacher** (or accepted to an open repository) with adoption evidence in
        the outcome ledger — or published with the blocker surfaced and `verifiedNeed` left `false`.

**M0 Definition of Done:** pedagogy/standards reviewer named (blocking role filled before any plan
review); canonical schema + template, license gate + composed-license rule, standards-alignment model
+ framework-license policy, and UDL/age-appropriateness checklists all published; schema validator
green in CI with golden fixtures; **one** pilot plan authored end-to-end with both gate artifacts
committed, exported, and **taught or repository-accepted** (evidence recorded) — or published with the
blocker surfaced; ≥ 1 partner-outreach thread opened.

---

## Milestone M1 — Gates hardened + first adoptions

| ID | Title | Type | Size | Risk | Deliverable | Depends on | Reviewer |
| --- | --- | --- | --- | --- | --- | --- | --- |
| teacher-lesson-plans-snapshot-009 | License-snapshot + attribution-completeness checker | code | small | low | pr | template-001, license-003 | Technical |
| teacher-lesson-plans-readability-010 | Reading-level + sensitive-subject detector (CI) | code | small | low | pr | udl-005 | Technical |
| teacher-lesson-plans-casemeta-011 | CASE/LRMI alignment metadata emitter + validator | code | medium | low | pr | standards-004, validator-006 | Technical |
| teacher-lesson-plans-unit-012 | Author a coherent 3–5 plan unit (one subject/grade) | writing | large | low | document | pilot-008, casemeta-011 | License, Pedagogy/standards |
| teacher-lesson-plans-partner-013 | Secure first confirmed adopting partner | research | small | low | document | outreach-007 | Steward |
| teacher-lesson-plans-sensitive-014 | One sensitive-subject plan via the medium-risk path | writing | medium | medium | document | unit-012, reviewer-002 | License, Pedagogy/standards, Subject expert |

**Acceptance criteria — key tasks**

- **snapshot-009 (snapshot + attribution checker)**
  - [ ] Implements the decided snapshot format (committed copy + SHA-256 + Wayback URL); bare URL
        insufficient.
  - [ ] Attribution-completeness check fails the build if any source lacks a complete attribution block
        (title, author, source, license, link, changes-made).
  - [ ] Code MIT; tests + CI green; no credentials embedded.

- **unit-012 (3–5 plan unit)**
  - [ ] Every plan passes both gates with committed artifacts; CASE/LRMI metadata emitted + valid.
  - [ ] Plans form a coherent sequence (shared subject/grade band, building objectives).
  - [ ] ≥ 1 plan **taught** by a real teacher with structured feedback recorded (content-only, no
        student data).

- **partner-013 (first confirmed partner)**
  - [ ] A named teacher/school/repository confirms they will adopt/use contributed plans.
  - [ ] Adoption mechanism documented (classroom use vs. repository submission).
  - [ ] Affected tasks updated to `verifiedNeed: true` with `requestor` set.

- **sensitive-014 (sensitive-subject plan)**
  - [ ] Correctly flagged `sensitiveSubject` and escalated to `riskTier: medium`.
  - [ ] Subject-matter expert signed off accuracy, balance, and "education, not advice" framing.
  - [ ] Non-partisan, age-appropriate, inclusive; sources cited.

**M1 Definition of Done:** snapshot + attribution checker and reading-level/sensitive detector green in
CI; CASE/LRMI metadata emitted + validated per plan; ≥ 3 plans authored with both gates passed and
≥ 1 taught with feedback recorded; ≥ 1 confirmed adopting partner (affected tasks → `verifiedNeed:
true`); ≥ 1 sensitive-subject plan correctly escalated and expert-reviewed (or explicitly none authored).

---

## Milestone M2 — Export, interoperability & scale

| ID | Title | Type | Size | Risk | Deliverable | Depends on | Reviewer |
| --- | --- | --- | --- | --- | --- | --- | --- |
| teacher-lesson-plans-pdf-015 | Markdown → print PDF/HTML exporter (fixtures) | code | medium | low | pr | template-001, validator-006 | Technical |
| teacher-lesson-plans-cc-016 | IMS Common Cartridge / Thin CC export (fixtures) | code | medium | low | pr | template-001, casemeta-011 | Technical |
| teacher-lesson-plans-repo-017 | OER repository submission channel + acceptance flow | research | small | low | document | partner-013 | Steward |
| teacher-lesson-plans-scale-018 | Scale library to ≥ 10 plans across units | writing | large | low | document | unit-012, pdf-015, cc-016, repo-017 | License, Pedagogy/standards |

**Acceptance criteria — key tasks**

- **cc-016 (Common Cartridge export)** *(pattern also applies to pdf-015)*
  - [ ] Emits a valid IMS Common Cartridge / Thin CC package against the **pinned spec version**
        (recorded in `specVersions`); pdf-015 emits accessible, print-ready PDF/HTML.
  - [ ] Ships committed golden input→output fixtures diffed in CI; output validated against the spec.
  - [ ] Round-trip verified by importing into at least one open LMS (or a captured import schema where
        no sandbox exists).
  - [ ] Code MIT; tests + CI green; no credentials embedded.

- **scale-018 (≥ 10 plans)**
  - [ ] ≥ 10 plans published cumulatively, each both-gates-passed with committed artifacts.
  - [ ] ≥ 5 adopted (taught or repository-accepted) with evidence in the outcome ledger.
  - [ ] Median author→review→deliver cycle time recorded and improving vs. the M0/M1 baseline.

**M2 Definition of Done:** print PDF/HTML + Common Cartridge exporters fixture-tested and green in CI
(pinned spec versions); LRMI/CASE metadata emitted + valid per plan; ≥ 1 repository submission channel
working with acceptance evidence; ≥ 10 plans published, ≥ 5 adopted; cycle-time baseline recorded and
improving.

---

## Milestone M3 — Classroom outcomes & sustainability

| ID | Title | Type | Size | Risk | Deliverable | Depends on | Reviewer |
| --- | --- | --- | --- | --- | --- | --- | --- |
| teacher-lesson-plans-feedback-019 | Teacher-feedback loop + outcome ledger | design-spec | small | low | document | partner-013 | Steward |
| teacher-lesson-plans-refresh-020 | Staleness/refresh process (links, standards, sources) | maintenance | small | low | document | snapshot-009 | Maintainer |
| teacher-lesson-plans-a11y-021 | Full accessibility audit of delivered plans | research | small | low | document | scale-018 | Accessibility |
| teacher-lesson-plans-reuse-022 | Track & verify external reuse/adoption events | research | small | low | document | scale-018, feedback-019 | Steward |

**Acceptance criteria — key tasks**

- **feedback-019 (feedback loop + ledger)**
  - [ ] Content-only, anonymous teacher feedback form (no student/teacher PII).
  - [ ] Outcome ledger records, per plan: who taught/accepted it, date, usefulness rating, reuse events.
  - [ ] ≥ 80% usefulness rating across piloted plans reported (honestly caveated).

- **refresh-020 (staleness/refresh)**
  - [ ] Detects dead source links, revised standards, and updated source OER; spawns `maintenance` tasks.
  - [ ] Stale plans are flagged (not silently left wrong); refresh owner identified.

- **reuse-022 (reuse tracking)**
  - [ ] ≥ 3 verifiable external reuse/adoption events recorded (repository acceptance, fork,
        translation, or independent teacher reuse) — each with externally verifiable evidence.

**M3 Definition of Done:** ≥ 25 plans taught/adopted cumulatively; teacher-feedback loop + outcome
ledger operating with ≥ 80% usefulness; staleness/refresh process documented and owned; ≥ 1 full a11y
audit completed; ≥ 3 verifiable external reuse events; maintainer/steward/reviewer rotation confirmed.

---

## Backlog / future

| ID | Title | Type | Size | Risk | Deliverable | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| teacher-lesson-plans-i18n-023 | Localize a delivered plan (language + pedagogy reviewer) | translation | medium | medium | translation | Needs per-language reviewer; widens reach |
| teacher-lesson-plans-framework-024 | Add a second standards framework (non-US) | design-spec | medium | medium | document | Depends on framework-anchor decision |
| teacher-lesson-plans-dash-025 | Outcome/adoption dashboard (reads the ledger) | code | medium | low | pr | Supports success-metric reporting |
| teacher-lesson-plans-funded-026 | Funded-lane pilot to accelerate prioritized backlog | writing | medium | low | document | Requires `fundedBudgetUsd` + hard per-task cap |
| teacher-lesson-plans-nc-policy-027 | Board decision + policy on the NC tier | design-spec | small | medium | document | Resolves Open Question #3 |

---

## Example task JSON

```json
{
  "id": "teacher-lesson-plans-template-001",
  "title": "Canonical lesson-plan schema + authoring template",
  "project": "teacher-lesson-plans",
  "type": "writing",
  "lane": "donated",
  "priority": "high",
  "domain": ["education", "oer", "k12", "open-content"],
  "riskTier": "low",
  "urgent": false,
  "deliverable": "document",
  "tokenEstimate": "small",
  "status": "open",
  "context": "Open Educational Resources are abundant but rarely teachable as-is: a teacher still has to write objectives, align to standards, sequence the period, build formative checks, differentiate, and attribute sources. Before authoring any specific lesson plan, the project needs one canonical, structured lesson-plan model and a reusable authoring template that every plan (and every later exporter and metadata emitter) projects from. The deliverable is a lesson plan wrapping vetted OER, never the source content itself.",
  "objective": "Create the canonical lesson-plan schema and the reusable Markdown + YAML front-matter authoring template that all per-plan tasks, validators, and exporters will use.",
  "acceptanceCriteria": [
    "Canonical model documents every field: title, gradeBand, subject, durationMinutes, objectives[], standards[] {framework, code, descriptor?, alignmentRationale, descriptorLicenseOk}, materials[], priorKnowledge[], procedure[] {phase, minutes, teacherDoes, studentsDo}, formativeChecks[], differentiation {support[], extension[], languageSupports[], udlNotes}, accessibility {plainLanguage, altTextPresent, structureNotes}, answerKey?, sources[] {title, author, url, license {id, url, permitsDerivatives, shareAlike, nonCommercial, snapshotRef}, attributionText}, outputLicense, provenance, sensitiveSubject {flag, reason, framing}.",
    "Markdown + YAML front-matter template covers all model fields with inline authoring guidance, including UDL/differentiation and a per-source attribution block.",
    "Template explicitly states the deliverable is a lesson plan wrapping OER (not the source content), and defaults the content license to CC-BY-4.0 (CC-BY-SA-4.0 when wrapping share-alike sources).",
    "At least one filled-in worked example skeleton is included to guide contributors.",
    "pnpm build && pnpm test && pnpm lint pass for any committed tooling; commit is DCO signed-off."
  ],
  "resources": [
    "C:\\code\\elyos\\planning\\projects\\teacher-lesson-plans\\PLAN.md",
    "Creative Commons license suite (CC0, CC-BY, CC-BY-SA, CC-BY-NC) and compatibility guidance",
    "schema.org / LRMI LearningResource and alignmentObject",
    "UDL (Universal Design for Learning) guidelines",
    "OER sources: OpenStax, CK-12, OER Commons, Curriki, Siyavula"
  ],
  "output": "A canonical lesson-plan schema definition plus a reusable Markdown + YAML authoring template, committed to the project repo and ready for reuse by all per-plan authoring, validation, and export tasks.",
  "requestor": "TO BE SECURED",
  "verifiedNeed": false,
  "outputLicense": "CC-BY-4.0"
}
```

---

## Backlog rollup

- **22 scheduled tasks** across M0–M3 (M0: 8, M1: 6, M2: 4, M3: 4) plus **5 backlog tasks** = **27**
  well-formed tasks.
- Two **hard, non-skippable gates** gate every published plan: the **license gate** (`license-003`,
  enforced by `snapshot-009`) and the **pedagogy/standards gate** (`reviewer-002`), with a
  **subject-expert escalation** (`sensitive-014`) for `medium`-risk plans.
- All current tasks: `lane: donated`, `verifiedNeed: false`, `requestor: TO BE SECURED` until a
  partner is confirmed (flips at `partner-013`). Default `outputLicense: CC-BY-4.0` (CC-BY-SA-4.0 when
  wrapping share-alike sources; `MIT` for code).
- No silent caps: success is measured by **plans actually taught/adopted**, not authored — the
  milestone targets pull from real adoption evidence in the outcome ledger.

---

## Generated task index

> Auto-generated by Elyos task-decomposition agent on 2026-06-29.
> All 27 task JSON files are in `tasks/` and pass schema validation.

| File | Title | Type | Lane | Priority | Deliverable | Token | Risk |
| --- | --- | --- | --- | --- | --- | --- | --- |
| [teacher-lesson-plans-template-001.json](tasks/teacher-lesson-plans-template-001.json) | Canonical lesson-plan schema + authoring template | writing | donated | high | document | small | low |
| [teacher-lesson-plans-reviewer-002.json](tasks/teacher-lesson-plans-reviewer-002.json) | Name/secure pedagogy/standards reviewer (blocking gate role) | research | donated | high | document | small | low |
| [teacher-lesson-plans-license-003.json](tasks/teacher-lesson-plans-license-003.json) | OER license gate checklist + composed-license rule | design-spec | donated | high | document | small | medium |
| [teacher-lesson-plans-standards-004.json](tasks/teacher-lesson-plans-standards-004.json) | Standards-alignment model + framework-license policy | design-spec | donated | high | document | small | medium |
| [teacher-lesson-plans-udl-005.json](tasks/teacher-lesson-plans-udl-005.json) | Accessibility/UDL + age-appropriateness checklists | design-spec | donated | high | document | small | low |
| [teacher-lesson-plans-validator-006.json](tasks/teacher-lesson-plans-validator-006.json) | Schema validator + golden fixtures (CI) | code | donated | high | pr | small | low |
| [teacher-lesson-plans-outreach-007.json](tasks/teacher-lesson-plans-outreach-007.json) | Partner/repository outreach + pilot shortlist | research | donated | high | document | small | low |
| [teacher-lesson-plans-pilot-008.json](tasks/teacher-lesson-plans-pilot-008.json) | One pilot lesson plan, end-to-end (both gates) | writing | donated | high | document | medium | low |
| [teacher-lesson-plans-snapshot-009.json](tasks/teacher-lesson-plans-snapshot-009.json) | License-snapshot + attribution-completeness checker | code | donated | medium | pr | small | low |
| [teacher-lesson-plans-readability-010.json](tasks/teacher-lesson-plans-readability-010.json) | Reading-level + sensitive-subject detector (CI) | code | donated | medium | pr | small | low |
| [teacher-lesson-plans-casemeta-011.json](tasks/teacher-lesson-plans-casemeta-011.json) | CASE/LRMI alignment metadata emitter + validator | code | donated | medium | pr | medium | low |
| [teacher-lesson-plans-unit-012.json](tasks/teacher-lesson-plans-unit-012.json) | Author a coherent 3-5 plan unit (one subject/grade) | writing | donated | medium | document | large | low |
| [teacher-lesson-plans-partner-013.json](tasks/teacher-lesson-plans-partner-013.json) | Secure first confirmed adopting partner | research | donated | high | document | small | low |
| [teacher-lesson-plans-sensitive-014.json](tasks/teacher-lesson-plans-sensitive-014.json) | One sensitive-subject plan via the medium-risk path | writing | donated | medium | document | medium | medium |
| [teacher-lesson-plans-pdf-015.json](tasks/teacher-lesson-plans-pdf-015.json) | Markdown to print PDF/HTML exporter (fixtures) | code | donated | medium | pr | medium | low |
| [teacher-lesson-plans-cc-016.json](tasks/teacher-lesson-plans-cc-016.json) | IMS Common Cartridge / Thin CC export (fixtures) | code | donated | medium | pr | medium | low |
| [teacher-lesson-plans-repo-017.json](tasks/teacher-lesson-plans-repo-017.json) | OER repository submission channel + acceptance flow | research | donated | medium | document | small | low |
| [teacher-lesson-plans-scale-018.json](tasks/teacher-lesson-plans-scale-018.json) | Scale library to 10 or more plans across units | writing | donated | medium | document | large | low |
| [teacher-lesson-plans-feedback-019.json](tasks/teacher-lesson-plans-feedback-019.json) | Teacher-feedback loop + outcome ledger | design-spec | donated | medium | document | small | low |
| [teacher-lesson-plans-refresh-020.json](tasks/teacher-lesson-plans-refresh-020.json) | Staleness/refresh process (links, standards, sources) | maintenance | donated | low | document | small | low |
| [teacher-lesson-plans-a11y-021.json](tasks/teacher-lesson-plans-a11y-021.json) | Full accessibility audit of delivered plans | research | donated | low | document | small | low |
| [teacher-lesson-plans-reuse-022.json](tasks/teacher-lesson-plans-reuse-022.json) | Track and verify external reuse/adoption events | research | donated | low | document | small | low |
| [teacher-lesson-plans-i18n-023.json](tasks/teacher-lesson-plans-i18n-023.json) | Localize a delivered plan (language + pedagogy reviewer) | writing | donated | low | translation | medium | medium |
| [teacher-lesson-plans-framework-024.json](tasks/teacher-lesson-plans-framework-024.json) | Add a second standards framework (non-US) | design-spec | donated | low | document | medium | medium |
| [teacher-lesson-plans-dash-025.json](tasks/teacher-lesson-plans-dash-025.json) | Outcome/adoption dashboard (reads the ledger) | code | donated | low | pr | medium | low |
| [teacher-lesson-plans-funded-026.json](tasks/teacher-lesson-plans-funded-026.json) | Funded-lane pilot to accelerate prioritized backlog | writing | funded | low | document | medium | low |
| [teacher-lesson-plans-nc-policy-027.json](tasks/teacher-lesson-plans-nc-policy-027.json) | Board decision + policy on the NC tier | design-spec | donated | low | document | small | medium |
