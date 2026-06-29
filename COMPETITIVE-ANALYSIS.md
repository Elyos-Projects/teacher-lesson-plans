# Competitive & Improvement Analysis — `teacher-lesson-plans`

> Scope: rigorous review of `PLAN.md` (v0.1.0) + `TASKS.md`, grounded against the real lesson-plan
> market via web research. Project = open, standards-aligned, ready-to-teach lesson plans wrapping
> vetted OER, with materials, for under-resourced classrooms. Guardrails: open (CC) license; standards
> alignment; educator review; culturally responsive; accessibility (UDL).

---

## 1. Correctness & completeness review of PLAN.md

The plan is unusually mature for a v0.1.0 draft. It already internalizes the hardest truths of this
domain. Findings below are ordered roughly by importance.

**Strong / correct foundations (keep):**

- **The core thesis is right and well-evidenced.** "Free content exists but is not teachable as-is" is
  the real bottleneck. Research backs this precisely: ~half of teachers spend **4+ hours/week**
  sourcing/building materials and 99% of elementary ELA teachers use self-assembled materials
  ([RAND via EdWeek](https://blogs.edweek.org/teachers/teaching_now/2020/04/rand_study_online_resources_not_teachers_top_choice_before_coronavirus_pandemic.html)).
  The "assembly labour gap" framing is the correct wedge.
- **"Delivered, not merged" is encoded honestly.** Metric #1 (plans *taught*, not authored),
  `verifiedNeed: false`, `requestor: TO BE SECURED`, and the demotion of repository publication to
  "publication, not adoption" are exactly right and resist the field's dominant vanity metric (download
  counts). Share My Lesson reports 420k resources and 16M downloads ([Share My Lesson / AFT](https://sharemylesson.com/about-us))
  — downloads that say nothing about whether a child got a good lesson.
- **License discipline is the standout.** The composed-license rule (plan license = most restrictive
  compatible across sources), SA propagation, NC quarantine, ND/ambiguous → EXCLUDE, no-default-allow,
  and snapshot+SHA-256+Wayback provenance are correct and rarely done even by funded OER projects.
- **Standards-frameworks-have-their-own-license trap is caught.** Treating CCSS (© NGA/CCSSO) and the
  "NGSS" trademark as separately licensed, defaulting to *code + link* rather than reproducing
  descriptor text, is a subtle, correct call most lesson sites get wrong.
- **AI-accuracy risk is named and gated.** "AI output is a draft, never publishable unreviewed" plus
  two blocking human gates is the right structural answer to the AI-slop wave (see §1 risk below).

**Gaps / corrections (should fix before M1):**

1. **Quality is asserted via gates but not *measured* against a credible external rubric.** The plan
   reviews alignment and "teachability," but the field already has an authoritative quality bar:
   **EdReports** rates curricula on *alignment* AND *usability* (all-green), and its 2.0 tools now add
   explicit **multilingual-learner** and science-of-reading criteria
   ([EdReports](https://edreports.org/resources/article/edreports-launches-next-generation-of-curriculum-reviews)).
   Borrowing/aligning the review rubric to EdReports-style indicators would make "quality" objective
   and externally legible, not just "a reviewer signed off." **Recommend: add an explicit quality
   rubric artifact** (not only a pass/fail gate).
2. **"Culturally responsive" is a guardrail but under-operationalized in the gates.** The plan covers
   non-partisan/inclusive/age-appropriate, but cultural responsiveness (CRP/CSP) is a *distinct*
   competency with its own pitfalls — TpT's documented failures were precisely lessons *marketed* as
   "multicultural/social justice/inclusive" that delivered stereotypes, tokenism, and slavery
   simulations ([EdSurge](https://www.edsurge.com/news/2021-02-10-what-teachers-pay-teachers-is-learning-from-bad-lessons-and-upset-teachers)).
   **Recommend: a dedicated cultural-responsiveness checklist + a reviewer with that lens**, separate
   from generic "inclusivity." This is a named guardrail and currently the thinnest gate.
3. **Standards alignment is reviewed but not independently *verified* against a machine-readable
   source of truth.** Reviewer sign-off catches false alignments, but there is no second, automated
   cross-check that the cited code exists and that the descriptor matches. The sibling project
   `curriculum-standards-map` (see §7) is the natural backstop; until it exists, alignment correctness
   rests on one human. A study analyzing 500k+ TpT lesson descriptions found pervasive *lack of*
   genuine Common Core alignment despite alignment claims
   ([ScienceDirect](https://www.sciencedirect.com/science/article/pii/S266655732200009X)) — the exact
   failure mode to guard against. **Recommend: a CASE/registry lookup that validates code existence +
   surfaces the canonical descriptor for the reviewer.**
4. **OER duplication risk is unaddressed.** The plan wraps OER, but several "competitors" (Illustrative
   Mathematics, EngageNY/Eureka, Open Up, CommonLit 360) already ship *complete, openly-licensed,
   EdReports-green, standards-aligned lesson sequences*. **The project must not re-wrap what is already
   teach-ready.** There is no explicit "is this gap already filled by existing OER?" check in SELECT.
   **Recommend: add a "prior-art / non-duplication" step** to the pipeline (step 1.5) that documents
   why an existing OER unit isn't already classroom-ready for the target context.
5. **Classroom-readiness is claimed but not *piloted into the definition of the artifact*.** "Teachable
   in the stated time" is reviewer-judged, not classroom-tested. ReadWriteThink's credibility rests on
   "classroom-tested" lessons ([ReadWriteThink/NCTE](https://www.readwritethink.org/classroom-resources/lesson-plans)).
   The M0 pilot does require "taught by a pilot teacher," which is good — but **readiness signals
   (printable materials, no-prep substitute-friendliness, low-tech/low-resource variant) should be
   first-class schema fields**, given the under-resourced-classroom target. The schema has UDL but no
   explicit "works with no projector / one shared copy / no internet" low-resource flag.
6. **Materials licensing for *generated* artifacts is implicit.** The plan licenses wrapped OER and the
   composed plan, but "materials" (worksheets, slides, manipulatives) the model drafts net-new need an
   explicit license + an explicit "this is original scaffolding, not wrapped source" provenance tag to
   avoid the inverse problem (claiming CC-BY on something that embedded an SA source figure).
7. **Reviewer credentialing + capacity is the realistic bottleneck, flagged but unresolved.** Open
   question #7 (what qualifies a pedagogy reviewer) gates *everything*; with one blocking human gate,
   throughput is reviewer-bound. This is correctly risk-listed but needs a concrete answer before M1
   scale-up, not M3.
8. **Minor:** Success metric #2 (≥80% "usable as-is or with minor edits") and metric #3 (≥95% alignment
   confirmed) lack a defined sample/denominator and who adjudicates disputes; "n/a baseline" is fine but
   the measurement instrument should be specified in M0, not deferred.

Overall: **completeness is high; the two most material correctness gaps are (a) no objective external
quality rubric and (b) under-operationalized cultural-responsiveness + alignment *verification*.**

---

## 2. Competitive landscape (researched, cited)

| Competitor | What it is | Strengths | Weaknesses (our opening) |
|---|---|---|---|
| **Teachers Pay Teachers (TpT)** | Dominant paid marketplace; **>80% of US teachers** use it; **4M+ resources** ([company via Hechinger](https://hechingerreport.org/most-english-lessons-on-teachers-pay-teachers-and-other-sites-are-mediocre-or-not-worth-using-study-finds/)) | Massive selection, teacher-authored, searchable, ratings, ubiquitous | **Paid** (toll on the poorest classrooms); **quality "mediocre / not worth using"** in studies; documented racist/insensitive lessons & weak Common Core alignment; now **clogged with low-quality AI-generated content** ([EdSurge](https://www.edsurge.com/news/2021-02-10-what-teachers-pay-teachers-is-learning-from-bad-lessons-and-upset-teachers), [Hechinger](https://hechingerreport.org/most-english-lessons-on-teachers-pay-teachers-and-other-sites-are-mediocre-or-not-worth-using-study-finds/)) |
| **Share My Lesson (AFT)** | Free union-run community library; **2.2M members, 420k resources, 16M downloads** ([SML](https://sharemylesson.com/about-us)) | Free, large, credible sponsor (AFT), PreK–higher-ed | Uneven/un-curated (community upload), variable standards alignment, licensing not uniformly open/CC, download≠taught |
| **OER Commons (ISKME)** | OER discovery hub since 2007; **~50k resources** ([OER Commons](https://en.wikipedia.org/wiki/OER_Commons)) | Genuinely open, metadata/alignment tooling (OpenAuthor), curation | Discovery layer, not "teach-tomorrow" packaging; heterogeneous quality; *finding* ≠ *ready* — the exact gap we target |
| **BetterLesson** | Teacher-created lessons + professional coaching | Implementation advice, coaching model | Now commercial/PD-oriented; not a focused open library |
| **ReadWriteThink (ILA/NCTE)** | Free literacy lessons, **educator-written & classroom-tested**, standards-based ([RWT](https://www.readwritethink.org/classroom-resources/lesson-plans)) | High trust, reviewed, free, ready-to-use | Narrow (literacy/ELA), aging, US-centric, no machine-readable alignment/UDL metadata |
| **Khan Academy / Khanmigo** | Free instruction + **AI lesson-plan generation** ([Khan blog](https://blog.khanacademy.org/generate-sample-lesson-plan-quickly-with-khan-academy-khanmigo-kt/)) | Free, trusted brand, scalable AI drafting | AI-generated = *unreviewed* (the slop risk); content-centric, not standards-aligned reviewed plans; not openly licensed plan corpus |
| **EngageNY / Eureka Math** | Free OER full curriculum (NY), CCLS-aligned ([Great Minds](https://greatminds.org/math/eurekamath)) | Complete, free, widely adopted, OER | Already teach-ready (don't duplicate); math/ELA only; aging EngageNY; Eureka commercial upsell |
| **Illustrative Mathematics + Open Up Resources** | Free, CC-licensed, **EdReports-green** math/ELA curricula; **10M+ students**, $0 vs $80–120/student commercial ([EdSurge](https://www.edsurge.com/news/2017-08-24-open-up-resources-announces-first-full-math-curriculum-and-its-plans-for-profitability)) | Gold standard: open, complete, expert-authored, adopted at scale | Whole-course adoption (heavy), few subjects/grades, US standards — **leaves long-tail topics/subjects/contexts uncovered** |
| **Common Curriculum** | Lesson planning/planbook tool | Planning workflow, standards tagging | A *tool*, not an open content library; subscription |
| **UNESCO (OER Recommendation 2019)** | Global normative instrument: equity, inclusive *quality* OER, international cooperation ([UNESCO](https://www.unesco.org/en/legal-affairs/recommendation-open-educational-resources-oer)) | Global legitimacy; policy tailwind for exactly this work | Policy/advocacy, not a producer of plans — a *framework to align with*, not a competitor |

**Synthesis:** Two poles exist. (1) **Big & uneven & paid** (TpT, Share My Lesson) — selection without
reliable quality, the poorest pay or get slop. (2) **High-quality but heavy & narrow** (IM, Open Up,
EngageNY, CommonLit, ReadWriteThink) — excellent where they exist, but whole-curriculum and limited to
a few subjects/grades/standards. **No one occupies "open + reviewed-quality + standards-aligned +
single ready-to-teach lessons + explicitly low-resource & culturally responsive."** That is the seam.

---

## 3. Gaps we can fill

1. **The "trusted single lesson" niche.** Whole-course OER (IM/Open Up) is great but heavy; teachers
   often need *one* excellent lesson for *tomorrow's* gap. TpT fills this but paid + uneven. We can be
   the **free, reviewed, single-lesson** layer.
2. **Quality assurance the free libraries lack.** Share My Lesson and OER Commons are large but
   un-curated; we ship a **visible, EdReports-style quality + alignment + UDL + cultural-responsiveness
   gate** on every plan.
3. **Explicit low-resource readiness.** None of the majors foreground "works with one shared copy, no
   projector, no internet, no budget." This is our beneficiary's defining constraint and an unfilled
   metadata/design dimension.
4. **Machine-readable alignment + portability on *single* lessons.** CASE/LRMI alignment + Common
   Cartridge export on individual plans (most free single lessons lack structured alignment metadata).
5. **An anti-slop guarantee.** As TpT/Khanmigo flood the market with unreviewed AI content, "every plan
   here passed two human gates + a license gate" is itself a fillable trust gap.
6. **Genuinely open license clarity.** Share My Lesson's licensing is inconsistent; we guarantee CC
   with computed, audited composed licenses — reuse/translate/redistribute without legal guesswork.
7. **Long-tail subjects/grades/standards** the big OER curricula skip (electives, multi-standard,
   non-US frameworks later).

---

## 4. Differentiators to win (vs TpT and Share My Lesson)

1. **Free *and* quality-gated.** TpT is paid-and-uneven; SML is free-but-uneven. We are the only one
   that is **free + every plan independently reviewed** for alignment, accuracy, UDL, and cultural
   responsiveness. This is the single strongest differentiator.
2. **"Delivered, not merged."** We count a plan only when a real teacher teaches it — vs TpT downloads
   and SML's 16M-download vanity metric. Outcome integrity is a brand.
3. **Verifiable, computed open licensing.** Snapshot+hash+Wayback provenance and a composed-license
   rule — reuse without legal risk, vs SML's mixed terms and TpT's all-rights-reserved paywall.
4. **Standards alignment you can *trust and verify*** (machine-readable CASE/LRMI + reviewer +
   eventual registry cross-check) — vs TpT's documented false/weak alignment claims.
5. **Built for under-resourced & culturally responsive by design**, not as an afterthought — directly
   answering TpT's documented inclusivity failures.
6. **Anti-slop positioning** as AI-generated junk floods both incumbents.

---

## 5. Claude API leverage (and the hard "Claude must NOT decide" line)

**Where Claude adds the most value (draft-only, human-gated):**

1. **Assemble teach-ready plans from vetted OER** — turn an openly-licensed passage/sim/problem set
   into objectives → procedure → formative checks → answer key → materials, against the canonical
   template. (Highest-leverage: this *is* the "assembly labour" gap.)
2. **Differentiation + UDL + multilingual + low-resource variants** — generate support/extension tiers,
   language scaffolds, plain-language rewrites, alt-text, and a "no-tech/one-copy" variant per plan.
3. **Standards-alignment *tagging* (candidate, not authority)** — propose framework codes + a rationale
   and a draft CASE/LRMI `alignmentObject` for the educator to confirm; also draft license-clause
   extraction (permitsDerivatives/shareAlike/nonCommercial booleans + citing clause) for the license
   reviewer to verify.

Other strong uses: reading-level/age-band screening, attribution-block drafting, sensitive-subject
detection/flagging, Common Cartridge/PDF export scaffolding, and translation drafts (with a
language+pedagogy reviewer per language).

**Where Claude must NOT be the decider (hard gates — plan already encodes these; keep them inviolable):**

- **Pedagogy & factual accuracy** → a qualified educator confirms objectives, procedure, and **answer
  keys**; AI output is a draft, never published unreviewed.
- **Standards alignment correctness** → educator-verified (ideally + registry cross-check); no
  AI-asserted alignment ships; no-honest-alignment → ship unaligned.
- **Cultural responsiveness / age-appropriateness / non-partisanship** → human reviewer with the CRP
  lens; sensitive subjects escalate to a subject-matter expert.
- **License & attribution legitimacy** → license reviewer verifies every cited clause and the computed
  composed license; AI extraction is advisory only.
- **"Delivered"** → only a real teacher/partner adopting the plan; never model judgment.

This division is the project's integrity story and the antidote to the Khanmigo/TpT "unreviewed AI" failure mode.

---

## 6. Ten concrete optimizations

1. **Adopt an explicit EdReports-style quality rubric artifact** (alignment + usability + multilingual)
   alongside the pass/fail gate, so "quality" is objective and externally legible.
2. **Add a pipeline step 1.5 "non-duplication / prior-art check"** documenting why existing OER (IM,
   Open Up, EngageNY, CommonLit, ReadWriteThink) isn't already classroom-ready for the target context.
3. **Make low-resource readiness first-class schema fields** (`requiresProjector`, `requiresInternet`,
   `printOnly`, `oneSharedCopyOk`, `subFriendly`) — directly serving the under-resourced beneficiary.
4. **Add a dedicated cultural-responsiveness checklist + reviewer lens** separate from generic
   inclusivity, with concrete anti-patterns (simulations of oppression, tokenism) drawn from documented
   TpT failures.
5. **Wire automated standards cross-validation** (code exists in CASE/registry; descriptor matches)
   feeding the reviewer — interlock with `curriculum-standards-map`.
6. **Specify the measurement instruments now** for metrics #2/#3 (sample, denominator, dispute
   adjudicator), not at M3.
7. **Tag net-new generated materials with explicit origin + license** ("original scaffolding, CC-BY"
   vs "wrapped source, inherits X") to prevent inverse license contamination.
8. **Publish an "anti-slop" provenance badge** per plan (gates passed, reviewer, date, sources) as a
   public trust signal versus AI-flooded marketplaces.
9. **Resolve reviewer credentialing (open Q#7) before M1**, and pre-build a reviewer-onboarding kit +
   rotation, since throughput is reviewer-bound.
10. **Pilot into a high-need, OER-thin niche** (e.g., a science or civics topic the big curricula skip)
    rather than competing where IM/Open Up are already green — maximizes marginal value and avoids
    duplication.

---

## 7. Parallel & perpendicular spin-offs

- **`oer-everything` (parallel):** shared OER-source registry + per-source license-gate results; this
  project is the highest-value *consumer*. Avoid duplicate license vetting across projects.
- **`curriculum-standards-map` (perpendicular, high-synergy):** the machine-readable standards graph
  that powers alignment *verification* here (the §1 gap #3 backstop) and CASE/LRMI emission.
- **`quiz-bank-open` (parallel):** openly-licensed formative-check / item bank that plugs directly into
  the `formativeChecks[]` field — reuse instead of re-authoring assessment items.
- **`oer-science-labs` (parallel):** lab/activity OER that this engine wraps into ready lessons;
  natural source feed for the OER-thin science niche (§6.10).
- **Reusable "lesson-assembly engine" (the platform play):** the canonical schema + license gate +
  UDL/CRP checklists + exporters + alignment emitter, factored into a generic engine. Any subject/region
  team feeds vetted OER + a standards framework and gets gated, portable, ready-to-teach plans. This is
  the durable asset; lesson plans are its first output.
- **MCP server (perpendicular):** expose the engine as an MCP server — tools like `align_to_standard`,
  `check_license`, `assemble_lesson`, `udl_review`, `export_common_cartridge`, `find_oer_source` — so
  any agent (or partner LMS) can request a gated lesson-assembly step. Turns the pipeline into shared
  infrastructure and a clean Claude-API integration point, while keeping humans in the gate loop.

---

## 8. Open questions

1. **External quality rubric:** adopt/adapt EdReports indicators, or define our own? (Borrowing buys
   legitimacy; defining buys fit for single-lesson + low-resource context.)
2. **Standards anchor (PLAN Q#1):** CCSS+NGSS first (US reach) vs framework-agnostic (global, more
   work)? Gates `curriculum-standards-map` scope.
3. **Non-duplication boundary:** how different/complementary must a plan be from existing green OER to
   justify authoring? Who adjudicates?
4. **Cultural-responsiveness reviewer:** is this a distinct credentialed role or part of pedagogy
   review? Where do CRP reviewers come from?
5. **Reviewer credentialing & capacity (PLAN Q#7):** the real throughput limiter — resolve before M1.
6. **Partner-first vs repository-first cold-start (PLAN Q#2):** which gives the strongest "delivered"
   signal fastest, given OER Commons/Zenodo are publication-not-adoption?
7. **NC tier (PLAN Q#3):** include CC-BY-NC at all, given it muddies the "freely reusable" promise?
8. **Low-resource validation:** how do we *verify* a plan truly works with no projector/internet/budget
   — checklist only, or a real low-resource classroom pilot?
9. **AI-content disclosure:** do we disclose that drafts were AI-assisted (transparency) even though
   human-gated, to differentiate from unlabeled AI slop?

---

### Sources

- TpT scale & quality: [Hechinger Report](https://hechingerreport.org/most-english-lessons-on-teachers-pay-teachers-and-other-sites-are-mediocre-or-not-worth-using-study-finds/), [EdSurge](https://www.edsurge.com/news/2021-02-10-what-teachers-pay-teachers-is-learning-from-bad-lessons-and-upset-teachers), [PBS NewsHour](https://www.pbs.org/newshour/show/why-teachers-selling-lesson-plans-have-sparked-debate), [MiddleWeb](https://www.middleweb.com/41448/why-ive-stopped-using-teachers-pay-teachers/), [ScienceDirect — 500k TpT descriptions / CC alignment](https://www.sciencedirect.com/science/article/pii/S266655732200009X)
- Share My Lesson: [About / AFT](https://sharemylesson.com/about-us), [AFT](https://www.aft.org/education/share-my-lesson)
- OER Commons / ISKME: [OER Commons (Wikipedia)](https://en.wikipedia.org/wiki/OER_Commons), [ISKME](https://www.iskme.org/oer-commons-education-ecosystem-using-knowledge-sharing/)
- IM / Open Up / EngageNY / Eureka: [EdSurge](https://www.edsurge.com/news/2017-08-24-open-up-resources-announces-first-full-math-curriculum-and-its-plans-for-profitability), [EdWeek](https://www.edweek.org/teaching-learning/can-an-open-math-curriculum-compete-with-commercial-publishers/2017/08), [Illustrative Mathematics](https://illustrativemathematics.org/open-up-resources-and-illustrative-mathematics-share-a-common-vision-for-an-open-ecosystem-for-k-12-education/), [Great Minds / Eureka](https://greatminds.org/math/eurekamath)
- ReadWriteThink / NCTE: [ReadWriteThink](https://www.readwritethink.org/classroom-resources/lesson-plans)
- Khan Academy / Khanmigo: [Khan blog](https://blog.khanacademy.org/generate-sample-lesson-plan-quickly-with-khan-academy-khanmigo-kt/)
- UNESCO OER Recommendation 2019: [UNESCO Legal Affairs](https://www.unesco.org/en/legal-affairs/recommendation-open-educational-resources-oer), [UNESCO OER](https://www.unesco.org/en/open-educational-resources)
- Teacher prep-time / where teachers find materials: [RAND via EdWeek](https://blogs.edweek.org/teachers/teaching_now/2020/04/rand_study_online_resources_not_teachers_top_choice_before_coronavirus_pandemic.html), [US News](https://www.usnews.com/opinion/articles/2016-05-06/why-teachers-rely-on-google-and-pinterest-for-course-materials)
- Quality rubric benchmark: [EdReports 2.0](https://edreports.org/resources/article/edreports-launches-next-generation-of-curriculum-reviews), [EdReports FAQs](https://edreports.org/resources/article/5-key-faqs-about-edreports-curriculum-reviews)
