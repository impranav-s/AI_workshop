# October 26 workshop: proposed teaching plan

The revised workshop teaches one complete research workflow and then shows how to scale it. Participants first see a project with its paper, data, scripts, and build instructions. They follow a small change through planning, editing, review, and verification. The same task becomes the example for parallel agents, ownership, worktrees, persistent issues, and an orchestrator that keeps the research goals in view.

The deck has 29 teaching slides and 14 reference slides. It preserves Madrid, the default blue palette, the original dinosaur-builder image, the Git workflow and branch diagrams, and the merge-conflict illustration. The proposed change is substantial in sequence and emphasis, while the recognizable presentation style remains.

## Assumptions and decisions

This version assumes mixed experience and a demonstration-led session with one optional paired exercise. Those are proposals, not confirmed audience facts. If the audience is already comfortable with Git, shorten slides 8–11 and spend the recovered time on a visible two-session orchestration demonstration. If participants are mostly new, use the prepared diff for the exercise and avoid remote-control setup.

The original repository already implements a clustered-standard-error extension. Reusing “add clustered SE” as an untouched live task would be misleading. The revised demo instead traces an existing paper table to its generator and corrects the Quick Start. This is modest enough to inspect in fifteen minutes, and it connects code, writing, and reproducibility. The substantive clustered-SE research exercise is retained as an optional audit on slide 41, with its existing tables and figures in the source bundle. For a more substantive research demo, Tomas could use that audit or choose a familiar manuscript/table audit in advance; it should have an existing expected answer and take the same time slot. Do not improvise a new simulation during this session.

The Command Center appears only as a generic diagram. An actual dashboard screenshot or live screen remains an instructor decision requiring a separate privacy review and approval. The distributed workflow can be taught with labeled sessions and a shared task board even without that screen.

## Run of show

| Time | Slides | Instructor action and participant outcome |
|---|---|---|
| 0–7 | 1–4 | State the outcome: a task that can be reviewed. Keep the dinosaur-builder joke to one minute. Clarify what saved Git history can and cannot recover. |
| 7–18 | 5–7 | Open the actual project. Read the README, preview the paper/slides, locate a script, and show a diff. Explain the browser/partner fallback; do not install software in the room. |
| 18–31 | 8–11 | Explain repository, commit, branch, and remote. Walk the Git diagram. Use the example issue to show a goal, scope, owner, and acceptance criteria. Show why a PR gives a collaborator a reviewable proposal. |
| 31–43 | 12–17 | Spend two minutes on model/harness/interface. Compare the ten features in four groups. Use instructions, a reusable skill, and plan-to-edit as the concrete examples. Mention remote control and advisor briefly; keep them optional. |
| 43–58 | 18–19 | Run the bounded demonstration described below. Finish with the diff, checks actually performed, and an independent review prompt. Use a prepared issue/PR example to explain sharing and closeout. |
| 58–68 | 20 | Give two minutes to define acceptance criteria, four to edit or inspect, three to verify one claim, and one to report a decision. Pair people who lack an authenticated agent. |
| 68–82 | 21–28 | Introduce the human engagement ladder, then keep the task board visible. Show one writer and one read-only checker. Explain worktrees, the orchestrator, generic multi-machine routing, scarce allowance, and verified closeout. |
| 82–90 | 29 | Ask what participants would delegate in their own projects and what evidence they would require. Take questions and name one small next task. |

The durations sum to 90 minutes. Slides 30–43 are reference material and are not part of the timed presentation.

## Modular timing if participants need more hands-on time

For a 20-minute research exercise, use 0–7 for the goal, 7–15 for the workbench, 15–25 for Git/review, 25–35 for the comparison, 35–48 for the live demonstration, 48–68 for the exercise, 68–82 for orchestration, and 82–90 for questions. Keep the same materials and cut explanation time rather than adding content. Use the robustness audit on slide 41 for experienced participants, or the prepared README diff for beginners. The instructor can also use all 20 minutes for a guided demonstration if participants will mainly watch.

## Fifteen-minute demo script

1. **Minutes 0–3: orient.** Open `tex/paper/paper.tex`, locate `tables/summary_statistics.tex`, and trace it to `scripts/analysis.py` and the `update-outputs` target. Use existing outputs; make no new empirical claim. Then show the original Quick Start and the issue-style task brief.
2. **Minutes 3–6: plan.** In one authenticated provider, ask for a read-only diagnosis of the README and Makefile. Compare the proposed scope with the brief. Show how project instructions influence the plan. Point to the equivalent entry point in the other provider; do not run two long implementations sequentially.
3. **Minutes 6–10: edit.** Permit a README-only change in a prepared isolated copy. Inspect the resulting diff in VS Code. Ask the agent to distinguish commands it ran from commands it merely read. The proposed deck/build revision is separate from this small classroom task.
4. **Minutes 10–13: review.** Give a fresh read-only session the brief and diff. Ask it to identify inaccurate setup claims, missing dependencies, and commands that trigger extra work. Compare its findings with the source files.
5. **Minutes 13–15: hand back.** State whether the change is ready. Show a prepared PR example linked to the issue and explain what would need to be verified after integration. Classroom sharing follows the instructor's permissions; this preparation task created no issue, PR, push, or published artifact.

Keep `demo/README.before.md`, `demo/README.after.md`, and `demo/README.patch` open as a fallback. The deliberately small example only changes the prerequisite/build guidance and remains README-only. It does not rely on the new `slides-only` target. The full workshop revision has a separate source diff.

## Orchestration demonstration

At minute 68, reuse the task board on slide 22. A planner holds the agreed goal; Claude Code A writes the documentation; Codex B checks the Makefile read-only; reviewer C waits for the candidate diff. These labels illustrate distinct roles, not provider rankings. Show the working folder beside each session label. Interrupt or narrow a task once so participants see control rather than a wall of autonomous activity.

Explain that the personal assistant or orchestrator keeps project priorities and decisions outside the implementation-heavy chat. An issue is a persistent record that collaborators can inspect; a new session must still be told to read it. Give each task an input version, a location to run, an output destination, a budget, and a stop condition. Worktrees protect concurrent file edits, while shared external services still require coordination.

For the multi-machine example, use the generic diagram on slide 26. Demonstrate routing and input/output management verbally unless an approved screen is ready. Remote control is a separately rehearsed optional feature; it is not needed to explain orchestration.

## Where the structure is still vulnerable

- **Feature overload:** ten features can become a catalog. Spend most comparison time on instructions, skills, and planning. Let the other rows answer practical questions in the demo; keep exact version details in the source notes.
- **Too many orchestration concepts:** slides 21–28 average less than two minutes each. Treat them as one continuous example. If the audience needs a slower explanation, use slides 22, 25, 26, and 28 as the main anchors and reference the others briefly.
- **A documentation task may feel too small:** explicitly trace the paper table first. The learning objective is a dependable delegation/review loop. A chosen manuscript audit could replace the example, but it needs a known answer and rehearsal.
- **Setup can consume the session:** authenticate beforehand. Do not make paid access, MCP, remote control, or both providers prerequisites. Use the paired review fallback immediately if setup stalls.
- **A live dashboard can distract:** keep the private Command Center demonstration under three minutes and explain the task, ownership, resources, and output paths. Avoid touring every control.
- **Git is not universal undo:** Git history protects recorded files, not messages, permissions, or all external effects. The revised humor retains the useful metaphor without suggesting otherwise.

If the live demo is five minutes late, switch to the prepared diff, shorten the exercise to a five-minute paired review, and retain the final eight minutes for questions. Do not borrow time by racing through the orchestration explanation.

## Rehearsal checklist

Prepare one authenticated session per provider and verify the exact available commands. Open the project, original README, prepared diff, paper table, and Makefile. Use permitted teaching files. Check that an independent reviewer can read the candidate change. Confirm that the correct working directory is visible. Build the slides with `make slides-only`, open the PDF, and test the two internal navigation links. Optional remote-control/advisor demonstrations require their own setup check and sufficient allowance.

The artifact build and visual inspection are complete in this review package. The full research pipeline and a live multi-provider classroom run were not executed for this revision. Those are distinct checks and should not be inferred from a clean slide build.
