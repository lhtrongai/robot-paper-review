# Reviewer complaint catalog

What real reviewers complain about, and what they praise, in robot learning papers, as one shared set of error groups and kinds. Official reviewer criteria of RSS, CoRL, ICRA, IROS and RA-L, mapped onto the same groups, are in venue-review-criteria.md. Use it in step 5 (checklist) and step 7 (ranking) of SKILL.md. Per-topic, per-venue and topic x venue counts, with the share treated as a reason to reject and the share resolved by rebuttal, are in catalog-views.md next to this file: read the view for the paper's topic and venue first, then this general catalog.

## Saturation status (2026-11-20)

Rule (fixed before reading reviews): a topic's complaints are saturated when the last 10 coded papers added no new complaint group and at most 2 new kinds; praise is saturated when the last 10 coded papers added no new praise group; cap 40 papers.

| Topic | Complaints | Praise | Papers | Venues |
|---|---|---|---|---|
| Evaluation of VLA and robot-learning policies, benchmarks used for evaluation, robustness, measurement | saturated (rule met on ICLR 2027 at 30 papers, and again at paper 12 across venues) | saturated at paper 20 | 20 calibration + 30 + 20 | ICLR 2025-2027, NeurIPS 2025-2026, CoRL 2023-2024 |
| Manipulation methods (imitation learning, diffusion and flow policies, VLA training) | saturated at paper 10 | saturated at paper 13 | 13 | ICLR 2025-2027, NeurIPS 2024-2025, CoRL 2023, TMLR |
| Locomotion, whole-body control, humanoids, RL, sim-to-real | saturated at paper 10 | saturated at paper 20 | 20 | ICLR 2025-2027, NeurIPS 2025-2026, CoRL 2023-2024, TMLR |
| CoRL venue sample (accepted CoRL 2023-2024 papers, all topics) | saturated at paper 10 | saturated at paper 19 | 19 | CoRL 2023-2024 (accepted papers only) |
| World and video models for robots | not run | not run | 0 | - |
| Datasets and benchmarks for robot learning | not run | not run | 0 | - |

For unsaturated topics use the evaluation catalog as a weak prior and say so in the review header.

Sources so far: ICLR 2027 reviews of 50 papers on VLA and robot-learning evaluation (20 calibration papers, 205 issues, 2026-11-17; 30 low-scored or withdrawn papers, 102 issues raised by at least two reviewers of the same paper, 2026-11-19); plus 72 papers across ICLR 2025-2027, NeurIPS 2024-2026, CoRL 2023-2024 and TMLR with severity, rebuttal and praise tags (evaluation 20, manipulation 13, locomotion 20, CoRL venue sample 19; 2026-11-19 and 2026-11-20). One venue and one year: for other venues treat the shares as a weak prior.

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
- Target leakage (added 2026-11-20, locomotion): inputs, instructions or conditioning derived from the outcome the model should predict.
- Metric thresholds, weights or exclusion rules chosen by hand without sensitivity analysis [3] (new): a 90th-percentile threshold, an asymmetric F1, rule sets that keep very different numbers of tasks.

## (d) Claims beyond the evidence - 23%

- One model, one benchmark, one simulator or a few tasks generalized [13, the second most frequent kind and present in 13 of 30 papers]: also a benchmark whose main experiments cover only part of its own tasks.
- Simulation only while the claims concern deployment, safety or real sensors [4]: including simulated tactile and deformable physics never checked against reality.
- A claimed consequence or downstream benefit that is never tested (added 2026-11-19, multi-venue run): the paper says the finding makes policies brittle, improves selection or helps deployment, but no experiment checks it.
- A claim contradicted by the paper's own results (added 2026-11-20, CoRL).
- Claim true by definition, or evidence of the wrong kind [6]: scripted components standing in for the learned system; injected faults standing in for natural failures; a mechanistic reading that does not exclude other explanations; a metric read more strongly than its definition allows.

## (b) Baselines, controls and ablations - 12%

- The simplest baseline or control a reviewer thinks of first is missing [8]: a sham or random-direction control, a data-matched dataset without the filtering, simply recollecting demonstrations or editing the instruction, a human or geometric baseline, a policy already trained for the property being tested.
- The closest current method or benchmark is missing [2].
- Unfair comparison [1]: clean scores copied from other papers, controls not matched.
- A component is not isolated by an ablation [1] (new): two things change between the compared rows, so the gain cannot be attributed.

## (a) Scope, insight and practical value - 13%

- Shows the effect without explaining the mechanism [2].
- "So what" [6]: the procedure is not shown to change any decision, predict real-robot outcomes or beat what practitioners already do.
- Failure modes or operating limits not analysed (added 2026-11-20, manipulation): no breakdown of when and why the method fails.
- Unrealistic premise or a framing that does not match the content [3]: a method that needs exact simulator state restore; risk types far from real use; a VLA framing around a domain-agnostic method.
- Net benefit not shown [1] (new): the fix improves the targeted metric while degrading another capability.
- Does not scale [1] (new): the pipeline depends on manual review or hand-built rules, so it is subjective and hard to apply to larger datasets.

## (e) Novelty and prior art - 12%

- The effect is already known or expected [4].
- Incremental over named work, or an assembly of existing components, without a matched comparison [8].
- Closely related prior work not cited or not positioned against (added 2026-11-20, manipulation).

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

- Out of the venue's scope (added 2026-11-20, CoRL): no learning component in a learning venue, or a pure systems paper.
- Desk-reject items only (anonymity, page limit, links). No reviewer raised compliance in the 50 ICLR 2027 papers.
- A section the venue requires (for example a limitations section at CoRL or RSS) missing or inadequate (added 2026-11-19, from one CoRL 2023 paper, partly from score fields; treat as weak).

## Praise catalog

Only specific praise raised by 2 or more reviewers of the same paper. Counts per topic and venue are in catalog-views.md. At CoRL the most frequent praise is real-robot evidence and a well-motivated component that fixes a real failure of prior pipelines.

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
- Clear conceptual framing that organizes the design space and motivates the experiments (added 2026-11-20, manipulation).
- Reproducibility detail: protocols, implementation details or supplement sufficient to reproduce (added 2026-11-20, locomotion).
- Honest scoping: negative results and limitations reported openly, claims kept within the evidence (added 2026-11-20, locomotion).
- A working end-to-end system: several hard components integrated so the whole pipeline runs (added 2026-11-20, CoRL).

In the 63 papers with tagged rows, the amount of praise does not predict the decision (about 2.5 praise rows per paper for accepted and for rejected or pending papers), and the number of complaints treated as reasons to reject separates them only weakly (2.6 per accepted paper against 2.8 for rejected or pending ones). What did show up only in accepted papers: 8 praise rows where the meta-review named a strength as outweighing the remaining complaints, namely broad evidence across many models or tasks, a released real-robot dataset or other asset, downstream usefulness shown, real-robot evidence, or a simple well-motivated component. Use complaint kinds and severity to predict the reviews, and treat any score prediction as a wide band.

A second grader (a different model) re-coded a random 20% of the evaluation and manipulation rows: agreement 94-100% per field (kind and praise group 100%, severity 94% with kappa 0.77, rebuttal 94% with kappa 0.92). Disagreements all ran one way: the first coders were slightly lenient (one reviewer plus a score field counted as two; reject reason given to points raised by positive reviewers; offset given for "accept despite limitations"). The reject-reason shares in catalog-views.md may therefore be a few points high.

## How to use it

1. Before writing weaknesses, walk every kind above and answer it with a location in the paper.
2. Start from catalog-views.md: the view for the paper's topic and venue, then the topic view, then this list. Kinds with a high reject-reason share and a low rebuttal-resolved share (one model or benchmark generalized; incremental over named work; effect already known) are the ones that decide outcomes.
3. When ranking, the kinds that reviewers agree on most often are: the metric does not measure what it claims; one model or benchmark generalized; the simplest baseline or control missing; incremental over named work; "so what"; sparse data carrying a strong claim.
4. A new kind of complaint that fits none of the above is worth noting in the review output, so the catalog can grow.
