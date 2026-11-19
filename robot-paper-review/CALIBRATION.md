# Calibration log

Append-only. Each row records how well blind reviews predicted what real reviewers raised, for one venue family, one period and one reviewer model. Numbers are only meaningful for the model and period in their row: when the model running the skill is different, or the newest row for the venue family is older than 12 months, treat every number here as a hint and say so in the review header.

How a round is measured: real reviews are coded into issues before any prediction is read; each issue is matched against the blind review's top 3 and full weakness list (yes, partial, no); precision is the share of the review's weaknesses that match a real issue; a second grader (another model or a person) re-checks at least 20% of the papers. Only aggregate numbers are kept here, never per-paper review text.

Error groups: (a) scope and insight, (b) baselines, controls and ablations, (c) statistics, (d) claims beyond the evidence, (e) novelty and prior art, (f) venue compliance, (g) measurement design and validity, (o) clarity, reproducibility and technical errors.

## Rounds

| Date | Venue family, venue | Papers, topic | Reviewer model | What was compared | Results |
|---|---|---|---|---|---|
| 2026-11-16 | ML conferences, ICLR 2027 | 10, VLA evaluation and robustness | not recorded | earlier rubric prompt alone | Full-list recall 66%, top-3 recall 34%; issues raised by 2 or more reviewers 84% and 63%. Lowest recall: (g) 56% on 24 issues, (b) 56% on 9. Statistics ranked too high; venue compliance raised on 5 papers where no reviewer raised it. |
| 2026-11-17 | ML conferences, ICLR 2027 | 10 new papers, same topic | Claude Opus 5.5 (graders: the same model on all papers, a Sonnet model on 2, kappa 0.78 on precision calls) | this skill vs the earlier prompt, both blind | Top-3 recall 35% vs 30% (skill better on 8 of 10 papers); precision 56% vs 47%; full-list recall 66% vs 60% by issue matching but 43% vs 46% by item matching, so no reliable difference; consensus issues 88% vs 85%; prior art (e) 94% vs 67% on 9 issues; (b) unchanged at 56%. Caveats: the skill had the larger search budget; its review-trend step failed in 10 of 10 runs. |

## Catalog saturation runs

These runs grow the complaint catalog (references/complaint-catalog.md); they do not measure a blind reviewer, so they are not rows of the table above.

| Date | Venue, papers | Selection | Coding | Result |
|---|---|---|---|---|
| 2026-11-19 | ICLR 2027, 30 papers on robot-learning evaluation, benchmarks, robustness and measurement | Title screen of all submissions before any review was read; withdrawn, or mean rating below 2.5 on the 1-4 scale, at least 2 reviews; the 20 calibration papers excluded; 60 eligible, order fixed by `random.Random(20261119).shuffle` on the sorted ids | Only issues raised by 2 or more reviewers of the same paper (102 issues); one coder, Claude Opus 5.5, no second grader | No new error group in 30 papers; 6 new kinds (27 to 33), added at papers 1 (2), 4, 9, 13 and 20, none in papers 21-30. The pre-registered stop rule (last 10 papers: no new group and at most 2 new kinds) was already met at paper 11; coding continued to 30 by mistake, and the extra 19 papers added only 2 kinds. |
| 2026-11-19 to 2026-11-20 | ICLR 2025-2027, NeurIPS 2025-2026, CoRL 2023-2024, TMLR; 18 papers in three topics (evaluation 13, manipulation 3, locomotion 2) | Title screen of all submissions with public reviews (accepted, rejected, withdrawn, pending), one pool per topic, cap 25 per venue-year (manipulation 9), seeded order per topic; manipulation re-ordered CoRL first by an amendment recorded before its reviews were read | Complaints and specific praise raised by 2 or more reviewers, each row tagged with severity (reject reason or suggestion), rebuttal outcome and decision; one coder per topic, Claude Opus 5.5 | Evaluation: complaints saturated at paper 12 (10-paper rule; 3 new kinds), praise saturated at paper 13 (3 consecutive papers with no new praise group; 11 praise groups). Manipulation: 3-paper rule met after 3 CoRL papers with nothing new, too thin to call saturated. Locomotion: 2 papers, stopped. World models and datasets: not run. 79% of tagged complaint rows were reasons to reject; rebuttal resolved 20% of rows with a public outcome. |

Caveats: one venue and one year; ratings may still change after rebuttal; ICLR 2026 and NeurIPS Datasets and Benchmarks were not needed because ICLR 2027 alone gave 60 eligible papers, so venue diversity is untested.

## Complaint digest (latest)

ICLR 2027, 50 papers on VLA and robot-learning evaluation: 20 calibration papers (205 issues, 2026-11-17) and 30 low-scored or withdrawn papers (102 consensus issues, 2026-11-19). Full list of kinds with counts: references/complaint-catalog.md; views by topic, venue and topic x venue with reject-reason and rebuttal shares: references/catalog-views.md.

- Share of all issues in the 20 calibration papers: (g) measurement design and validity 24%, (d) claims beyond the evidence 23%, (b) baselines and controls 13%, (o) clarity, reproducibility and technical errors 12%, (a) scope and insight 10%, (e) prior art 9%, (c) statistics 9%, (f) venue compliance 0%.
- Consensus issues (raised by 2 or more reviewers of the same paper): 57 in the 20 calibration papers, (d) 37%, (g) 26%, (a) 14%; 102 in the 30 saturation papers, (g) 23%, (d) 23%, (a) 13%, (e) 12%, (b) 12%, (c) 11%, (o) 8%, (f) 0%.
- Most frequent kinds in the 30 saturation papers: one model, benchmark or few tasks generalized (13 papers); the metric does not measure what it claims (11); the simplest baseline or control missing (8); incremental over named work (8); "so what" (6); sparse data carrying a strong claim (6).
- Kinds added on 2026-11-19: evaluation overlaps training or tuning; metric thresholds or rules chosen without sensitivity analysis; a component not isolated by an ablation; net benefit not shown (a gain that costs another capability); does not scale (manual review, hand-built rules); unfinished paper.
- Use for other topics or venue families only as a weak prior, and say so.

## Trend-scan notes

- 2026-11-17: OpenReview answered automated requests with a browser challenge in 10 of 10 automated runs. Check reachability with one fetch, then fall back to reviews the user attaches or to the digest above.
- 2026-11-19: from the user's own signed-in browser, api2.openreview.net answered JSON requests with no challenge (submission lists, and per-forum notes with the rating and review fields). An automated fetch without that browser is still expected to be blocked.
