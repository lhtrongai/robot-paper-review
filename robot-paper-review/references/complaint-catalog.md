# Reviewer complaint catalog

What real reviewers complain about, and what they praise, in robot learning papers, as one shared set of error groups and kinds. Use it in step 5 (checklist) and step 7 (ranking) of SKILL.md. Per-topic, per-venue and topic x venue counts, with the share treated as a reason to reject and the share resolved by rebuttal, are in catalog-views.md next to this file: read the view for the paper's topic and venue first, then this general catalog.

## Saturation status (2026-11-20)

| Topic | Complaints | Praise | Papers | Venues |
|---|---|---|---|---|
| Evaluation of VLA and robot-learning policies, benchmarks used for evaluation, robustness, measurement | saturated: 10-paper rule met on ICLR 2027 (30 papers) and again on 12 papers across ICLR 2025-2027, NeurIPS 2025-2026, CoRL 2023-2024 | saturated: no new praise group in 3 consecutive papers (13 papers) | 20 calibration + 30 + 13 | as listed |
| Manipulation methods (imitation learning, diffusion policies, VLA training) | thin: 3-paper rule met after only 3 CoRL papers, nothing new; treat as unsaturated | thin: same 3 papers | 3 | CoRL 2023-2024 |
| Locomotion, whole-body control, humanoids, RL, sim-to-real | not saturated: 2 papers coded | not saturated | 2 | ICLR 2027, TMLR |
| World and video models for robots | not run | not run | 0 | - |
| Datasets and benchmarks for robot learning | not run | not run | 0 | - |

For unsaturated topics use the evaluation catalog as a weak prior and say so in the review header.

Sources so far: ICLR 2027 reviews of 50 papers on VLA and robot-learning evaluation (20 calibration papers, 205 issues, 2026-11-17; 30 low-scored or withdrawn papers, 102 issues raised by at least two reviewers of the same paper, 2026-11-19); plus 18 papers across ICLR 2025-2027, NeurIPS 2025-2026, CoRL 2023-2024 and TMLR with severity, rebuttal and praise tags (2026-11-19 and 2026-11-20). One venue and one year: for other venues treat the shares as a weak prior.

Counts in brackets are the number of consensus issues (raised by 2 or more reviewers of the same paper) in the 30-paper saturation run. A kind with 0 still came up in the 20 calibration papers.

## (g) Measurement design and validity - 23% of consensus issues

- Two factors changed at once [3]: a perturbation or condition changes more than the factor it names (lighting with camera pose, material with salience, static versus runtime perturbation differing in duration and timing, a new task mixing missing skill with instruction following).
- No zero-strength or null control through the same code path [0].
- Instrument depends on what it measures [0]: states, tasks or features chosen using a reference model's outcomes or anomalous gains.
- Unequal budgets across conditions [1]: steps, wall-clock time, episodes, memory or parameter count.
- Floor or ceiling effects, single level [1]: success near zero or near 100% so the comparison cannot show anything; one severity level or one paraphrase.
- Mislabeled variable [0]: a "seed" that moves fixtures, a perturbation outside the benchmark's initialization range.
- The metric does not measure what the paper says [11, the most frequent kind]: labels or validators never checked against people; a probe that decodes information the policy may not use; a proxy (action divergence, predicted cost) never shown to track task success; an intervention never checked to preserve or change the intended fact; safety defined only by hand-written predicates.
- Evaluation overlaps training or tuning [4] (new): test demos or perturbation families shared with training; hyperparameters, layers or features selected on the evaluation tasks; gains measured on starts already examined.
- Redundant or overlapping metrics or axes reported as distinct dimensions (added 2026-11-19, multi-venue run): correlated signals or axes presented as separate capabilities.
- Metric thresholds, weights or exclusion rules chosen by hand without sensitivity analysis [3] (new): a 90th-percentile threshold, an asymmetric F1, rule sets that keep very different numbers of tasks.

## (d) Claims beyond the evidence - 23%

- One model, one benchmark, one simulator or a few tasks generalized [13, the second most frequent kind and present in 13 of 30 papers]: also a benchmark whose main experiments cover only part of its own tasks.
- Simulation only while the claims concern deployment, safety or real sensors [4]: including simulated tactile and deformable physics never checked against reality.
- A claimed consequence or downstream benefit that is never tested (added 2026-11-19, multi-venue run): the paper says the finding makes policies brittle, improves selection or helps deployment, but no experiment checks it.
- Claim true by definition, or evidence of the wrong kind [6]: scripted components standing in for the learned system; injected faults standing in for natural failures; a mechanistic reading that does not exclude other explanations; a metric read more strongly than its definition allows.

## (b) Baselines, controls and ablations - 12%

- The simplest baseline or control a reviewer thinks of first is missing [8]: a sham or random-direction control, a data-matched dataset without the filtering, simply recollecting demonstrations or editing the instruction, a human or geometric baseline, a policy already trained for the property being tested.
- The closest current method or benchmark is missing [2].
- Unfair comparison [1]: clean scores copied from other papers, controls not matched.
- A component is not isolated by an ablation [1] (new): two things change between the compared rows, so the gain cannot be attributed.

## (a) Scope, insight and practical value - 13%

- Shows the effect without explaining the mechanism [2].
- "So what" [6]: the procedure is not shown to change any decision, predict real-robot outcomes or beat what practitioners already do.
- Unrealistic premise or a framing that does not match the content [3]: a method that needs exact simulator state restore; risk types far from real use; a VLA framing around a domain-agnostic method.
- Net benefit not shown [1] (new): the fix improves the targeted metric while degrading another capability.
- Does not scale [1] (new): the pipeline depends on manual review or hand-built rules, so it is subjective and hard to apply to larger datasets.

## (e) Novelty and prior art - 12%

- The effect is already known or expected [4].
- Incremental over named work, or an assembly of existing components, without a matched comparison [8].

## (c) Statistics - 11%

- Single run, no seeds, no intervals, too few trials for the claimed difference [5].
- Rank flips inside the noise [0].
- Intervals that ignore selection error or clustering [0].
- Sparse cells or few data points carrying a strong conclusion [6]: 5 model points, 7 cells, cells with 2 successes at full weight.

## (o) Clarity, reproducibility and technical errors - 8%

- Reads like an internal log; undefined terms; experiments not connected to the main question [4].
- Abstract dense with numbers, notation used before definition [0].
- Missing parameters, protocols, code, checkpoints or per-episode results [2].
- Implausible or inconsistent numbers in tables [0].
- Unfinished paper [2] (new): empty result cells, experiments deferred to the camera-ready version, declared tracks never run.

## (f) Venue compliance - 0%

- Desk-reject items only (anonymity, page limit, links). No reviewer raised compliance in the 50 ICLR 2027 papers.
- A section the venue requires (for example a limitations section at CoRL or RSS) missing or inadequate (added 2026-11-19, from one CoRL 2023 paper, partly from score fields; treat as weak).

## Praise catalog

Only specific praise raised by 2 or more reviewers of the same paper. Counts are rows in the evaluation topic (13 papers) plus manipulation (3) and locomotion (2); see catalog-views.md for the split.

- Careful measurement or evaluation design: controls, accounting or protocol that isolates the effect.
- Informative findings or insight into mechanism: results reveal something non-obvious.
- Broad or consistent empirical evidence: many models, tasks or settings with the same trend.
- Real-robot evidence (the most frequent praise at CoRL).
- Thorough ablations or design studies of the key choices.
- Useful released assets or infrastructure: data, code, pipeline, benchmark.
- Realistic threat model or problem setting.
- Careful statistics or formal guarantees: seeds, intervals, calibrated or conformal bounds.
- Low cost or simple deployment: lightweight, no retraining of the policy.
- A well-motivated component that solves a concrete technical difficulty of prior pipelines.
- Downstream usefulness demonstrated: the method or measurement helps an actual use (failure detection, data selection, control).

In the coded papers, accepted and rejected papers drew about the same number of praise rows (about 2 per paper), and no meta-review was coded as saying that a strength outweighed a serious complaint. Praise predicts the strengths section of the reviews, not the decision.

## How to use it

1. Before writing weaknesses, walk every kind above and answer it with a location in the paper.
2. Start from catalog-views.md: the view for the paper's topic and venue, then the topic view, then this list. Kinds with a high reject-reason share and a low rebuttal-resolved share (one model or benchmark generalized; incremental over named work; effect already known) are the ones that decide outcomes.
3. When ranking, the kinds that reviewers agree on most often are: the metric does not measure what it claims; one model or benchmark generalized; the simplest baseline or control missing; incremental over named work; "so what"; sparse data carrying a strong claim.
4. A new kind of complaint that fits none of the above is worth noting in the review output, so the catalog can grow.
