# Workshop revision: October 26, 2026

Implemented from the restored original author deck at `2ca6cca`, whose slide source matches `main` at `303c821`. The approved order is introduction, Git, GitHub, VS Code/harnesses, advanced topics, then closing. **40 slides and 40 PDF pages**, including title, questions, and the Makefile reference slide.

## What changed

- Removed five decorative dividers (original 9, 14, 20, 31, 36), the scripted demonstration (39), and the meta anecdote (45).
- Combined materials/structure (6+7) and next steps/resources (43+44). Flattened slide 4 overlays.
- Added worktrees after the original branching slides and one writing slide. Replaced the agreed harness/interface/orchestration slots; kept the original Madrid theme, typography, figures and most diagrams.
- Updated the date, setup/access guidance and selected outdated claims. The full Git/GitHub teaching sequence remains, with small factual corrections.
- Updated README prerequisites and build instructions. Research scripts, data, paper source, Makefile and user instruction files were not changed. Existing slide images are included for a reproducible checkout.

## Old-to-new slide map

| Original | New | Original title | Change |
|---|---|---|---|
| 1 | 1 | Git, GitHub, and VS Code | Retained; moved where needed |
| 2 | 2 | Workshop Overview | Retained; moved where needed |
| 3 | 3 | Why This Workshop? | Retained with small factual/setup edit |
| 4 | 4 | The "Jur-AI-ssic Park" Approach to Research | Retained; one page instead of four overlays |
| 5 | 5 | The Symbiosis: Agents as Builders | Retained with small factual/setup edit |
| 6 | 6 | Workshop Materials | Combined |
| 7 | 6 | Reproducible Research Template | Combined |
| 8 | 7 | Workshop Prerequisites | Retained with small factual/setup edit |
| 9 | — | Git, GitHub, and VS Code | Cut as approved |
| 10 | 23 | What is VS Code? | Retained with small factual/setup edit |
| 11 | 24 | Useful Extensions for Research & Productivity | Retained; moved where needed |
| 12 | 25 | Essential VS Code Features | Retained; moved where needed |
| 13 | 26 | VS Code Workspace Setup | Added one agent-panel bullet |
| 14 | — | Git, GitHub, and VS Code | Cut as approved |
| 15 | 27 | What is Agentic AI? | Retained introduction; human engagement hierarchy |
| 16 | 28 | VS Code Copilot Chat Modes | Replaced in approved slot |
| 17 | 29 | VS Code Custom Context & Skills | Targeted instructions/skills update |
| 18 | 30 | Custom Agents in VS Code | Replaced in approved slot |
| 19 | 31 | Data Privacy & Security Considerations | Retained with small factual/setup edit |
| 20 | — | Git, GitHub, and VS Code | Cut as approved |
| 21 | 8 | What is Git? | Retained with small factual/setup edit |
| 22 | 9 | Git Core Concepts | Retained with small factual/setup edit |
| 23 | 10 | The Git Workflow | Retained with small factual/setup edit |
| 24 | 11 | Essential Git Commands | Retained with small factual/setup edit |
| 25 | 12 | Branching Strategy | Retained; moved where needed |
| 26 | 13 | Visualizing Branches | Retained; moved where needed |
| 27 | 15 | Git Best Practices | Retained with small factual/setup edit |
| 28 | 16 | The .gitignore File | Retained with small factual/setup edit |
| 29 | 17 | Common Challenges & Solutions | Retained; moved where needed |
| 30 | 18 | Resolving Merge Conflicts in VS Code | Retained; moved where needed |
| 31 | — | Git, GitHub, and VS Code | Cut as approved |
| 32 | 19 | What is GitHub? | Retained with small factual/setup edit |
| 33 | 20 | GitHub Workflow: Issues | Retained; moved where needed |
| 34 | 21 | GitHub Project Boards | Retained; moved where needed |
| 35 | 22 | GitHub Workflow: Pull Requests | Retained; moved where needed |
| 36 | — | Git, GitHub, and VS Code | Cut as approved |
| 37 | 32 | MCP: Model Context Protocol | Retained with small factual/setup edit |
| 38 | 33 | How AI Tools Connect: The Big Picture | Replaced in approved slot |
| 39 | — | Live Demo: End-to-End Example | Cut as approved |
| 40 | 34 | Common Frictions in Academic Research | Retained with small factual/setup edit |
| 41 | 35 | Optimum Workflow: Overleaf + VS Code | Retained diagram/text; spacing repair |
| 42 | 36 | Complementary Research Tools | Retained; moved where needed |
| 43 | 38 | Next Steps | Combined |
| 44 | 38 | Resources | Combined |
| 45 | — | Behind the Scenes: Meta Moment | Cut as approved |
| 46 | 39 | Questions? | Retained; moved where needed |
| 47 | 40 | The Makefile Approach | Retained with small factual/setup edit |
| Added | 14 | Git Worktrees: Separate Folders for Parallel Work | Within Git, after original 26 |
| Added | 37 | Author Instructions: Write for the Paper's Reader | One writing slide |

## 90-minute run of show

| Minutes | Slides | Focus |
|---|---|---|
| 0–8 | 1–7 | Purpose, materials and setup |
| 8–28 | 8–18 | Git, branches, worktrees and conflicts |
| 28–43 | 19–22 | GitHub issues, boards and PRs |
| 43–65 | 23–31 | VS Code, harnesses, interfaces and skills |
| 65–80 | 32–38 | MCP, orchestration, Overleaf, writing and next steps |
| 80–90 | 39 | Questions |
| Reference | 40 | Makefile explanation as needed |

For a two-hour session, use the extra 30 minutes for audience questions and the author's existing tool demonstrations. No new exercise or revision-demo script was added.

## Assessment

The 40-slide limit is met, but 90 minutes still requires selective narration. The extension list (24), skills slide (29), and Makefile reference (40) are material to point to rather than read line by line. Setup and authentication should happen before the session. The GitHub slides retain the author's original demonstration cues; several full live demonstrations would need the two-hour option.

The original Git/GitHub substance and recognizable style are preserved. Current tool claims distinguish harnesses, models and interfaces; they do not rank models. Ten detailed comparison points and installation sources live in the companion source notes rather than ten new slides.

One inherited point merits discussion during author review: the original backup slide (now 17) permits Dropbox backup of a live repository. Simultaneous synchronization of Git metadata can interfere with staged state. The existing caution about coordination is retained; no backup configuration was changed.

## Validation

- `make clean && make all` passed in an isolated copy using the existing sample data. No research simulation was introduced.
- The final slide source compiled successfully with 40 pages and no overfull box warnings or undefined references.
- All 40 pages were rendered and visually inspected. The Overleaf diagram's original vertical overflow and a label overlap were repaired without changing its content.
- A separate extracted source-bundle build passed. All 40 rendered pages matched the delivered PDF, with no overflow warnings or undefined references.
- Command Center appears only as a generic description. No private code, screenshots, research results, credentials or machine details are included.

## Review files

- `frame_changes.patch`: focused, slide-by-slide text changes, avoiding noise from reordering.
- `source_diff.patch`: standard source/README diff against the restored original baseline.
- `source_notes.md`: current official references, comparison details and optional skill installation guidance.
