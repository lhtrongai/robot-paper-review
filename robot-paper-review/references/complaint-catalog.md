# Reviewer complaint catalog

What real reviewers complain about in robot learning evaluation, benchmark, robustness and measurement papers, as a list of error groups and the kinds of error inside each group. Use it in step 5 (checklist) and step 7 (ranking) of SKILL.md. Built from public reviews; see CALIBRATION.md for how it was built and how far it has saturated.

Sources so far: ICLR 2027 reviews of 50 papers on VLA and robot-learning evaluation (20 calibration papers, 205 issues, 2026-11-17; 30 low-scored or withdrawn papers, 102 issues raised by at least two reviewers of the same paper, 2026-11-19). One venue and one year: for other venues treat the shares as a weak prior.

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
- Metric thresholds, weights or exclusion rules chosen by hand without sensitivity analysis [3] (new): a 90th-percentile threshold, an asymmetric F1, rule sets that keep very different numbers of tasks.

## (d) Claims beyond the evidence - 23%

- One model, one benchmark, one simulator or a few tasks generalized [13, the second most frequent kind and present in 13 of 30 papers]: also a benchmark whose main experiments cover only part of its own tasks.
- Simulation only while the claims concern deployment, safety or real sensors [4]: including simulated tactile and deformable physics never checked against reality.
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

- Desk-reject items only (anonymity, page limit, links). No reviewer raised compliance in 50 papers.

## How to use it

1. Before writing weaknesses, walk every kind above and answer it with a location in the paper.
2. When ranking, the kinds that reviewers agree on most often are: the metric does not measure what it claims; one model or benchmark generalized; the simplest baseline or control missing; incremental over named work; "so what"; sparse data carrying a strong claim.
3. A new kind of complaint that fits none of the above is worth noting in the review output, so the catalog can grow.
