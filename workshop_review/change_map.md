# Slide-by-slide change map

Original numbers refer to the 47 numbered Beamer frames, not the 50 PDF pages. Final slide numbers equal PDF page numbers.

| Final slide | Original frame | Change |
|---|---|---|
| 1. Git, GitHub, and VS Code | 1 | Fixed workshop date and updated subtitle. |
| 2. Why This Workshop? | 3 | Keep two-column motivation; replace absolute safety claims with a concrete learning objective. |
| 3. Our 90 Minutes | 2 | Replace table of contents with explicit time budget. |
| 4. The Symbiosis: Agents as Builders | 5 | Retain original illustration and metaphor without portraying models as inherently stupid or chaotic; absorb frame 4. |
| 5. VS Code: An Integrated Research Environment | 10 | Reframe editor around research; remove unsupported editor ranking. |
| 6. Reproducible Research Template | 7 | Correct actual raw/processed layout; combine materials frame 6. |
| 7. Workshop Prerequisites | 8 | Match README; remove mandatory Copilot/MCP and stale education promises. |
| 8. Git Core Concepts | 22 | Retain five Git concepts and small command example; clarify recorded snapshots. |
| 9. The Git Workflow | 23 | Retain original workflow diagram; improve scope of history. |
| 10. GitHub Issues: Shared Research Context | 33 | Use an actual repository documentation problem; durable context is explicitly retrieved, not automatic memory. |
| 11. GitHub Workflow: Pull Requests | 35 | Retain PR and branching diagram; replace race-to-merge demo cue. |
| 12. What Is Agentic AI? | 15 | Replace generic autonomy claims with operational loop. |
| 13. Model, Agent, and Interface | New | Separate model choice from product capabilities; official VS Code source. |
| 14. Claude Code and Codex: Context and Planning | New | Ten features grouped by use, with surface-specific qualifications and official sources. |
| 15. Claude Code and Codex: Output, Tools, Control | New | Ten features grouped by use, with surface-specific qualifications and official sources. |
| 16. Claude Code and Codex: Sessions and Remote Work | New | Ten features grouped by use, with surface-specific qualifications and official sources. |
| 17. Claude Code and Codex: Delegation and Review | New | Ten features grouped by use, with surface-specific qualifications and official sources. |
| 18. Live Demo: One Task, Visible Evidence | 39 | Replace already-implemented clustered-SE scenario; budget 15 minutes and a prepared fallback. |
| 19. A Prompt You Can Inspect | New | Concrete advisory-to-edit transition for either provider. |
| 20. Ten-Minute Exercise: Review a Change | New | Exercise has a no-installation paired fallback and explicit timing. |
| 21. You Choose the Level of Engagement | New | Human engagement ranges from question and design through exact implementation. |
| 22. Parallel Work Needs Distinct Ownership | New | Shared task board, visible sessions, dependency and ownership rules. |
| 23. One Machine: Clearly Labeled Sessions | New | Correct prior blanket CLI-discovery claim; no mandatory cross-provider application. |
| 24. Separate Worktrees for Separate Writers | New | Explain isolation and limits without overselling worktrees as a sandbox. |
| 25. The Orchestrator Keeps the Big Picture | New | Big-picture assistant separated from implementation context. |
| 26. Several Projects and Machines | New | Safe generic Command Center placeholder; no screenshots, addresses, private code, or connection details. |
| 27. Allocate Models and Attention by Task | New | Task fit, scarce subscription allowance, independent review; no ranking. |
| 28. Finish the Task, Then Verify Closeout | New | Verified closeout with explicit authorization boundary; issue closure alone is not proof. |
| 29. Next Steps and Questions | 43 | Combine next steps and questions; remove unverified one-prompt provenance slogan. |
| 30. Visualizing Branches | 26 | Retain original branch diagram. |
| 31. Essential Git Commands | 24 | Remove git add . and direct push-to-main as default teaching path. |
| 32. Worktree Commands: One Writer per Folder | New | Concrete safe worktree example. |
| 33. Git Best Practices | 27 | Avoid absolute never-commit-output rule; qualify sample data permissions. |
| 34. The .gitignore File | 28 | Correct ignore behavior and avoid ignoring all figures needed to compile. |
| 35. Resolving Merge Conflicts in VS Code | 30 | Keep merge-conflict screenshot and explanation; fit within slide. |
| 36. Useful VS Code Features | 12 | Consolidate long extension/shortcut lists; remove incorrect duplicate-line shortcut. |
| 37. MCP: Model Context Protocol | 37 | Correct optional protocol framing; remove token-pasting installation recipe. |
| 38. Data Privacy and Permissions | 19 | Remove complete-privacy and weaker-local-model blanket claims. |
| 39. Overleaf, Statistical Software, and VS Code | 40 | Consolidate oversized Overleaf diagram and broad unsupported integration claims. |
| 40. The Makefile Approach | 47 | Use actual targets, remove nonexistent command options and misleading reproducibility guarantee. |
| 41. Research Exercise: Audit the Robustness Check | 39 | Retain substantive clustered-SE work as an audit of the existing implementation, with optional hands-on variant. |
| 42. VS Code Session Discovery: Scope Matters | New | Official parent fact-check, including single-writer caveat. |
| 43. Resources | 44 | Add primary-source comparison documentation. |

## Material consolidated or removed from the teaching path

Original frame 4 is consolidated into the dinosaur-builder slide. Materials (6) join the project structure. Extension lists/workspace setup (11–13) become the research environment and reference features. Decorative dividers (9, 14, 20, 31, 36) are removed. Copilot-specific modes/context/custom-agent instructions (16–18) are replaced with the current cross-provider comparison. Git overview/branch strategy (21, 25) are covered by the retained concepts/diagrams. Common challenges (29) are distributed across worktrees, conflict review, and synchronization guidance. GitHub overview/boards (32, 34) join issues, PRs, and orchestration. MCP flow (38) is condensed. Overleaf diagram (41) joins reference integration guidance. The complementary-tools catalog (42) and unverified one-prompt claim (45) are omitted to protect the 90-minute scope. The original source remains in `original/` for review and recovery. Questions (46) join next steps.

`README.md` now matches the proposed prerequisites and distinguishes local exercises, slide-only builds, and full analysis builds. `Makefile` adds `slides-only` without changing analysis recipes. `comparison.tex` contains the four new editable comparison slides.
