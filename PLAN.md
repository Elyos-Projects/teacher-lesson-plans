# PLAN — teacher-lesson-plans

> Status: Draft · Version: 0.1.0 · Last updated: 2026-06-28 · Owner: TBD (maintainer) · Lane: donated

> **Positioning (one line):** Open, standards-aligned, *ready-to-teach* lesson plans that wrap
> existing openly-licensed educational content (OER) so a teacher can walk into class and teach —
> without rebuilding the wheel, hunting for resources, or paying a marketplace toll.

---

## Executive summary

Open Educational Resources (OER) are abundant but rarely *teachable as-is*. A teacher who finds an
openly-licensed reading passage, a simulation, or a problem set still has to do the hard, unpaid
work: write learning objectives, align to the standards their district mandates, sequence a class
period, build formative checks, differentiate for mixed-ability learners, prepare materials lists,
and assemble it all into something they can actually deliver tomorrow morning. That assembly labour
is the gap between "free content exists" and "a child got a good lesson." It is also exactly the gap
that commercial marketplaces (e.g. pay-per-download lesson sites) monetize.

**teacher-lesson-plans** closes that gap as a public good. It produces complete, classroom-ready
lesson plans — objective → standards alignment → materials → step-by-step procedure → formative
assessment → differentiation/UDL supports → answer keys — each one a thin, *correctly attributed*
wrapper around vetted OER source material, and each released under an open license so any teacher,
anywhere, can use, adapt, translate, and redistribute it for free.

The **deliverable is a lesson plan (a document/bundle), not the source content.** We do not mirror,
fork, or relicense the underlying OER beyond what its license permits; we compose, sequence, align,
and attribute. Each lesson plan is a self-contained unit of work suitable for a single donated AI
session plus human (teacher) review.

The project is **low risk** in the aggregate (general open educational content), but it is not
*zero* risk, and the plan refuses to pretend otherwise. The real risks are pedagogical and
editorial, not technical: (1) **license/attribution drift** — silently wrapping content whose
license forbids derivatives, omits attribution, or imposes share-alike/non-commercial terms we then
violate; (2) **factual / pedagogical inaccuracy** — wrong answer keys, misaligned standards,
age-inappropriate material; (3) **safeguarding / inclusivity** — content for children must be
age-appropriate, non-discriminatory, and non-partisan, and any sensitive subject (health, safety,
contested history, evolution, sexuality, religion) must be escalated to subject-expert review and
framed factually, never as personal/medical/legal advice. The plan front-loads a **license gate**
and a **pedagogy/standards review gate** as hard, non-skippable controls, and escalates sensitive
subjects to `medium` risk with mandatory subject-matter review.

No partner classroom, teacher network, or OER repository has yet agreed to accept and use these
plans. The *general* need is well established; the *per-plan, per-partner* need is **TO BE
SECURED**. Until a named teacher/school/repository confirms they will adopt contributions, tasks
carry `verifiedNeed: false`. This is deliberate: under Hee-Lee Oss's "delivered, not merged" bar, a lesson
plan is only a good deed once a real teacher teaches it (or a real repository accepts it for reuse),
not when it is merely authored.

---

## Problem & beneficiaries

**Who is helped (primary beneficiaries).**

- **Teachers** — especially the under-resourced: new teachers, out-of-field teachers, substitute
  teachers, teachers in low-income public schools, and teachers in under-served regions and
  languages. They are the direct users; the outcome is *hours of unpaid prep returned to them* and
  *higher-quality, standards-aligned instruction they can trust*.
- **Students** — the ultimate beneficiaries: better-prepared lessons, grounded in quality OER,
  accessible to mixed-ability learners (UDL), at no cost to their families or schools.
- **Homeschool families, tutors, and informal educators** — who need structured, sequenced material
  but lack institutional curriculum.

**Who is *also* helped (secondary).**

- **OER authors and repositories** (OpenStax, CK-12, OER Commons, Curriki, Siyavula, state OER
  hubs, etc.) — increased, attributed, verifiable reuse of content they created, which strengthens
  the open-content commons and the case for funding it.

**Who must NOT be the primary beneficiary.** Per Hee-Lee Oss guardrails, this project must not primarily
benefit a for-profit (e.g. a tutoring company, an edtech vendor, or a lesson marketplace). Outputs
are openly licensed precisely to prevent capture.

**The verified need.**

- The *general* need is well established and we treat it as real: teachers spend many hours per week
  sourcing and preparing materials; OER adoption is repeatedly bottlenecked not by content scarcity
  but by the absence of ready-to-teach, standards-aligned packaging. (Citations consolidated in
  `## References`; this plan does not overstate any single statistic.)
- The *specific* need — a named teacher, school, district, or repository that has agreed to **adopt
  and use** these particular plans — is **TO BE SECURED**. Until then, individual tasks carry
  `verifiedNeed: false` and `requestor: TO BE SECURED`. We will not declare a deed "delivered" on
  the strength of a plausible general need; a real beneficiary must accept and use the output.

**Partner / requestor.** **TO BE SECURED.** Candidate partner types: (a) an individual teacher or
small teacher cohort willing to pilot and give feedback; (b) a school/district curriculum lead; (c)
an OER repository willing to host contributed plans under an open license. Self-serve fallback if no
partner is secured: publish to an open repository (e.g. OER Commons, a public GitHub repo, Zenodo
with a DOI) so the work is at least discoverable and reusable — but this is **publication, not
adoption**, and does not by itself satisfy the "delivered" bar.

---

## Goals and non-goals

**Goals**

1. Produce **complete, teach-tomorrow lesson plans** — not lesson *ideas* or link lists — each
   wrapping vetted OER with full attribution and an open license.
2. **Standards alignment as a first-class, verifiable property** — every plan declares the standards
   it meets (by stable identifier), and that alignment is reviewed by a qualified educator, not
   asserted by the model.
3. **License & provenance rigor** — every source's license is verified to permit the reuse and
   derivation we perform; attribution and license-compatibility are machine-checked and human-checked
   before publication.
4. **Accessibility & equity by design** — every plan applies Universal Design for Learning (UDL):
   differentiation for varied readiness, language supports for multilingual learners, and
   accessibility (plain language, alt-text for any images, screen-reader-friendly structure).
5. **Real classroom adoption** — measure success by teachers actually teaching the plans and
   reporting they worked, not by plans authored or pages published.
6. **Interoperability** — emit plans in open, portable formats (Markdown source of truth, print-ready
   PDF, and LMS-importable packages) with open learning-resource metadata, so adoption is frictionless.

**Non-goals (this project will NOT…)**

- **Not build an LMS, an app, a student-facing platform, or any system that collects student data.**
  We produce content + metadata; we do not run software that touches learners.
- **Not host, mirror, fork, or relicense the underlying OER** beyond what each source license
  permits. We wrap and attribute; we do not re-publish source corpora.
- **Not invent or fabricate standards alignments.** If a plan cannot be honestly aligned to a cited
  standard, it ships unaligned (and says so) rather than claiming a false alignment.
- **Not generate net-new "facts," figures, or primary content presented as authoritative.** Source
  claims come from cited OER; original writing is limited to pedagogical scaffolding (objectives,
  procedure, prompts, rubrics).
- **Not produce graded, high-stakes assessments or anything that determines a student's record.**
  Formative checks only; clearly labelled as such.
- **Not give medical, legal, financial, or safety advice.** Where a lesson touches such a domain, it
  is factual, sourced, expert-reviewed, and framed "for education, not advice."
- **Not take partisan positions** on contested civic/political/religious/cultural questions. Civic
  and history content is balanced, sourced, and age-appropriate.
- **Not scrape, ingest, or process any student or teacher personal data.** Zero PII pipeline.
- **Not chase volume.** A small library of genuinely excellent, adopted plans beats a large library
  of unverified ones.

---

## Success metrics (outcomes)

Outcome-centric (beneficiary impact), not vanity counts. Baselines are recorded during M0–M1 because
the project is new; targets are set against those baselines.

| # | Outcome metric | Baseline | Target | How measured |
|---|---|---|---|---|
| 1 | **Lesson plans actually taught** by a real teacher (not just authored) | 0 | ≥ 5 taught by M1 close; ≥ 25 by M3 | Steward-recorded adoption evidence (teacher confirmation / classroom use) in the outcome ledger |
| 2 | **Teacher-reported usefulness** ("I could teach this with little/no rework") | n/a | ≥ 80% of piloted plans rated usable as-is or with minor edits | Short structured teacher feedback form (no student data) |
| 3 | **Standards-alignment accuracy** (alignment confirmed correct by a qualified educator) | n/a | ≥ 95% of declared alignments confirmed; 0 false alignments shipped | Pedagogy/standards reviewer sign-off per plan |
| 4 | **License/attribution correctness** (zero violations) | n/a | **0** license or attribution defects in published plans | License gate artifact + spot audit; any defect is a P0 recall |
| 5 | **Accessibility/UDL coverage** | n/a | 100% of plans include differentiation + language supports + accessible structure; ≥ 1 plan passes a full a11y audit per milestone | UDL checklist + a11y audit |
| 6 | **Verified external reuse / adoption** beyond the original pilot | 0 | ≥ 3 verifiable downstream reuse events by M3 | Repository acceptance, teacher reuse, fork/translation evidence |
| 7 | **Prep-time returned to teachers** (self-reported estimate of hours saved per adopted plan) | n/a | Recorded for every adopted plan; reported as an aggregate, honestly caveated | Optional teacher self-report |
| 8 | **Partner secured** | 0 | ≥ 1 confirmed adopting partner by M1; ≥ 1 repository channel by M2 | Signed/confirmed partner record; flips affected tasks to `verifiedNeed: true` |

Anti-metrics we explicitly refuse to optimize: raw count of plans authored, page views, downloads
without evidence of teaching, or social sharing. Publication ≠ delivery.

---

## Scope

**In scope**

- Authoring complete lesson plans wrapping **openly-licensed** OER (CC-BY, CC-BY-SA, CC0, public
  domain; CC-BY-NC / NC-SA only in a clearly separated, non-relicensed NC tier — see §Data).
- Standards alignment to published frameworks via **stable identifiers** (e.g. Common Core State
  Standards codes, NGSS performance expectations, and — where license permits — state/national
  frameworks), with machine-readable alignment metadata.
- A canonical lesson-plan **schema + template**, an OER **license gate**, an **accessibility/UDL**
  checklist, a **reading-level / age-appropriateness** check, and **validation tooling**.
- Export to open, portable formats: Markdown (source of truth), print-ready PDF/HTML, and
  LMS-importable packages (IMS Common Cartridge / Thin CC), with LRMI / schema.org
  `LearningResource` metadata and CASE-style standards alignment.
- Contributing plans back to a partner teacher/school or an open repository.
- A teacher-feedback loop (content feedback only; no student data) and an outcome/adoption ledger.

**Out of scope**

- Any student-facing software, LMS, account system, analytics, or data collection (see Non-goals).
- Hosting/mirroring/relicensing source OER corpora.
- High-stakes or graded assessments; certification; official curriculum endorsement.
- Generating original primary content presented as authoritative (textbook passages, datasets,
  scientific claims) — we wrap cited OER, we do not author the canon.
- Subjects requiring professional advice delivered *as advice* (medical/legal/financial/safety).
  Educational treatment only, expert-reviewed, "not advice" framed.
- Republishing full standards text where the standards' own license forbids it (we cite codes +
  short permitted descriptors + links instead).
- Translation/localization at scale in M0–M1 (deferred to backlog; needs language + pedagogy
  reviewers per target language).

---

## Solution approach & architecture

This is primarily a **content + metadata pipeline** with light supporting tooling. The unit of work
is one lesson plan.

### Pipeline (per lesson plan)

```
1. SELECT     → pick a topic + grade band + target standard(s) from the planning backlog
2. SOURCE     → identify candidate OER source(s) for the content
3. LICENSE    → license gate: verify each source permits reuse + the derivation we perform,
                capture license id + URL + snapshot, record attribution + compatibility (HARD GATE)
4. ALIGN      → map to standard identifier(s); record alignment + rationale (machine-readable)
5. AUTHOR     → draft the plan against the canonical template (objectives, procedure, formative
                checks, differentiation/UDL, materials, answer key, attributions)
6. CHECK      → automated checks: schema-valid, reading-level/age band, attribution completeness,
                metadata validity, accessibility structure, link/source resolvability
7. REVIEW     → pedagogy/standards reviewer sign-off (qualified educator); subject-expert review
                if sensitive-subject (escalates to medium risk) (HARD GATE)
8. EXPORT     → emit Markdown (canonical) + print PDF/HTML + LMS package + LRMI/CASE metadata
9. DELIVER    → contribute to partner teacher/school or open repository
10. OUTCOME   → record adoption + teacher feedback in the outcome ledger; learn / iterate
```

### Components

- **Canonical lesson-plan model** — a single structured schema all outputs project from. Fields
  (illustrative): `title`, `gradeBand`, `subject`, `durationMinutes`, `objectives[]`,
  `standards[] {framework, code, descriptor?, alignmentRationale, descriptorLicenseOk}`,
  `materials[]`, `priorKnowledge[]`, `procedure[] {phase, minutes, teacherDoes, studentsDo}`,
  `formativeChecks[]`, `differentiation {support[], extension[], languageSupports[], udlNotes}`,
  `accessibility {plainLanguage, altTextPresent, structureNotes}`, `answerKey?`,
  `sources[] {title, author, url, license {id,url,permitsDerivatives,shareAlike,nonCommercial,snapshotRef}, attributionText}`,
  `outputLicense`, `provenance {createdAt, reviewer, subjectExpert?}`, `sensitiveSubject {flag, reason, framing}`.
- **OER license gate** — a checklist + (later) a script that classifies each source license
  PASS/FLAG/EXCLUDE, records the permits-derivatives / share-alike / non-commercial booleans from a
  cited clause, and computes the *resulting* license obligation for the composed plan.
- **Standards-alignment module** — alignment to framework identifiers; emits CASE-style
  (1EdTech Competencies & Academic Standards Exchange) / LRMI `alignmentType: teaches` metadata.
- **Accessibility/UDL checklist** — enforced per plan; plus a deeper a11y audit per milestone.
- **Reading-level / age-appropriateness check** — readability metric for the grade band + a
  safeguarding/age-appropriateness checklist; sensitive-subject detector that forces escalation.
- **Validation tooling (code)** — schema validator, attribution-completeness checker, metadata
  validator (LRMI/CC schema.org + CASE), link/source resolvability checker, golden fixtures, CI.
- **Exporters (code)** — Markdown → print PDF/HTML; Markdown → IMS Common Cartridge / Thin CC;
  metadata emitter. Deterministic, fixture-tested.
- **Outcome ledger** — per-plan record of adoption, teacher feedback, and reuse events.

### Tech stack & key decisions

- **Repo language/tooling:** TypeScript, ESM, pnpm workspaces (per Hee-Lee Oss conventions). Code is MIT;
  content is CC-BY-4.0 (subject to upstream share-alike — see §Data).
- **Source of truth:** Markdown + YAML front-matter (the canonical model serialized), so plans are
  diffable, reviewable in PRs, and trivially open. Generated PDFs/CC packages are build artifacts.
- **Metadata:** schema.org/LRMI `LearningResource` + `alignmentObject` for standards; CASE for
  machine-readable framework alignment. Pinned spec versions recorded in a `specVersions` file.
- **Agent-neutral:** all authoring guidance lives as project content/prompts in the repo; no
  vendor/agent-specific logic. (Consistent with Hee-Lee Oss's agent-neutral-core rule — this project ships
  content + adapters/tooling, not coding-agent integration.)
- **Decision — wrap, don't relicense:** the composed plan's license is the most restrictive
  compatible license across its sources. Prefer CC-BY/CC0/PD sources so plans can be CC-BY-4.0;
  CC-BY-SA sources force the plan to ShareAlike; NC sources are quarantined to an NC tier and never
  presented as CC-BY.
- **Decision — alignment by identifier, not republication:** store standard *codes* + short
  descriptors only where that framework's license permits; otherwise code + link only.

---

## Data, licensing & compliance

**This is the central, non-negotiable discipline of the project.** Treated conservatively.

### Source OER licenses

Accepted as primary (outputs can be CC-BY-4.0): **CC0**, **public domain**, **CC-BY-4.0** (and 3.0),
and US-government works that are public domain. Accepted with consequences:

- **CC-BY-SA** — derivatives must be ShareAlike-compatible. A plan wrapping SA content is licensed
  **CC-BY-SA-4.0**, not CC-BY. Mixing SA with incompatible licenses in one plan is disallowed.
- **CC-BY-NC / CC-BY-NC-SA** — **non-commercial**. These are *not* fully "open" in the Hee-Lee Oss sense
  (they restrict commercial reuse and, for some, derivatives). Decision: keep them in a **clearly
  labelled, segregated NC tier**, never relicensed, never blended into a CC-BY plan, never the
  default. Each NC plan is conspicuously marked. (Conservative because NC creates downstream reuse
  friction and is easy to mishandle.)
- **No-derivatives (ND)** licenses, "all rights reserved," "for educational use only with no license
  text," ambiguous/unstated terms → **EXCLUDED**. No default-allow; missing evidence = exclude.

**Objective license criterion:** a source PASSES only if `permitsDerivatives: true` is established
from a **cited clause/URL**, with `shareAlike` and `nonCommercial` booleans likewise recorded. The
gate computes the composed plan's required license from the set of source obligations.

### Standards frameworks (their *own* licensing)

Standards text is itself copyrighted and licensed, and this is a common trap:

- **Common Core State Standards (CCSS):** © NGA Center & CCSSO; a public license permits use/reproduction
  with the required attribution/notice. We cite **codes** and reproduce descriptor text only within the
  license's permitted terms, with the required notice; otherwise code + link.
- **NGSS:** "Next Generation Science Standards" is a registered trademark; the standards are released
  under a Creative Commons license by the lead states — we follow its attribution terms and the
  trademark-use guidance (don't imply endorsement).
- **State / national frameworks:** licensing varies widely (some public-domain government works, some
  restrictive). Each framework's terms are verified before any descriptor text is reproduced; default
  is **code + link, no descriptor reproduction** until the license is confirmed.
- We never imply official endorsement or accreditation by a standards body.

### Provenance model

Per source: title, author/publisher, source URL, retrieval date, version, license id + URL, a
**license snapshot** (committed copy of the license text/page + SHA-256 + Wayback URL — a bare URL is
insufficient), the `permitsDerivatives`/`shareAlike`/`nonCommercial` booleans with the citing clause,
and the exact attribution string to display. Stored in the plan's front-matter and a provenance
record.

### Privacy / PII

- **Zero student or teacher PII.** No pipeline ingests, stores, or processes personal data.
- Teacher feedback is collected as **content feedback only**, voluntarily, with no student data and
  no identifying classroom data; aggregate/anonymous reporting only.
- Any example names, scenarios, or sample student work in a plan are **fictional and inclusive**;
  no real student work is ever used.
- Lesson content is screened for material that could expose or target individuals.

### Attribution requirements

Every plan carries: (1) a per-source attribution block (title, author, source, license, link, and
"changes made") satisfying CC-BY/CC-BY-SA attribution; (2) the composed plan's own license notice;
(3) the standards-framework notice where descriptor text is used. Attribution completeness is a
machine check **and** a reviewer check; missing attribution blocks publication.

### Safeguarding & content standards (children)

Because the audience includes minors: age-appropriateness checklist per grade band; non-discrimination
and inclusivity review; non-partisan treatment of contested topics; **no** collection of children's
data; sensitive subjects (health, safety, sexuality, religion, contested history/politics, anything
with a "harm" surface) **escalate to `medium` risk** and require subject-matter-expert review and
"education, not advice" framing.

---

## Quality, review & risk gates

**Risk tier: `low` by default; `medium` for any sensitive-subject plan** (health, safety, sexuality,
religion, contested civic/historical/political content, or anything touching the refusal guardrails).
There is no `high`-tier content planned; if a proposed plan would require credentialed
medical/legal/safety *advice*, it is out of scope (reframed as education-only or refused).

**Hard gates (non-skippable) before a plan is published/delivered:**

1. **License gate** — every source PASSED with a committed artifact (permits-derivatives = true with
   cited clause, share-alike/NC recorded, snapshot captured); composed-plan license computed and
   correct; all attribution blocks present. *Owner: License reviewer.*
2. **Pedagogy & standards review gate** — a **qualified educator** confirms: objectives are sound and
   age-appropriate; the standards alignment is correct (no false alignments); the procedure is
   teachable in the stated time; the answer key is correct; UDL/differentiation is present and
   meaningful. *Owner: Pedagogy/standards reviewer.*
3. **Subject-expert gate (sensitive subjects only)** — a relevant subject-matter expert reviews for
   accuracy, balance, and safe framing; confirms "education, not advice." *Owner: Subject expert.*
4. **Automated checks** — schema-valid; reading level within grade band; attribution complete;
   metadata (LRMI/CASE) valid; links/sources resolve; accessibility structure present. CI-enforced.

**Definition of Shipped (per plan):** acceptance criteria met + all applicable gates passed + CI
green + the plan **adopted by a real teacher/partner** (taught, or accepted by a repository for
reuse) with adoption evidence recorded in the outcome ledger — **or**, if no adoption channel yet
exists, published openly with the blocker explicitly surfaced and `verifiedNeed` left `false`.
Authored-but-unadopted plans are *not* "delivered."

---

## Roadmap & milestones

Phased; each milestone has a goal and **measurable exit criteria**. M0 is a thin, cold-start
foundation; later phases scale and prove adoption.

### M0 — Foundation & cold-start
**Goal:** stand up the canonical model, the two hard gates, the core checks, and prove the whole
pipeline on **one** excellent pilot plan; open partner outreach.
**Exit criteria:**
- Pedagogy/standards reviewer role **named and filled** (blocking role exists before any plan review).
- License reviewer role named/filled (may be same person in M0 if competent in both, but the two
  gate *artifacts* remain distinct).
- Canonical lesson-plan schema + authoring template published; schema validator green in CI.
- OER license gate checklist + composed-license rule published.
- Accessibility/UDL checklist + reading-level/age-appropriateness checklist published.
- **One pilot lesson plan** authored end-to-end, both gates passed (artifacts committed), exported to
  Markdown + PDF, and either **taught by a pilot teacher** or accepted to an open repository — or
  published with the blocker surfaced.
- ≥ 1 partner-outreach thread opened (teacher/school/repository).

### M1 — Gates hardened + first adoptions
**Goal:** harden the gates into tooling, author a small coherent set (e.g. one unit / 3–5 plans),
secure the first adopting partner.
**Exit criteria:**
- License-snapshot capture + attribution-completeness checker working in CI.
- Standards-alignment metadata (CASE/LRMI) emitted and validated for every plan.
- ≥ 3 plans authored, both gates passed, ≥ 1 **taught** by a real teacher with feedback recorded.
- ≥ 1 **confirmed adopting partner**; affected tasks flip to `verifiedNeed: true`.
- Reading-level/age check automated; ≥ 1 sensitive-subject plan correctly escalated to subject-expert
  review (or none authored — recorded either way).

### M2 — Export, interoperability & scale
**Goal:** make adoption frictionless (LMS import, metadata, repository submission) and scale to a
useful library.
**Exit criteria:**
- Exporters for print PDF/HTML and IMS Common Cartridge / Thin CC, fixture-tested in CI.
- LRMI/schema.org `LearningResource` metadata + CASE alignment emitted per plan and validated.
- ≥ 1 repository submission channel working (plans accepted onto an OER repository with acceptance
  evidence).
- ≥ 10 plans published cumulatively, ≥ 5 adopted (taught or repository-accepted) with evidence.
- Median author→review→deliver cycle time recorded and improving vs. the M0/M1 baseline.

### M3 — Classroom outcomes & sustainability
**Goal:** prove real classroom outcomes, establish maintenance, and seed localization.
**Exit criteria:**
- ≥ 25 plans taught/adopted cumulatively; ≥ 3 verifiable external reuse events.
- Teacher-feedback loop operating; ≥ 80% usefulness rating across piloted plans.
- Staleness/refresh process (dead links, updated standards, updated source OER) documented and owned.
- Localization/i18n backlog defined with the language+pedagogy reviewer requirement per language.
- Maintainer + steward + reviewer rotation confirmed for ongoing operation.

---

## Work breakdown

The itemized, schema-mapped backlog lives in **`TASKS.md`**: milestone task tables (`ID | Title |
Type | Size | Risk | Deliverable | Depends on | Reviewer`), acceptance criteria for the most
important tasks per milestone, each milestone's Definition of Done, a backlog of sized-but-unscheduled
tasks, and one complete schema-valid example Task JSON. Tasks map to the Hee-Lee Oss Task schema in
`packages/schema/src/schemas.ts`. All current tasks are `lane: donated`, `verifiedNeed: false`,
`requestor: TO BE SECURED` until a partner is confirmed.

---

## Governance, roles & stakeholders

- **Maintainer (Owner: TBD)** — owns the repo, the canonical model, the backlog, and merges; ensures
  conventions and gates are enforced.
- **License reviewer** — runs the license gate; owns the PASS/FLAG/EXCLUDE artifact and composed-license
  computation. Blocking, non-skippable.
- **Pedagogy/standards reviewer** — a **qualified educator** (certified teacher or curriculum
  specialist) who signs off pedagogy, age-appropriateness, and standards alignment per plan.
  Blocking, non-skippable. A small **reviewer rotation** is established as volume grows to avoid a
  single bottleneck and single point of view.
- **Subject-matter experts (on call)** — for sensitive-subject (`medium`) plans: e.g. a health
  educator, a historian, a science specialist. Sign-off required before publication of those plans.
- **Accessibility reviewer** — periodic a11y/UDL audits (≥ 1 per milestone).
- **Steward (last-mile owner)** — owns *adoption*: secures partners, gets plans into real classrooms
  or repositories, records adoption evidence and teacher feedback in the outcome ledger. This role
  is what turns "authored" into "delivered."
- **Partner / requestor** — **TO BE SECURED** (teacher, school/district curriculum lead, or OER
  repository).
- **Hee-Lee Oss board/community** — adjudicates edge cases (e.g. a contested-subject plan) against the COI
  and refusal checklists.

---

## Dependencies & integrations

- **OER sources** (external): OpenStax, CK-12, OER Commons, Curriki, Siyavula, Wikimedia/Wikibooks,
  PhET (interactive sims — check license), state OER hubs, public-domain texts. Each gated per-source.
- **Standards frameworks** (external): Common Core (CCSS), NGSS, state/national frameworks; their
  licensing verified before descriptor reproduction.
- **Metadata/interop specs**: schema.org/LRMI, 1EdTech CASE, IMS Common Cartridge / Thin CC; pinned
  versions recorded.
- **Archival**: Wayback Machine (license snapshots); optionally Zenodo (DOIs for published bundles).
- **Hee-Lee Oss pieces**: the Task schema (`packages/schema`), the CLI workspace/PR flow (donated lane),
  the outcome ledger / "delivered, not merged" definition, and the governance refusal/COI checklists.
- **Tooling**: a readability metric library; a Markdown→PDF/HTML toolchain; an LRMI/CASE validator;
  pnpm/TypeScript/CI.

---

## Risks & mitigations

| Risk | Likelihood | Impact | Mitigation | Owner |
|---|---|---|---|---|
| Wrapping content whose license forbids derivation / omits attribution | Medium | High | Hard license gate; no default-allow; cited-clause requirement; snapshot; attribution machine+human check; P0 recall on any defect | License reviewer |
| Share-alike / NC contamination (e.g. blending SA into a "CC-BY" plan, or relicensing NC) | Medium | High | Composed-license rule computed by the gate; SA plans labelled SA; NC quarantined to a labelled NC tier, never relicensed | License reviewer |
| False or sloppy standards alignment | Medium | High | Alignment reviewed by a qualified educator; "no honest alignment → ship unaligned"; 0-false-alignment metric | Pedagogy/standards reviewer |
| Factual error / wrong answer key | Medium | High | Reviewer verifies answer keys; source claims must be cited; automated link/source resolvability | Pedagogy/standards reviewer |
| Age-inappropriate or non-inclusive content | Low–Med | High | Age-appropriateness + inclusivity checklist; sensitive-subject escalation to subject expert | Pedagogy reviewer / subject expert |
| Sensitive subject framed as advice (health/legal/safety) | Low | High | Out-of-scope-as-advice rule; "education, not advice" framing; subject-expert gate; refuse if it requires credentialed advice | Subject expert / Maintainer |
| Partisan/biased treatment of contested topics | Low–Med | Med | Non-partisan standard; balanced sourcing; board adjudication of edge cases | Maintainer / board |
| Reproducing standards text beyond its license | Medium | Med | Code+link default; descriptor reproduction only within verified license terms + required notice | License reviewer |
| No partner secured → plans authored but never taught | High | High | `verifiedNeed: false` default; steward owns adoption; self-serve repository fallback; success measured by adoption not authoring | Steward |
| Reviewer bottleneck / single point of view | Medium | Med | Reviewer rotation; clear gate artifacts; size tasks to one session | Maintainer |
| Source link rot / standards revisions over time | High (long-term) | Med | License/source snapshots; staleness/refresh process (M3); refresh tasks | Maintainer |
| Over-reliance on AI accuracy ("looks right, isn't") | Medium | High | Human gates are mandatory and blocking; AI output is a draft, never publishable unreviewed | All reviewers |
| Primary benefit drifting to a for-profit (e.g. a vendor harvesting plans) | Low | Med | Open license is the structural defense; non-goal explicit; COI checklist | Maintainer / board |

---

## Security & privacy

- **Threat surface is small** (a content repo + light tooling), but real: (a) supply-chain in build
  tooling/exporters, (b) malicious or mislicensed "OER" sources, (c) accidental inclusion of PII or
  harmful content, (d) link injection in generated artifacts.
- **Secrets:** none should be required for core authoring. If any service (e.g. a repository API,
  Zenodo) needs a token, it lives in CI secrets / env — **never** committed, logged, or written into
  plans, receipts, or front-matter (per CLAUDE.md).
- **PII:** zero-PII pipeline by design; teacher feedback is anonymous/content-only; example student
  content is fictional. No children's data collected, ever.
- **Abuse/misuse prevention:** refusal guardrails apply — refuse and flag any task steering content
  toward harm, harassment, discrimination, disinformation, surveillance, or unqualified high-stakes
  advice. Sensitive subjects escalate to expert review. Sources verified to be genuinely
  openly-licensed (not laundered third-party copyrighted material).
- **Integrity:** license snapshots are hashed (SHA-256) + archived; exporters are deterministic and
  fixture-tested; generated artifacts are reproducible from the Markdown source of truth.
- **Tooling supply chain:** pinned dependencies, lockfile committed, CI runs build+test+lint; no
  network calls baked into published plans.

---

## Sustainability & maintenance

- **After delivery**, plans live in an open repo (and/or partner repository) under an open license,
  so they survive the project. The **maintainer** keeps the model, tooling, and CI healthy; the
  **steward** keeps the adoption + outcome ledger current.
- **Outcome tracking:** every adopted plan has a ledger entry (who taught/accepted it, when, feedback,
  any reuse events). Success metrics are reported from the ledger, honestly caveated.
- **Refresh:** an M3 staleness process detects dead source links, revised standards, and updated
  source OER, spawning `maintenance` tasks; plans that go stale are flagged, not silently left wrong.
- **Reviewer continuity:** a small rotation of qualified educators (and on-call subject experts)
  prevents single-point bottlenecks; onboarding docs lower the cost of adding reviewers.
- **Cost:** donated-lane authoring is the default (no escrow). A funded lane could later accelerate a
  prioritized backlog with a hard per-task budget cap, but is not required for the core mission.

---

## Open questions

1. **Which standards framework(s) to anchor first?** CCSS + NGSS (US-centric) maximize immediate
   reach but narrow global relevance; a framework-agnostic alignment model is more work. Decision
   needed before M1 scale-up.
2. **Partner-first vs. repository-first cold-start?** A pilot teacher gives the strongest "delivered"
   signal but is slow to secure; an OER repository is faster but adoption ≠ teaching. Steward to
   resolve in M0.
3. **NC tier — include at all?** Including CC-BY-NC content widens the source pool but complicates the
   "freely available / open" promise and downstream reuse. Board decision recommended.
4. **Grade band / subject focus for the pilot library?** (e.g. start with one subject + grade band to
   build a coherent unit, or spread across the highest-need gaps.)
5. **How much standards descriptor text may we reproduce** under each framework's license? Needs a
   per-framework legal read before M1.
6. **Localization sequencing** — which languages, and how to secure language+pedagogy reviewers per
   language (deferred to M3 backlog, but the gating policy is needed earlier).
7. **Reviewer credentialing bar** — what qualifies someone as the pedagogy/standards reviewer, and
   how is the rotation governed?

---

## References

- Hee-Lee Oss work rules and guardrails — `C:\code\hee-lee-oss\CLAUDE.md`.
- The Good Deed Definition (5 criteria + risk tiers) — `C:\code\hee-lee-oss\docs\good-deed-definition.md`.
- Hee-Lee Oss Task schema — `C:\code\hee-lee-oss\packages\schema\src\schemas.ts`.
- Hee-Lee Oss portfolio roadmap (this project listed in Track 3) — `C:\code\hee-lee-oss\planning\ROADMAP.md`.
- Sibling exemplar plan/tasks — `C:\code\hee-lee-oss\planning\projects\open-data-datasheets\{PLAN,TASKS}.md`.
- Creative Commons license suite (CC0, CC-BY, CC-BY-SA, CC-BY-NC) — license terms and compatibility.
- Common Core State Standards (CCSS) — © NGA Center & CCSSO, public license + attribution terms.
- Next Generation Science Standards (NGSS) — CC-licensed by lead states; "NGSS" trademark guidance.
- UDL (Universal Design for Learning) guidelines.
- schema.org / LRMI `LearningResource` + `alignmentObject`; 1EdTech CASE; IMS Common Cartridge / Thin CC.
- OER repositories/sources: OpenStax, CK-12, OER Commons, Curriki, Siyavula, PhET, Wikimedia/Wikibooks.
- (Need-evidence citations on teacher prep time and OER adoption barriers to be consolidated and
  source-verified during M0; this plan does not rely on any single unverified statistic.)

---

## Appendix A — Improvements applied

Twenty-five specific improvements identified against the first draft and **applied** in the text
above. Each is a concrete change, not a vague aspiration.

1. **Adoption, not authoring, defined as success.** Reframed the headline metric and Definition of
   Shipped so a plan counts only when a real teacher teaches it or a repository accepts it — added
   metric #1 and the "authored ≠ delivered" rule throughout.
2. **Two distinct hard gates separated.** Split "review" into an explicit **license gate** and a
   **pedagogy/standards gate**, each with its own owner and committed artifact, so neither can hide
   behind the other.
3. **Composed-license rule made explicit.** Added the rule that a plan's license is the most
   restrictive compatible license across sources, with worked consequences for SA and NC — closing
   the most likely real licensing defect.
4. **NC content quarantined, not banned-or-blended.** Defined a labelled NC tier with a clear "never
   relicensed, never default, never blended into CC-BY" policy, plus an open question for the board.
5. **Standards frameworks' own licensing addressed.** Added the CCSS/NGSS/state-framework licensing
   nuance (a trap most plans miss) with a "code + link by default, reproduce descriptors only within
   verified terms" rule.
6. **Sensitive-subject escalation built in.** Defined the `medium`-risk escalation path (health,
   safety, sexuality, religion, contested civic/history) with a mandatory subject-expert gate and
   "education, not advice" framing — and ruled credentialed-advice content out of scope.
7. **Zero-PII stance made concrete.** Specified no student/teacher data pipeline, anonymous
   content-only teacher feedback, and fictional/inclusive example student content.
8. **Safeguarding for minors added.** Added an age-appropriateness + inclusivity + non-partisan
   checklist because the audience includes children.
9. **Provenance hardened to snapshot+hash+Wayback.** Adopted the sibling project's stronger evidence
   standard (committed copy + SHA-256 + Wayback URL) instead of a bare license URL.
10. **Attribution made machine-checkable.** Added an attribution-completeness checker as both an
    automated check and a blocking reviewer check.
11. **Interoperability concretized.** Named real open specs (LRMI/schema.org, CASE, IMS Common
    Cartridge/Thin CC) with pinned-version recording, rather than vague "export formats."
12. **Markdown chosen as source of truth.** Locked a diffable, PR-reviewable, trivially-open canonical
    format with PDFs/CC packages as build artifacts.
13. **Reviewer rotation + bottleneck risk.** Added a rotation to avoid a single reviewer becoming a
    throughput and viewpoint bottleneck.
14. **Steward role added for last-mile adoption.** Distinguished the steward (owns getting plans into
    classrooms + the outcome ledger) from the maintainer.
15. **Anti-metrics named.** Explicitly refused to optimize plan count, downloads, and views — the
    vanity metrics this kind of project most easily drifts toward.
16. **Baselines acknowledged as new-project.** Marked baselines as "recorded in M0–M1" instead of
    inventing numbers, and set targets against them.
17. **"No false alignment" made a measurable target.** Metric #3 sets 0 false alignments shipped and
    a ≥95% confirmed-alignment bar.
18. **License gate uses an objective, no-default-allow criterion.** PASS only on a cited clause
    establishing `permitsDerivatives: true`; missing evidence = exclude.
19. **Refresh/staleness process scheduled (M3).** Added link-rot, standards-revision, and source-OER
    update handling so plans don't silently rot.
20. **Self-serve fallback defined but demoted.** Repository publication is allowed as a fallback but
    explicitly labelled "publication, not adoption," preserving honesty in the success bar.
21. **For-profit-capture defense stated structurally.** Open licensing named as the mechanism that
    prevents primary for-profit benefit, satisfying good-deed criterion #3.
22. **Scope crisply bounded against platform creep.** Non-goals now explicitly exclude building an
    LMS/app/student-data system, keeping the project a content+metadata effort.
23. **Pipeline made a numbered, auditable flow.** Turned the architecture into a 10-step pipeline with
    gates at steps 3 and 7, so the process is checkable, not narrative.
24. **Funded lane addressed and bounded.** Noted a possible future funded lane with a hard per-task
    budget cap, consistent with Hee-Lee Oss's escrow rules, without making it required.
25. **Open questions sharpened into decisions-needed.** Each open question now names who decides and by
    when (framework anchor before M1, NC tier to the board, partner-vs-repository to the steward in
    M0), instead of listing unowned uncertainties.

---

## Review sign-off

**Reviewed against:** the PLAN_SPEC 17-section structure, `CLAUDE.md` work rules, the Good Deed
Definition + risk tiers, the Task schema, and the open-data-datasheets exemplar for house style.

**Completeness check.** All 17 required H2 sections are present and in order (Executive summary;
Problem & beneficiaries; Goals and non-goals; Success metrics; Scope; Solution approach &
architecture; Data, licensing & compliance; Quality, review & risk gates; Roadmap & milestones; Work
breakdown; Governance, roles & stakeholders; Dependencies & integrations; Risks & mitigations;
Security & privacy; Sustainability & maintenance; Open questions; References), followed by Appendix A
and this sign-off.

**Correctness check & fixes applied during review.**
- Confirmed every Good Deed criterion is satisfied: tangible public benefit (teacher prep + student
  learning); freely available (open licenses); not primarily for-profit (open license is the
  structural guard); no harm/discrimination/misinformation (safeguarding, non-partisan, sourced); AI-
  executable with human/expert review (the two gates + sensitive-subject escalation).
- Confirmed risk tiering is honest: `low` default, `medium` for sensitive subjects, no `high` content
  (credentialed-advice content ruled out of scope rather than mis-tiered).
- Confirmed the "delivered, not merged" bar is encoded in the Definition of Shipped and in metric #1,
  and that `verifiedNeed: false` / `requestor: TO BE SECURED` honesty is stated wherever a partner is
  absent.
- Confirmed no secrets/PII handling violates CLAUDE.md; zero-PII pipeline and secrets-in-CI-only.
- Fixed a latent inconsistency: clarified that in M0 one person may hold both reviewer roles but the
  **two gate artifacts remain distinct** (so the separation-of-concerns isn't lost at small scale).
- Verified consistency between this PLAN's milestones (M0–M3) and the milestone tables in `TASKS.md`,
  and that all tasks map to required schema fields.

**Outstanding (tracked as Open questions, not blockers):** standards-framework anchor choice; NC-tier
board decision; partner-vs-repository cold-start; per-framework descriptor-reproduction legal read.

**Sign-off:** Plan is internally consistent, guardrail-compliant, and ready for maintainer/board
review. Status remains **Draft v0.1.0** pending a named maintainer, reviewers, and partner.
