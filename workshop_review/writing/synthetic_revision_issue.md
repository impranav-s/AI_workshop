# Synthetic local issue draft: align the continuation exhibit

This is an invented teaching example. It is not a Refine comment, a real research finding, or a hosted issue.

## Comment to investigate

The prose describes persistence for the entering cohort, while the exhibit appears to condition on enrollment. Establish the intended population and align the equation, calculation, caption, and interpretation.

## Author decision

Choose the target population and persistence horizon. Decide which scientific claim the exhibit should support. No agent should settle this by silently changing the denominator.

## Work and dependencies

| Task | Owner label | Files / output | Depends on |
|---|---|---|---|
| A: define estimand and timing | Researcher + theory agent | Local task brief and derivation | Author decision |
| B: independent probability check | Reviewer | Separate small-case calculation | A |
| C: align implementation | Implementation agent | scripts/exhibit.py in worktree C | A; reconcile B |
| D: generate exhibit | Exhibit agent | PDF figure and LaTeX table from one output version | B and C |
| E: integrate argument | Draft integrator | tex/model.tex, caption, results paragraph | D and approved interpretation |
| F: review closeout | Independent reviewer + researcher | Diff, rendered draft, comment-response record | E |

B and C can proceed in parallel after A. Two writers should not edit the same files concurrently. A draft editor can flag language independently, but final interpretive edits wait for the validated exhibit.

## Acceptance criteria

The target population and horizon are explicit. The derivation and implementation agree on conditional versus unconditional probabilities. A small-case check passes. Counts, units, uncertainty labels, and table/figure entries agree. Missing results remain marked. The rendered draft fits and makes only the approved claim.

## Integration

Prepare local PR descriptions linked to this issue draft, including checks performed and remaining limits. Inspect the integrated version before marking the comment resolved. No external issue, assignment, PR, or closeout action has occurred.

