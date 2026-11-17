# Calibration log

Append-only. Each row records how well blind reviews predicted what real reviewers raised, for one venue family, one period and one reviewer model. Numbers are only meaningful for the model and period in their row: when the model running the skill is different, or the newest row for the venue family is older than 12 months, treat every number here as a hint and say so in the review header.

How a round is measured: real reviews are coded into issues before any prediction is read; each issue is matched against the blind review's top 3 and full weakness list (yes, partial, no); precision is the share of the review's weaknesses that match a real issue; a second grader (another model or a person) re-checks at least 20% of the papers. Only aggregate numbers are kept here, never per-paper review text.

Error groups: (a) scope and insight, (b) baselines, controls and ablations, (c) statistics, (d) claims beyond the evidence, (e) novelty and prior art, (f) venue compliance, (g) measurement design and validity, (o) clarity, reproducibility and technical errors.

## Rounds

| Date | Venue family, venue | Papers, topic | Reviewer model | What was compared | Results |
|---|---|---|---|---|---|
| 2026-11-16 | ML conferences, ICLR 2027 | 10, VLA evaluation and robustness | not recorded | earlier rubric prompt alone | Full-list recall 66%, top-3 recall 34%; issues raised by 2 or more reviewers 84% and 63%. Lowest recall: (g) 56% on 24 issues, (b) 56% on 9. Statistics ranked too high; venue compliance raised on 5 papers where no reviewer raised it. |
| 2026-11-17 | ML conferences, ICLR 2027 | 10 new papers, same topic | Claude Opus 5.5 (graders: the same model on all papers, a Sonnet model on 2, kappa 0.78 on precision calls) | this skill vs the earlier prompt, both blind | Top-3 recall 35% vs 30% (skill better on 8 of 10 papers); precision 56% vs 47%; full-list recall 66% vs 60% by issue matching but 43% vs 46% by item matching, so no reliable difference; consensus issues 88% vs 85%; prior art (e) 94% vs 67% on 9 issues; (b) unchanged at 56%. Caveats: the skill had the larger search budget; its review-trend step failed in 10 of 10 runs. |

## Complaint digest (latest)

ICLR 2027, 20 papers on VLA evaluation and robustness, 205 issues coded from real reviews (2026-11-16 and 2026-11-17):

- Share of all issues: (g) measurement design and validity 24%, (d) claims beyond the evidence 23%, (b) baselines and controls 13%, (o) clarity, reproducibility and technical errors 12%, (a) scope and insight 10%, (e) prior art 9%, (c) statistics 9%, (f) venue compliance 0%.
- Issues raised by 2 or more reviewers of the same paper (57): (d) 37%, mostly one model, benchmark or simulator generalized; (g) 26%; (a) 14%.
- Use for other topics or venue families only as a weak prior, and say so.

## Trend-scan notes

- 2026-11-17: OpenReview answered automated requests with a browser challenge in 10 of 10 agent runs. Check reachability with one fetch, then fall back to reviews the user attaches or to the digest above.
