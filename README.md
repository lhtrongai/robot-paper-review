# robot-paper-review

A skill for a blind pre-submission review of a robot learning or embodied AI paper, written the way reviewers at the target venue will read it. It covers VLA and robot foundation models, manipulation, humanoids, sim-to-real, benchmarks, and robustness or evaluation studies, at ML venues, robotics venues, journals and workshops.

What it does at run time:

- fetches the target venue's current rules, review form, score scale and AI policy, and records each URL with its fetch date;
- searches recent prior art, including the benchmark or method the community adopted most recently;
- applies a prior per venue family (ML conference, benchmark track, robot learning conference, broad robotics conference, journal, workshop);
- walks a checklist per error group, starting with the groups real reviewers raise most;
- outputs ranked weaknesses, the top 3 complaints reviewers are most likely to raise, questions for the authors, a score band, the cheapest fixes, and an audit of every source used.

## Files

- `SKILL.md`: the procedure. It holds no dated numbers, so it does not go stale when models or venues change.
- `CALIBRATION.md`: an append-only log of how well blind reviews predicted real public reviews, with the reviewer model and date of each round, plus the latest digest of recurring complaints. The skill reads it at the start of every run and warns when the current model or the date does not match.

## Install

- Claude apps: zip the folder and upload it as a custom skill.
- Claude Code: copy the folder to `~/.claude/skills/robot-paper-review/`.

## Use

Ask for a blind review of a paper and name the venue, year and track, for example: "Blind review of this paper for RSS 2027." Run it in a fresh chat with no memory and without the authors' notes, so the review sees only the paper. For a real submission, run it twice with different models and merge the results.

## Limits

Calibration so far covers one venue (ICLR 2027) and one topic (VLA evaluation and robustness), 20 papers. Other venue families are marked uncalibrated in the skill. Many robotics venues do not publish reviews, so those families can only be calibrated slowly, from the user's own submissions.

## License

MIT, see `LICENSE`.
