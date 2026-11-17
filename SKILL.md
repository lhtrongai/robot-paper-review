---
name: "robot-paper-review"
description: "Blind pre-submission review of a robot learning or embodied AI paper for a named venue: fetches current rules, recent reviews and fresh prior art at run time, applies venue-family weights, predicts complaints and score."
---

# Robot paper review

Review a finished or near-finished paper the way reviewers at the target venue will, before it is submitted. Scope: robot learning and embodied AI (VLA and robot foundation models, manipulation, humanoids, sim-to-real, robot benchmarks, robustness and evaluation studies) at ML venues, robotics venues, journals and workshops. Vietnamese triggers include "review bài này như reviewer", "phản biện mù", "chấm thử trước khi nộp", "reviewer sẽ chê gì", "viết thử metareview", "kiểm rebuttal". Not for writing or revising the paper (use a paper-writing skill) and not for judging a research direction before the work exists (use research-direction-check).

Why this skill exists: an uncalibrated AI reviewer catches obvious problems but misses part of what real reviewers care about, and it does not know what reviewers at a given venue complain about this year. This skill fetches current venue rules and fresh prior art at run time, applies venue-family priors, and is checked against real public reviews. Measured hit rates, the reviewer model they were measured on, and a digest of recurring complaints live in CALIBRATION.md next to this file; read it at the start of every run. If the file is not next to this one, fetch the current version from https://raw.githubusercontent.com/lhtrongai/robot-paper-review/main/CALIBRATION.md and name the source in the header; if neither works, treat every venue family as UNCALIBRATED.

## 0. Ground rules

- Blind means the reviewer sees only the anonymized paper, the venue, year and track, and optionally the call for papers. Run in a chat with no memory and no project attached (incognito, or memory off, outside any project that holds the authors' notes). Do not read the authors' notes, project documents, Notion pages or chat history about the paper. If any of these are present in context, say so and label the whole output "NOT BLIND".
- When the paper under review is already public (a calibration test), exclude its own review forum, its reviews and any page quoting them from every search.
- Fresh information only. Rules, scales, page limits and AI policies change every year. Fetch them at run time, record URL and fetch date for each, and mark anything you could not verify as UNVERIFIED. Never present a remembered venue fact as current.
- Every novelty or prior-art complaint names a specific paper with a link you actually opened or saw in search results.
- Every complaint points to a location in the paper. Never invent numbers; quote the paper's own.
- Write the review in English; talk to the user in their language.

## 1. Modes

- Full (default for a real submission): all steps, including the trend scan.
- Quick (while drafting): skip step 3 and say so in the output header.
- Mock metareview and rebuttal check: see step 11.

## 2. Venue brief and family (fetch at run time)

Identify the venue, year, track and its family below. Fetch for that exact year: call for papers or author guide, reviewer guidelines, review form and score scale, AI-use policy, paper checklist, rebuttal or revision rules, and which reviews are made public. Output a short venue brief with URLs and dates.

Each family has a prior on what reviewers weigh most. Priors marked UNCALIBRATED come from general knowledge, not from measured reviews: say so in the output and let the fetched reviewer guidelines override them.

- ML conferences (ICLR, NeurIPS, ICML main tracks). Calibration status: see CALIBRATION.md. Weigh: novelty against recent named work, insight into why an effect happens, measurement validity, statistical care, positioning. Simulation-only evidence is acceptable when claims are scoped to it.
- ML dataset, benchmark and evaluation tracks (for example NeurIPS Evaluations and Datasets). UNCALIBRATED. Weigh: whether the benchmark measures what it claims, what it reveals that existing benchmarks cannot, documentation, licensing, hosting and maintenance, accessibility.
- Robot learning conferences (CoRL, RSS). UNCALIBRATED. Weigh: relevance to robot learning rather than a pure benchmark story, real-robot evidence or an explicit argument for transfer, comparison with current robot policies. Check the year's review structure (for example a hypothesis-first first stage, or first-round rejection without rebuttal) and judge by it.
- Broad robotics conferences (ICRA, IROS). UNCALIBRATED. Weigh: practical contribution, real-robot validation, clarity for readers outside ML, supplementary video. Decisions run through associate editors with short reviews, so the abstract, first figure and experiments carry most of the weight.
- Journals (RA-L, T-RO, IJRR and similar). UNCALIBRATED. Weigh: completeness, breadth of comparisons and ablations, depth of related work, reproducibility detail, and for long-form journals the extension beyond any prior conference version. Outcomes include major and minor revision, so the review must end in a concrete revision list, not only reasons to reject.
- Workshops. UNCALIBRATED. Weigh: fit to the workshop call, clarity, an interesting early result. Check whether the workshop is archival, because that affects later submission.

## 3. Trend scan (run time, full mode)

1. Recent public reviews: find 5 to 10 public reviews from the venue's latest edition for papers of the same contribution type and topic. If the venue publishes none, use the closest venue that does and say which. List recurring complaints and mark those raised by 2 or more reviewers of the same paper.
2. Prior art, last 12 months: search arXiv, OpenReview and the venue proceedings for (a) work asking the same question, (b) the benchmark, protocol or method the community currently treats as standard for this topic, including ones released after the paper's related work was written, (c) issue trackers and documentation of the benchmarks and simulators the paper uses, where the effect may already be reported. List the 3 to 5 closest works with one line each on how the paper differs or fails to differ.
3. Reachability first: OpenReview usually answers automated requests with a browser challenge (see the trend-scan notes in CALIBRATION.md). Spend one fetch on a review page before planning the scan; if it is blocked, stop retrying and fall back in this order: (a) public reviews of other papers that the user attached for this run; (b) the latest complaint digest in CALIBRATION.md. Write in the header which source was used, for example "trend scan failed (browser challenge), used digest of <date>". Do not guess complaints beyond what the source shows.
4. Record every query and URL for the audit.

## 4. Contribution type

- Empirical analysis (robustness, diagnosis, controlled comparison, replication, negative result): does it explain why, not only show that an effect exists? Does it change a practitioner's decision?
- Method: does it beat strong, current baselines under equal budgets, with ablations isolating each component?
- Benchmark, dataset, metric or protocol: does it measure what it claims, reveal something existing benchmarks cannot, and come released and usable?
- Systems: does the integration achieve something its parts could not, shown on hardware?

## 5. Checklist by error group

Answer every question with a location. The first two groups had the lowest recall in calibration; do them first and in full.

Measurement design and validity
- Does each perturbation or condition change exactly one factor, or two at once?
- After a perturbation, is the task goal still identifiable while the success checker is unchanged? Was that checked by a person or a rule?
- Do compared conditions get the same budget (steps, wall-clock time, horizon, control frequency)? Does a shared harness distort any model relative to its native settings?
- Were conditions, states or tasks selected using outcomes (a reference model's success, the test set itself, anomalous gains)? Does the conclusion survive a different selection?
- Does the metric measure what the paper says, or only agreement with a reference policy?

Baselines, controls and ablations
- What is the simplest baseline or control a reviewer will think of first (an LLM rewriting the instruction, a sham control with the same motion but no intervention, a zero-strength perturbation through the same code path, the closest published method on the same benchmark)? Was it run?
- Is every component isolated by an ablation? Are baselines current and given equal budgets?

Novelty and prior art
- Is the main effect already documented in papers, issue trackers or simulator documentation? If the paper only measures known effects more systematically, that is a MAJOR point; name the sources.
- Does it position against the benchmark or method the community adopted most recently?

Scope, framing and insight
- Is the main question in the first two sentences of the abstract? Does the title promise more than the experiments answer?
- Does the paper explain the mechanism, not only show the effect? Does a proposed procedure or metric demonstrably improve decisions, for example agreement with real-robot rankings? If not, MAJOR.

Claims beyond the evidence
- One model, one benchmark, one simulator or one camera angle generalized to all? Simulation presented as deployment? Claims made true by definition?
- Is the limitations section real?

Statistics
- Episodes per cell, seeds, confidence intervals, paired tests, power for the smallest effect of interest, multiple comparisons. Are headline differences outside the noise?

Venue compliance
- Page limit, template, anonymity including links and self-citations, mandatory statements, citations that exist.

Other
- Clarity (internal jargon, dense abstract), reproducibility (code, data, configurations, checkpoints), errors in tables.

## 6. Three reviewer lenses

Most issues the calibrated reviewer missed were raised by a single real reviewer, each bringing one angle. Write weaknesses from three lenses, then merge duplicates:
1. Methods and statistics: measurement design, statistics, baselines and controls.
2. Venue practitioner, chosen by family: ML researcher for ML conferences; robot learning practitioner for CoRL and RSS; roboticist outside ML for ICRA and IROS; completeness reviewer for journals; dataset maintainer for benchmark tracks. This lens asks whether the paper matters to that audience and whether its claims hold for them.
3. Related work: novelty and prior art, using the trend scan.

## 7. Ranking rules

General (from the ML calibration):
- Rank highest what real reviewers most often agree on: the effect is already known or the paper is incremental over a named work; limited insight or unclear practical value; one model or one benchmark generalized too far; the measurement does not measure what it claims; the obvious baseline or control is missing.
- Statistics enter the top 3 only when the headline depends on them (a claimed reversal within noise, a single run behind the main claim).
- Compliance and citation hygiene enter the top 3 only if they risk desk rejection.

Family adjustments (UNCALIBRATED priors, revise per step 10):
- Robot learning conferences: missing real-robot evidence, or simulation claims not argued to transfer, ranks at the top unless the call explicitly accepts simulation-only work.
- ICRA and IROS: presentation that a non-ML reader cannot follow ranks higher than at ML venues.
- Journals: missing comparisons, ablations or related work rank higher, phrased as revision requests.
- Benchmark tracks: measurement validity, release, documentation and licensing rank at the top.

Score with the venue's own scale as a band, not a point. In calibration the reviewer missed the real outcome by about one band in both directions, so state confidence honestly. Keep at most 10 weaknesses in total; merge near-duplicates instead of listing them.

## 8. Output format (in this order)

0. Header: mode, blind or NOT BLIND, venue family and its calibration status, calibration date and reviewer model, warnings from step 10, trend scan status.
1. Summary of the paper in 5 sentences, precise enough that the authors would recognize it.
2. Three strengths.
3. Desk-reject checks: pass, fail or UNVERIFIED.
4. Weaknesses ranked BLOCK, MAJOR, MINOR; each with error group, lens, location and a short fix.
5. Top 3 complaints real reviewers are most likely to raise.
6. Up to 5 questions for the authors.
7. Score band in the venue's scale, confidence 1 to 5, and the lean (conferences: accept or reject; journals: accept, minor, major or reject).
8. The 3 cheapest experiments or edits that address the top complaints, ranked by cost.
9. Audit: venue URLs with fetch dates, trend-scan sources, search queries in order, and the model that wrote this review.

## 9. Two independent passes

For a real submission, run twice in separate blind chats with different models. Merge: issues both passes raise come first; issues only one raises are listed separately with the pass that raised them.

## 10. Calibration and staleness

- Calibration is specific to a reviewer model, a venue family and a period. Warn in the header when the current model differs from the calibrated one, when the calibration is older than 12 months, or when the venue family is UNCALIBRATED.
- After real reviews arrive (own submissions, or public papers used for practice): code each real issue into an error group, mark it as hit in the top 3, hit in the full list or missed, note complaints no reviewer raised, and log the row with the date, venue family and reviewer model. Have a second grader (another model or a person) re-check at least 20% of the matches.
- Change steps 5 to 7 only when a pattern holds across at least 5 papers of that family. Before adopting a change, run the old and new version blind on the same fresh papers with public reviews and the same web budget, and fix the deciding metric in advance: top-3 recall paired per paper, with precision as the guard. Report full-list recall with both issue-level and item-level matching, because the two can disagree. Keep the change only if top-3 recall rises on most papers without a fall in precision.
- Before reviewing, read CALIBRATION.md and compare its latest row with the current run: different reviewer model, calibration older than 12 months, or a venue family with no row means the hit rates are hints only; say so in the header.
- Append to CALIBRATION.md from the authors' own chat, never from a blind run. CALIBRATION.md holds only aggregate numbers from public papers, so a blind run may read it; per-paper grading files and the authors' notes stay outside the skill folder and a blind run must not read them.
- Many robotics conferences and journals do not publish reviews, so those families can only be calibrated from the user's own submissions and outside readers. Expect that to be slow and say so.

## 11. Other modes

- Mock metareview: given the reviews (real or from step 9), write the area chair summary: consensus strengths, decisive weaknesses, what a second round or revision would demand.
- Rebuttal check: given reviews and a rebuttal draft, judge for each concern whether it is resolved, partly resolved or unaddressed, and whether the rebuttal follows the venue's rules on length and new results.