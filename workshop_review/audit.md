# Source inventory and editorial audit

## Baseline and preservation

The actual `tlarroucau/AI_workshop` repository was inspected on connected Fox and compared read-only through the existing Kyubi route. Both held commit `303c8213509c3a19ac8b27a9db618dfd893f2d8a`, with identical workshop source and PDF hashes. The source checkout had one tracked modification, `tex/slides/workshop_slides.pdf`, and one untracked file, `CLAUDE.md`. Neither was changed. Work took place in a separate output copy.

The original `workshop_slides.tex` has 2,000 lines, 47 active frames, and a 50-page local PDF because one slide uses four overlays. It uses 11pt, 16:9 Beamer, Madrid, the default blue palette, graphicx/booktabs/hyperref/TikZ, and the twemojis package. The final deck keeps the typography/theme and selected diagrams; twemojis is no longer needed.

The asset inventory included `Symbiosis.png`, `merge_conflict.png`, a repository screenshot, and existing analysis plots in PNG/PDF. The final deck uses the dinosaur-builder and merge-conflict images. The supplied source bundle includes those two required raster assets and the pre-existing paper tables/figures for the optional research exercise. No Command Center file or screenshot was opened or copied.

Build instructions were read in `Makefile`, `README.md`, `AGENTS.md`, and `.github/copilot-instructions.md`. The global and shared `academic-draft-editing`, `econ-write` (including presentation guidance), `humanizer`, and PDF guidance were read. The repository's named vendored PDF skill path is absent; the available shared PDF skill and the session PDF skill supplied the applicable guidance. Beamer was retained throughout.

`make slides` depends on `update-outputs`, which runs analysis. The new `make slides-only` target avoids that dependency and compiles the source twice with `-halt-on-error`. No analysis or simulation was run. The full analysis pipeline remains outside this revision's validation scope.

## Claims and structural problems addressed

| Original material | Assessment and revision |
|---|---|
| “Undo any mistake” / Git as a universal safety fence | Too broad. The revised joke and teaching point distinguish recorded file recovery from external actions and unsaved work. |
| Agents “powerful, fast, but chaotic”; repeated dinosaur sizes | An unhelpful capability claim. Keep one builder image and teach scope, tools, permissions, and evidence. The actual source did not contain the literal “stupid model” phrase. |
| Agent tools mostly introduced as a coding catalog | Reframe VS Code around papers, notes, LaTeX, Git, reading, writing, and project management. |
| Decorative section-divider slides and long extension lists | Costly in a 90-minute workshop. Replace with a timed narrative and move practical commands to reference slides. |
| `AGENTS.md` “only read on demand” | Not a portable description across current tools. Replace with provider-specific instructions and source qualifications. |
| “Copilot is now free” and education upgrades as universal prerequisites | Access, quota, and billing differ. Require only one authenticated supported agent for the optional local agent exercise. |
| MCP presented as mandatory setup and a token recipe | Remove from the critical path. The exercise works without MCP; permissions and connected services are deliberate choices. |
| “Enables collaboration without conflicts” | Misstates Git. Retain branch/conflict teaching and explain ownership plus review. |
| `.gitignore` means “never commit,” one per root, and blanket `*.png`/`*.pdf` ignores | Correct already-tracked-file behavior and subdirectory scope. Included assets remain needed for builds. |
| Local model workflow guarantees “complete privacy” and necessarily lower performance | Both are unsupported blanket statements. Explain local execution versus inference and inspect the full configuration. |
| Clustered-SE live task | Already represented by repository history and implementation. Use a traceable table/build documentation task for mechanics and retain the richer robustness audit as an optional reference exercise. |
| “From idea to merged code in minutes” | Implies success independent of verification. Budget the steps and provide a prepared diff fallback. |
| Overleaf “optimum” diagram | The original rendered slide cropped the lower workflow rules. Consolidate into a compact synchronization rule and account-dependent integration note. |
| Makefile example | Uses options not represented by the actual script and implies a build guarantees reproducibility. Replace with real targets and verification. |
| README ASU-branded-slide claim | Contradicts current default-blue Beamer source after the branding revert. Correct README; retain existing research figure colors. |
| “Entire workshop created with one prompt” | Unverified provenance slogan. Remove from the revised instructional path. |

## Deliberate omissions and remaining choices

Long tool-shopping lists, personal-website creation, detailed Copilot dropdown instructions, and complementary-product tours are omitted from the 90-minute path. The original source is preserved alongside the review diff so these can be recovered. These are scope decisions, not claims that the tools lack those features.

Audience experience, desired hands-on intensity, and the exact private dashboard screen remain instructor choices. The delivered proposal uses mixed-experience, demonstration-led assumptions and a generic dashboard illustration. Official feature support does not prove that each installed classroom client exposes the same interface. The source notes separate documented support from features that still need rehearsal.

No push, PR, issue, email, sharing change, research simulation, or alteration to an unrelated project was performed.
