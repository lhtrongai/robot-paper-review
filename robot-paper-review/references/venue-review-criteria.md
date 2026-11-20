# Venue review criteria (official texts)

What robotics venues officially tell reviewers to judge, mapped onto the complaint groups (a, b, c, d, e, f, g, o) and praise groups (p1-p13) of complaint-catalog.md. This file holds official rules, not observed reviews. Observed frequencies, reject-reason shares and rebuttal shares are in catalog-views.md.

How to use it in a review:
1. Pick the venue section and read its stages, scale and desk-reject rules first: they decide whether a complaint can still be fixed (rebuttal, revision) or decides the outcome at once.
2. Use the weight hints as venue weights next to catalog-views.md: a kind that is frequent in catalog-views.md AND high here goes to the top of the ranked weaknesses; a kind that is frequent there but low or "not stated" here stays, with a note that the venue does not ask for it.
3. Walk section 4 (venue-specific checks) as extra checklist items; the generic catalog does not cover them.
4. Rules change every year. Before a real review, re-fetch the pages below for the target edition; anything marked UNVERIFIED must be re-checked.

Weights are inferred from the official wording only (high = named as a criterion, a desk-reject or first-round reason, or stressed; medium = mentioned or implied; low = explicitly de-emphasized; not stated = absent from the texts read).

## 1. Sources

All fetched 2026-11-20. "Official" = venue or IEEE RAS site. Pages that needed sign-in: OpenReview was read signed in for CoRL (S28, S29); PaperPlaza and IEEE review systems were not opened.

| # | Venue, edition | Page | URL |
|---|---|---|---|
| S1 | RSS 2027 | Call for Papers | https://roboticsconference.org/information/cfp/ |
| S2 | RSS 2027 | Reviewer Guidelines (review form) | https://roboticsconference.org/information/reviewer-guidelines/ |
| S3 | RSS 2027 | Author FAQ | https://roboticsconference.org/information/author-faq/ |
| S4 | RSS 2026 | Call for Papers | https://roboticsconference.org/2026/information/cfp/ |
| S5 | RSS 2025 | Review Process (served at /reviewps and /2025/reviewps/) | https://roboticsconference.org/2025/reviewps/ |
| S6 | RSS 2025 | Author Information | https://roboticsconference.org/information/authorinfo |
| S7 | CoRL 2026 | Instruction for Reviewers | https://www.corl.org/contributions/instruction-for-reviewers |
| S8 | CoRL 2026 | Instruction for Reviews | https://www.corl.org/contributions/instruction-for-reviews |
| S9 | CoRL 2026 | Instruction for Authors | https://www.corl.org/contributions/instruction-for-authors |
| S10 | CoRL 2026 | Instruction for Rebuttal | https://www.corl.org/contributions/instruction-for-rebuttal |
| S11 | CoRL 2026 | Call for Papers | https://www.corl.org/contributions/call-for-papers |
| S12 | CoRL 2025 | Instruction for Reviews | https://2025.corl.org/contributions/instruction-for-reviews |
| S13 | ICRA 2027 | Call for papers / submission details | https://2027.ieee-icra.org/contribute/call-for-icra-2027-papers-now-accepting-submissions/ |
| S14 | ICRA 2027 | Information for ICRA Reviewers (IEEE RAS) | https://www.ieee-ras.org/conferences-workshops/fully-sponsored/icra/information-for-icra-reviewers/ |
| S15 | ICRA 2027 | Information for ICRA Associate Editors (IEEE RAS) | https://www.ieee-ras.org/conferences-workshops/fully-sponsored/icra/information-for-icra-associate-editors/ |
| S16 | ICRA 2026 | Call for papers | https://2026.ieee-icra.org/contribute/call-for-icra-2026-papers-now-accepting-submissions/ |
| S17 | IROS (edition not named; timeline has a 2 March deadline) | Information for IROS Associate Editors (IEEE RAS) | https://www.ieee-ras.org/conferences-workshops/financially-co-sponsored/iros/information-for-iros-associate-editors/ |
| S18 | IROS (page metadata says 2017 review board) | Information for IROS Reviewers (IEEE RAS) | https://www.ieee-ras.org/conferences-workshops/financially-co-sponsored/iros/information-for-reviewers-4/ |
| S19 | RA-L (modified 2026-01-14) | Information for Authors | https://ieee-ras.org/publications/ra-l/information-for-authors-ra-l |
| S20 | RA-L | Information for Reviewers | https://ieee-ras.org/publications/ra-l/ra-l-information-for-reviewers |
| S21 | RA-L (modified 2025-12-17) | Information for Associate Editors | https://ieee-ras.org/publications/ra-l/information-for-associate-editors |
| S22 | RA-L (modified 2026-08-04) | Journal home (conference transfer windows) | https://ieee-ras.org/publications/ra-l |
| S23 | RA-L | FAQ | https://ieee-ras.org/publications/ra-l/faq |
| S24 | RA-L (says it applied until IROS 2022) | Information for RA-L option conference organizers | https://www.ieee-ras.org/publications/ra-l/information-for-ra-l-option-conference-organizers/ |
| S25 | ICLR 2027 | Reviewer Guidelines | https://iclr.cc/Conferences/2027/ReviewerGuidelines |
| S26 | NeurIPS 2026 | Reviewer Guidelines | https://neurips.cc/Conferences/2026/ReviewerGuidelines |
| S27 | NeurIPS 2026 | Main Track Handbook (review form, rebuttal) | https://neurips.cc/Conferences/2026/MainTrackHandbook |
| S28 | CoRL 2023 | Official review invitation (form fields and options), read signed in | https://api.openreview.net/invitations?id=robot-learning.org/CoRL/2023/Conference/-/Official_Review&expired=true |
| S29 | CoRL 2024 | Public official reviews of accepted papers (field names and score values) | https://api2.openreview.net/notes?forum=<accepted paper id> |

Not reachable or not opened (UNVERIFIED): RSS 2026 reviewer guidelines and review-process pages (/2026/information/reviewer-guidelines/, /2026/reviewps/, /2026/information/authorinfo/ returned errors); CoRL review form fields and full score scale (OpenReview invitation needs sign-in); ICRA/IROS criteria-rating names inside the PaperPlaza form; RA-L review form questions and the RAS review-form PDFs (fetch not permitted); the official IROS 2026 and IROS 2027 conference sites (not found by search, guessed URL not permitted); the RA-L page reachable at ieee-ras.org/publications/ra-l/ra-l-information-for-authors/ (not permitted; S19 used instead). Note: the non-www ICRA reviewer and AE URLs (ieee-ras.org/conferences-workshops/fully-sponsored/icra/information-for-reviewers and .../information-for-associate-editors) served T-RO/T-RL journal guidance on 2026-11-20; they are not used for ICRA.

## 2. Venues

### RSS 2027 (two stages, hypothesis first; changed from 2025-2026)

Stages and scale (S1, S2, S3):
- Stage 1: 6-page extended abstract, "up to 5 pages of content and 1 page of references"; deadline 2026-12-04. Experiments may be missing or preliminary; supplementary material, appendices and websites are not reviewed.
- Stage 1 review form: Value of Hypothesis (1 Limited Interest, 2 Possibly Interesting, 3 Interesting, 4 Strongly Interesting); Approach and Hypothesis (text); Feasibility of Conclusion (1 Weak, 2 Limited, 3 Good, 4 Very Strong); Feasibility text; Extension Charter suggestions (text); confidential comments.
- Stage 1 decision: reject or invitation to rebuttal (only a subset). Rebuttal 2027-02-05 to 02-12; template "will be made available in due course"; length UNVERIFIED (1 page in 2025 and 2026).
- Stage 2 decision: reject or invitation to execute an Extension Charter, "a concrete, constructive roadmap detailing the experiments, proofs, or validations". New or different experiments are expected here (FAQ 6). Final paper 8 pages excluding references, zip supplement up to 100 MB; final acceptance checks that authors "faithfully executed the pre-negotiated Extension Charter".
- Negative results: "Submissions will not be rejected for yielding negative experimental results", but "an experiment that didn't work" is not enough; it needs rigorous method such as comprehensive ablations (FAQ 2).
- Related work at Stage 1: only citations needed to establish novelty; reviewers judge direct relevance, not completeness.
- Desk reject: anonymity breaks, external links, hallucinated citations (automated checks), modified template, draft marks or page numbers, dual submission. Reviews and reviewer names of accepted papers are published.
- Limitations section: required with desk reject in RSS 2025 (S5, S6); not mentioned in the RSS 2026 or 2027 CFP (UNVERIFIED for 2026-2027).
- Edition before (RSS 2026, S4; 2025, S5): one full paper (8 pages excl. references in 2026; no page limit in 2025), three reviewers, recommendation SA/A/WA/WR/R/SR, round-1 reject or 1-page rebuttal, no new paper version during rebuttal; RSS 2025 also had a single-blind Demo track ("Demonstrating ...").

| Official criterion (Stage) | Complaint kinds | Praise | Weight | Reason from the text |
|---|---|---|---|---|
| Value of Hypothesis (1) | a2, a3, e1, e2 | p2, p12 | high | scored 1-4 on likely "impact on the community" |
| Approach and Hypothesis stated, testable (1) | o1, a3 | p12 | high | FAQ 9: needs "a concrete technical problem formulation" |
| Feasibility of Conclusion (1) | g1, g2, g7, b1, d3 | p1 | high | will planned experiments "support or falsify the hypothesis" |
| Plan for executing and interpreting experiments (1) | c1, c4, g5, g9 | p8 | medium | part of the feasibility text; statistics not named |
| Claims scoped to evidence (1-2) | d1, d4 | p3 | medium | "only part of the hypothesis can be supported" scores 2 |
| Negative results with explanation of why (1-2) | a1, a6, b4 | p5, p2 | medium | needs "comprehensive ablations" testing why it failed |
| Related work, direct only (1) | e3 | - | low | judged by direct relevance, not completeness |
| Preliminary or missing experiments (1) | o5 | - | low | "Experiments may be missing or preliminary" |
| Charter executed, insights achieved (2) | o5, d4, b, g | p2 | high | sole final-acceptance test |
| Reproducibility | o3 | p13 | medium | authors responsible that "all results are reproducible" |
| Real-robot evidence | d2 | p4 | not stated | no mention in S1-S3 |
| Compliance (template, anonymity, citations) | f1 | - | high | each is a desk-reject rule |

### CoRL 2026

Stages and scale (S7-S11; 2025 in S12):
- Score: "Weak accept (5) is the acceptance threshold"; 2025 and 2026 form fields UNVERIFIED: the review invitations are visible only to reviewers, even when signed in (checked 2026-11-20), and no 2025 or 2026 review is public yet. Confidence score required.
- Review form of earlier editions (checked 2026-11-20, signed in to OpenReview; S28 CoRL 2023 review invitation, S29 public CoRL 2024 reviews):
  - CoRL 2023 fields, in order: summary of paper; review (quality, clarity, originality, significance, strengths and weaknesses); questions for rebuttal (authors may submit a revised manuscript); originality (Excellent "surprising new results", Very Good "major advance", Good "some advance", Fair "incremental work, no significant advance", Poor); technical quality (Excellent to Poor; Good = "some additional experiments or analyses needed", Fair = "significant additional evidence required"); clarity of presentation (Excellent to Poor); impact (4 major impact, 3 incremental and unlikely to have much impact, 2 unsure, 1 not very relevant to the robot learning community); robotics focus (sufficient demonstration on hardware; highly relevant but no hardware experiments; relevant but unlikely to deploy to hardware soon; irrelevant to robotics); quality of the limitations section (clearly addressed; additional details required; not well addressed); recommendation (strong accept, weak accept, weak reject, strong reject); confidence (1-5); summary of recommendation.
  - CoRL 2024 public reviews carry the same fields with numeric scores (originality, technical quality, clarity of presentation, potential impact, robotics focus, quality of the limitations section, recommendation, confidence) plus a free review title.
  - Mapping: originality -> e1, e2 and praise p2, p10; technical quality -> g, b, c, d1, d3 and praise p1, p3, p5, p8; clarity -> o1, o2; impact and relevance -> a2, f3 and praise p11; robotics focus -> d2 and praise p4 (hardware evidence is its own scored field, so it weighs high); limitations quality -> f2, a6 and praise p14.
- New in 2026: first-round rejection without rebuttal when no reviewer and not the AC gives weak accept or above; SACs and PCs check all candidates.
- Rebuttal: one-page PDF on a fixed template (references included), no links, no individual replies, no paper update; "focused on addressing any factual errors" (S9) and on clarifications "specifically requested by the reviewers" (S10). New experiments: CoRL 2025 said reviewers "should not request additional experimental results in rebuttal" (S12); 2026 pages do not repeat that line. Conflict: S8 still says authors "update their papers during the rebuttal period", S9 and S10 say they cannot; follow S9/S10.
- Required post-rebuttal box (new 2026). Camera-ready gets a 9th page.
- Page limit: 8 pages main text, Limitations section counted inside; references, acknowledgments, appendix outside; reviewers not required to read the appendix. Video "highly encouraged", up to 250 MB, about 3 minutes; video, code and data encouraged as supplement.
- Limitations section required: "limiting assumptions, failure modes, and other limitations". Reviewers told: "A frank limitations section is a sign of a careful paper".
- Desk reject (consensus of all PCs and SACs): reciprocal reviewing not met, formatting (too long, wrong format), anonymity (paper, supplement or link), scope (relevance to robot learning by intent or outcome). Also: non-existent citations (GPTZero check, then manual), multiple near-duplicate papers by the same authors, undisclosed dual submission. Generative-AI use must be disclosed at submission.
- Prior work: papers within the last 4 months are contemporaneous; arXiv-only papers may be excused.

| Official criterion | Complaint kinds | Praise | Weight | Reason from the text |
|---|---|---|---|---|
| Relevance to learning for physical robots (scope) | a3 | p7 | high | scope is a desk-reject reason and "the first question" |
| Convincing evaluation, real hardware | d2, d1 | p4 | high | "Value real-robot evidence highly" |
| Claims "objectively established" | g7, g1, g8, b1, b3, c1, c4, d3 | p1, p3, p8 | high | one of four named criteria |
| Significance and novelty | e1, e2, a2 | p2, p10 | high | named criterion |
| Scientific or technological impact | a2, d4 | p11 | medium | named criterion, no detail given |
| Limitations section honest about failure modes | f2, a6 | - | high | required section; reviewers told to check it |
| Ablations and baselines | b2, b4 | p5 | medium | implied by "objectively established" only |
| Related and contemporaneous work | e3 | - | medium | 4-month window; arXiv-only may be excused |
| Reproducibility details, video, code, data | o3 | p6, p13 | medium | "strongly encouraged", not required |
| Clarity | o1, o2 | - | not stated | not a named criterion |
| Formatting, anonymity, citations, dual submission | f1 | - | high | desk-reject rules |

### ICRA 2027 (ICRA 2026 the same unless noted)

Stages and scale (S13-S16):
- Single round, no rebuttal mentioned (S13, S16). Paper must stand on its own.
- Score (S14): A 5.0 Definitely accept; B+ 4.5 Accept; B 4.0 High borderline; B- 3.5 Borderline; C 3.0 Low borderline; C- 2.5 Reject; D 2.0 Definitely reject ("trivial, wrong, or already known"); U 1.0 Inappropriate (flag: out of scope, suspected plagiarism, incomplete).
- Review content (S14): confidence, ratings on criteria (names UNVERIFIED), optional confidential note to the editorial board, detailed review justifying the assessment; at least 1,200 non-white characters. At least two reviews per paper; the AE resolves disagreements instead of averaging (S15).
- Summary reject by AE (S15, decided by Editor and EiC, capped at 10-15% of submissions): over 8 pages; clearly no novel contribution (justified from prior work); significant technical errors; previously published. Not grounds: "incremental contribution", lack of real-world experiments, poor writing, scope.
- Page limit: 8 pages including references and all supplementary content; over-length papers "returned without review". Double-anonymous.
- Video: strongly encouraged, only with the initial submission, up to 180 s, 20 MB, mpeg/mp4/mpg. ICRA 2026: reviewers need not view anything beyond paper and video (S16).
- Generative AI: disclose AI-generated text, figures or code in the acknowledgments; reviewers may not put manuscripts through AI systems.
- IROS-ICRA transfer: papers rejected at IROS may resubmit with an anonymous Author Response File; reviewed normally (new since ICRA 2026).

| Official criterion | Complaint kinds | Praise | Weight | Reason from the text |
|---|---|---|---|---|
| Novel contribution against prior work | e1, e2, e3 | p10 | high | "no novel contribution" is a summary-reject ground; D = "already known" |
| Technical correctness | o4, d3 | - | high | "significant technical errors" is a summary-reject ground |
| Incremental contribution | e2 | - | medium | explicitly not a summary-reject ground, still scored |
| Real-world experiments | d2 | p4 | low | lack of them is explicitly not a summary-reject ground |
| Writing quality | o1, o2 | - | low | poor writing is not a summary-reject ground |
| Evaluation design, baselines, statistics | g, b, c | p1, p5, p8 | not stated | criteria names UNVERIFIED |
| Completeness | o5 | - | high | "incomplete" papers get the U flag |
| Video quality | - | p4 | medium | strongly encouraged; no review rule found |
| Page limit, anonymity, AI disclosure | f1 | - | high | over-length returned without review |

### IROS (edition not named on the RAS pages)

- Same A to U scale as ICRA (S17, S18); AE guidance says B- "should not be used". Reviews: confidence, criteria ratings (names UNVERIFIED), confidential note, detailed review, 1,200-character minimum (S18, metadata says 2017).
- No rebuttal: "we will *not* be using the rebuttal process" (S17).
- Summary reject grounds (S17, cap 10-15%): no novel contribution, significant technical errors, previously published, plagiarism. Not grounds: incremental contribution, no real-world experiments, poor writing, AE's view of scope.
- AE also recommends presentation type (regular oral or multimedia) and award candidacy.
- Page limit, video rules, AI policy of IROS 2026/2027: UNVERIFIED (official IROS site not reached). Weight table: use the ICRA table.

### RA-L (IEEE Robotics and Automation Letters)

Stages and scale (S19-S24):
- Rounds: first decision within 3 months (Accept, Reject, or Revise and Resubmit); revision within 30 days with a Statement of Changes, no extension; second and final decision Accept or Reject, within 5 months; final decision guaranteed within 6 months. Re-review of the revision by the original reviewers is not the default (S21). New experiments in revision: not stated.
- Reviewer recommendation options or rating scale: not listed (UNVERIFIED). AE recommends publication, reject or revise and resubmit; technical editorial rejects are recorded as "Unsuitable" (S21).
- Quality bar: "timeliness favours originality over maturity"; comparable to short T-RO/T-ASE papers; conference A, B+ or B papers could become Letters after deep revision, some B- papers if substantially improvable (S20, S21).
- Reviewer prompts (S20): contribution and significance, clear writing and organization, purpose stated in the introduction, references relevant and complete (suggest journal papers from the last 2-3 years), technical soundness, how to shorten if too long, video consistency, quality and freedom from commercialism.
- Editorial reject without review: mainly "incomplete or otherwise clearly unsuitable papers", about 10-15% (S21); supplemental text or figures as multimedia; resubmission without response and highlighted diff.
- Page limit: 6 pages two-column including figures, references and appendices, plus up to 2 paid pages at 175 USD each (max 8). No supplemental text or figures; multimedia: one video, datasets, code, as one zip up to 50 MB with ReadMe.txt and Summary.txt; paper must read on its own. Double-anonymous, at least two reviewers. Human-subject or animal research needs an approval statement.
- Conference link (S22, modified 2026-08-04): no conference deadlines; accepted RA-L papers may transfer for presentation within 270 days of acceptance and inside a window (ICRA 2027: 2026-03-01 to 2026-12-31; IROS 2027: 2026-08-01 to 2027-04-30). The older simultaneous "RA-L with conference option" (conference SPC accepts even when RA-L rejects) is described as applying "until IROS 2022" (S24); S21 still mentions conference-option recommendations, so treat any current simultaneous option as UNVERIFIED.

| Official criterion | Complaint kinds | Praise | Weight | Reason from the text |
|---|---|---|---|---|
| Originality, timely contribution | e1, e2 | p2, p10 | high | "favours originality over maturity" |
| Related work coverage, recent journals | e3 | - | high | a suggested review section of its own |
| Technical soundness | o4, d3, g7 | p1 | high | named reviewer prompt |
| Significance of the contribution | a2 | p11 | medium | named prompt |
| Maturity: breadth, many seeds, many robots | d1, c1, c4 | p3, p8 | low | maturity explicitly ranked below originality |
| Clarity, organization, length | o1, o2 | - | medium | named prompts; 6-page limit is strict |
| Completeness | o5 | - | high | incomplete papers are editorially rejected |
| Multimedia (video, code, data) | o3 | p6, p13 | medium | allowed and reviewed for consistency and quality |
| Limitations section | f2 | - | not stated | no requirement found |
| Format: pages, no supplemental text | f1 | - | high | grounds for rejection without review |

## 3. Cross-venue emphasis

H = high, M = medium, L = low (explicitly de-emphasized), - = not stated. ICLR column from S25, NeurIPS from S26-S27.

| Group | RSS 2027 | CoRL 2026 | ICRA/IROS | RA-L | ICLR 2027 | NeurIPS 2026 |
|---|---|---|---|---|---|---|
| a Scope, insight, practical value | H (value of hypothesis) | H (relevance, impact) | M | M | H ("significance of the work") | H (significance rating) |
| b Baselines, controls, ablations | H at Stage 2 (Charter) | M | - | - | L (missing comparisons "cannot be a basis for rejection") | M (quality) |
| c Statistics | M | M | - | L (maturity) | - | M (quality; checklist) |
| d Claims beyond evidence | H (feasibility of conclusion) | H (objectively established) | M | M | H ("Does the paper support the claims?") | H (quality) |
| e Novelty and prior art | M (novelty; related work condensed) | H | H (summary reject) | H (originality first) | M (novel findings; SOTA not required) | H (originality rating) |
| f Venue compliance | H (desk rejects; Charter) | H (Limitations, scope, format) | H (8 pages incl. references) | H (6+2 pages, no supplement text) | M | M (checklist mandatory) |
| g Measurement design and validity | H (support or falsify) | H (objectively established) | - | M (soundness) | M | M (quality) |
| o Clarity, reproducibility, errors | M (formulation; reproducibility) | M (reproducibility encouraged) | H for errors, L for writing | M | M | H (clarity rating) |
| p1 Careful evaluation design | H | H | - | M | M | M |
| p2 Informative findings | H (insights, negative results) | H | M | H | H | H |
| p3 Broad evidence | M | M | - | L | - | - |
| p4 Real-robot evidence | - | H | L (not a reject ground) | - | - | - |
| p5 Thorough ablations | M (negative results) | M | - | - | - | - |
| p6 Released assets | L at Stage 1 | M | M (video) | M | - | M (checklist) |
| p8 Careful statistics | M | M | - | L | - | M |
| p11 Downstream usefulness | M | M (impact) | - | M | M | M |
| p12 Clear framing | H (hypothesis) | M | - | - | H (problem and motivation) | M (clarity) |
| p13 Reproducibility | M | M | - | M | - | H (checklist) |

Notes on the ML comparison: ICLR 2027 allows revisions and new experiments in discussion ("should not significantly change the content"); NeurIPS 2026 allows new results in a 10,000-character text rebuttal per review but no revised paper. So at ICLR and NeurIPS b, c and g can be partly fixed during discussion; at CoRL (1-page factual rebuttal, first-round reject), ICRA and IROS (no rebuttal) they cannot, and at RSS 2027 they become Charter items only if the Stage 1 design is judged feasible.

## 4. Venue-specific checks the generic catalog does not cover

RSS 2027
- Stage 1 fits 5 pages of content plus 1 page of references; any appendix inside the 5 pages; nothing critical left to supplement or website.
- Explicit, testable hypotheses and a concrete problem formulation; the experiment plan says how results would support or falsify each hypothesis.
- A negative-result framing explains why the approach failed (ablations), not only that it failed.
- Related work trimmed to what establishes novelty.
- No links, acknowledgments or self-revealing citations; all references real (automated check).
- For Stage 2: every Charter item executed and traceable in the 8-page paper.
- Limitations section: include it (required in 2025; 2026-2027 status UNVERIFIED).

CoRL 2026
- Limitations section inside the 8 pages, naming assumptions and failure modes.
- Scope sentence: the learning question for physical robots, or evaluation mainly on physical robots or realistic simulation with a transfer argument.
- Real-robot or credible sim-to-real evidence for any real-world claim.
- Initial version must earn at least one weak accept: no rebuttal-only fixes, the rebuttal is 1 page, no links, no paper update.
- Video (250 MB max, about 3 min) and code or data offered; no identifying links.
- Generative-AI use disclosed in the submission form; no near-duplicate sibling submissions; one author registered as reviewer.

ICRA 2027 and IROS
- 8 pages including references, acknowledgments and any supplement (ICRA); IROS limit UNVERIFIED.
- Video uploaded with the first submission (180 s, 20 MB, mp4); no later upload.
- AI-generated content disclosed in the acknowledgments.
- No rebuttal: every likely question answered in the paper.
- At least three ICRA keywords; for IROS-ICRA transfers, an anonymous Author Response File with the IROS reviews.
- An on-site presenter is required, or the paper counts as a no-show.

RA-L
- 6 pages including references and appendices (8 with paid pages); no supplemental text or figures anywhere.
- Multimedia zip up to 50 MB with ReadMe.txt and Summary.txt; paper readable without it.
- Recent journal papers (last 2-3 years) in related work.
- Plan for a 30-day revision with a Statement of Changes; a resubmitted rejected paper needs a response and a highlighted diff.
- Ethics approval statement for human-subject or animal studies; ORCID for all authors.
- Conference presentation is a transfer after acceptance, inside the conference window.
