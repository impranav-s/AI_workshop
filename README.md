# Research Project Template: Git, GitHub, and Agentic AI Workshop

> **Local review status:** This is the first revised deck. The stronger scientific example is still being selected; the README exercise is superseded as the proposed centerpiece. See [implementation status](workshop_review/IMPLEMENTATION_STATUS.md).

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This repository serves as a **template for reproducible research projects** created by **Tomas Larroucau** and accompanies the workshop: *"Git, GitHub, and VS Code: Agentic AI for Research, from One Task to Orchestration."*

## 🎯 Purpose

This template demonstrates best practices for:
- **Version control** with Git and GitHub
- **Reproducible data analysis** workflows
- **Integration of research agents** (Claude Code, Codex, and GitHub Copilot)
- **Collaborative research** through issues, pull requests, and project boards
- **Automated workflows** for analysis and document compilation

## 📁 Repository Structure

```
AI_workshop/
├── AGENTS.md                      # Instructions for AI coding agents
├── Makefile                       # Automation workflow
├── README.md                      # This file
│
├── .github/                       # GitHub-specific files
│   ├── copilot-instructions.md   # Copilot workspace configuration
│   ├── prompts/                  # Reusable prompt files
│   └── skills/                   # Agent skills (e.g., YouTube transcript fetcher)
│
├── data/                          # Raw and processed data
│   ├── raw/                      # Original data files (never modify!)
│   │   ├── generate_data.py      # Data generation script
│   │   └── sample_data.csv       # Sample dataset
│   └── processed/                # Cleaned/transformed data (gitignored)
│
├── scripts/                       # Analysis and processing scripts
│   ├── analysis.py               # Main analysis pipeline
│   ├── utils.py                  # Helper functions
│   └── requirements.txt          # Python dependencies
│
├── output/                        # Generated outputs (gitignored, rebuilt via make)
│   ├── figures/                  # Plots and visualizations
│   │   ├── distributions.png
│   │   ├── outcome_by_treatment.png
│   │   └── scatter_income_outcome.png
│   └── tables/                   # LaTeX-formatted tables
│       ├── balance_table.tex
│       ├── regression_results.tex
│       └── summary_statistics.tex
│
└── tex/                           # LaTeX documents
    ├── paper/                    # Research paper
    │   ├── paper.tex
    │   └── references.bib
    └── slides/                   # Presentation slides
        └── workshop_slides.tex
```

**Key principle:** Everything in `output/` is regenerated from scripts - never edit manually!

## 🚀 Quick Start

### Monday, October 26, 2026: 90-minute workshop

The session demonstrates one reviewable research task, compares Claude Code and Codex, and shows how to coordinate parallel work. The main deck ends at slide 29; the remaining slides are reference material.

### Workshop Prerequisites

To follow the demonstration, bring a browser and the workshop materials. For the local exercise, install **VS Code** and **Git**, and open a copy of this repository. The exercise edits the README; it does not require Python, LaTeX, or an MCP server. If setup is incomplete, work with a partner or review the prepared diff.

To run an agent yourself, install and sign in to **one** supported agent. Claude Code and Codex are demonstrated; both subscriptions are not required. Check your account's current access and allowance before the workshop. Native provider subscriptions, Copilot access, and API billing are separate routes. A GitHub account is needed for hosted issues and pull requests, but the local exercise stops before sharing.

Useful extensions include LaTeX Workshop, Python/Jupyter, GitHub Pull Requests and Issues, and your chosen agent's extension. Install only what your project needs. MCP setup is optional for this session.

### Get the project

```bash
git clone https://github.com/tlarroucau/AI_workshop.git
cd AI_workshop
git status
```

Open the folder in VS Code and read `README.md`, `AGENTS.md`, and `Makefile`. The October 26 revision is a local review copy until the author chooses to publish it; cloning the public repository does not automatically include these proposed edits.

### Build only the workshop slides

In this revised source bundle, a LaTeX distribution with Beamer and TikZ is sufficient to build the deck. With Make installed:

```bash
make slides-only
```

Without Make:

```bash
cd tex/slides
pdflatex -halt-on-error -interaction=nonstopmode workshop_slides.tex
pdflatex -halt-on-error -interaction=nonstopmode workshop_slides.tex
```

The result is `tex/slides/workshop_slides.pdf`. `comparison.tex` and the included `figures/` assets must remain beside the main source.

### Run the full research workflow (optional)

The analysis uses Python and the packages in `scripts/requirements.txt`. Full document builds also need LaTeX and Make. Use an isolated Python environment; the dependencies are lower bounds rather than a locked reproducible environment.

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r scripts/requirements.txt
make check-env PYTHON=python
make all PYTHON=python
```

On Windows, activate the environment with `.venv\Scripts\activate` and use a shell with Make available, or run the documented steps individually. Choose a currently supported Python version compatible with your installed packages; the full pipeline has not been revalidated as part of this slide-only revision.

`make all`, `make paper`, and `make slides` run analysis dependencies and regenerate outputs. `make slides-only` compiles the deck from existing assets. Inspect the Makefile before running a target. `make clean` removes generated data, figures, tables, and PDFs.

## 🔧 Makefile Targets

| Target | Description |
|--------|-------------|
| `make data` | Check for sample data; generate it only if missing |
| `make analysis` | Run statistical analysis |
| `make figures` | Generate plots and visualizations |
| `make tables` | Create LaTeX tables |
| `make update-outputs` | Copy analysis outputs to paper/slides directories |
| `make paper` | Compile research paper PDF |
| `make slides` | Run analysis, copy outputs, and compile slides |
| `make slides-only` | Compile the Beamer deck from existing assets |
| `make all` | Run complete pipeline |
| `make clean` | Remove generated files |

## 📊 Workflow Example

```bash
# 1. Process data
make data

# 2. Run analysis and update outputs
make update-outputs

# 3. Compile paper and slides
make paper slides
```

## 🤖 Working with AI Agents

This repository includes instructions for AI coding agents:

- **`.github/copilot-instructions.md`** - GitHub Copilot workspace instructions
- **`AGENTS.md`** - General AI agent guidelines for this project
- **`CLAUDE.md`** - Imports shared guidance for Claude Code when present

The workshop comparison also illustrates provider-specific skill locations. Product features depend on the installed version, interface, account, and organization settings. See the official sources in `workshop_review/source_notes.md`.

These files help AI assistants understand:
- Project structure and conventions
- Code style and patterns
- Common workflows and tasks
- Domain-specific context

## 🎓 Workshop Structure

- **0–7 minutes:** Research workflow and the goal for the session
- **7–18:** VS Code as a research environment; inspect the project template
- **18–31:** Git, shared issues, pull requests, and review
- **31–43:** Ten practical Claude Code/Codex comparisons
- **43–58:** Demonstrate a bounded task, inspect its diff, and verify its claims
- **58–68:** Short exercise or paired review
- **68–82:** Orchestration, worktrees, resources, and verified closeout
- **82–90:** Questions and a concrete next step

The comparison distinguishes the model, agent harness, and interface. Durable project instructions and reusable skills support reading, writing, analysis, and review. Parallel agents need clear ownership, isolated writing directories, and a shared record of decisions. The Command Center example is a generic private-demo illustration; the bundle contains no dashboard code or screenshots.

## 📝 Using This Template

1. **Click "Use this template"** on GitHub to create your own repository
2. **Update** `README.md` with your project details
3. **Replace** sample data with your actual data
4. **Modify** analysis scripts for your research questions
5. **Customize** LaTeX templates for your paper/presentation

## 🤝 Contributing

This is a teaching template. Contributions welcome via:
- **Issues:** Report bugs or suggest improvements
- **Pull Requests:** Submit enhancements
- **Discussions:** Share feedback or use cases

## 📚 Additional Resources

- [Workshop Slides](tex/slides/workshop_slides.pdf) (after compilation)
- [Git Documentation](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com/)
- [VS Code Documentation](https://code.visualstudio.com/docs)
- [GitHub Copilot Docs](https://docs.github.com/en/copilot)

## 📄 License

MIT License - Feel free to use this template for your research projects.

## 👤 Author

Template created by Tomas Larroucau for ASU's AI Strategic Plan workshop series.

## 🎨 Presentation Style

The workshop slides use Beamer's **Madrid** theme and default blue palette, following the repository's current slide source. Some existing research figures retain the ASU palette. The October 26 revision preserves the Beamer style, selected Git diagrams, and the original dinosaur-builder illustration.

---

**Happy Researching! 🔬**
