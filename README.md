# Research Project Template: Git, GitHub, and Agentic AI Workshop

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This repository serves as a **template for reproducible research projects** created by **Tomas Larroucau** and accompanies the workshop: *"Git, GitHub, and VS Code: Agentic AI for Project Management and Research Productivity."*

Workshop: **Monday, October 26, 2026**. The lecture deck begins with setup, VS Code, agent capabilities and writing, then Git/GitHub guardrails, orchestration, and integrations. Allow 90 minutes, with additional discussion up to two hours.

## 🎯 Purpose

This template demonstrates best practices for:
- **Version control** with Git and GitHub
- **Reproducible data analysis** workflows
- **Integration of AI agents** (GitHub Copilot, Codex, Claude Code)
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

### Workshop Prerequisites

For the workshop, prepare the accounts and software below. Python, LaTeX, and Make are needed only to run the template locally.

**1. Accounts**
- **GitHub Account:** Create a free account at [github.com](https://github.com).
- **GitHub Education (Recommended):** Check the [student or teacher eligibility requirements](https://education.github.com/). Verification and benefit activation are separate steps; complete them before the workshop. Access and usage limits depend on the plan.

**2. Software**
- **Visual Studio Code:** Download and install from [code.visualstudio.com](https://code.visualstudio.com).
- **Git:** Download and install from [git-scm.com](https://git-scm.com/downloads).
  - *Windows Users:* We recommend installing "Git for Windows" which includes Git Bash.
  - *Mac Users:* Git often comes pre-installed, or can be installed via Xcode command line tools (`xcode-select --install`).

**3. AI Agent Access**
- Set up **one** agent using its official instructions: [GitHub Copilot](https://code.visualstudio.com/docs/copilot/setup), [Codex CLI](https://learn.chatgpt.com/docs/codex/cli) or [IDE extension](https://learn.chatgpt.com/docs/codex/ide), or [Claude Code](https://code.claude.com/docs/en/quickstart).
- Sign in and test a request before the workshop. Provider subscriptions, Copilot access, and API billing are separate routes; you do not need every tool installed.
- In VS Code, use the provider's extension or supported agent integration. See the [current harness and interface requirements](https://code.visualstudio.com/docs/agents/run/agent-harnesses).

**4. Optional Integrations**
- GitHub MCP connects an agent to GitHub tools. Configure it for the selected harness, authenticate, and check permissions before use. It is optional for following the workshop.
- Overleaf Git integration and GitHub synchronization require eligible Premium access. Local LaTeX compilation is an alternative.

### Project Requirements (For Code Execution)

To run the analysis scripts and compile the documents locally:

- **Python** compatible with `scripts/requirements.txt`; use a current supported environment
- **LaTeX Distribution** (TeX Live, MiKTeX, or MacTeX), including Beamer, TikZ, and `twemojis`
- **Make Utility** for the `make` commands below

### Installation

1. **Clone this repository:**
   ```bash
   git clone https://github.com/tlarroucau/AI_workshop.git
   cd AI_workshop
   ```

2. **Install Python dependencies:**
   ```bash
   python -m pip install -r scripts/requirements.txt
   ```

3. **Run the complete workflow:**
   ```bash
   make all
   ```

To compile only the slides, without running the analysis pipeline:

```bash
cd tex/slides
pdflatex -interaction=nonstopmode -halt-on-error workshop_slides.tex
pdflatex -interaction=nonstopmode -halt-on-error workshop_slides.tex
```

The original slide assets are in `tex/slides/figures/`. LaTeX Workshop can compile and display the PDF in VS Code. Installation details and source links for the workshop's agent features and optional skills are in [workshop_review/source_notes.md](workshop_review/source_notes.md).

The current lecture deck is [workshop_slides.pdf](tex/slides/workshop_slides.pdf); its canonical source is [workshop_slides.tex](tex/slides/workshop_slides.tex).

### Skill material status

- The writing skills named in the slides (`academic-draft-editing`, `econ-write`, and `humanizer`) are references to the author's existing tools; their private originals are not bundled here.
- Optional third-party skills are linked in the source notes. Use their upstream installation instructions and attribution/redistribution terms; this repository does not redistribute those skill packages.
- The original YouTube transcript example remains in `.github/skills/youtube-transcript/`. It is a legacy example, not a validated cross-tool skill package; it requires `youtube-transcript-api` and tool-specific setup. Its original files and authorship history are retained.
- Command Center is a private example. Its implementation, private machine configuration, credentials, and research inputs are not included.

## 🔧 Makefile Targets

| Target | Description |
|--------|-------------|
| `make data` | Generate/process sample data |
| `make analysis` | Run statistical analysis |
| `make figures` | Generate plots and visualizations |
| `make tables` | Create LaTeX tables |
| `make update-outputs` | Copy analysis outputs to paper/slides directories |
| `make paper` | Compile research paper PDF |
| `make slides` | Compile presentation slides |
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

These files help AI assistants understand:
- Project structure and conventions
- Code style and patterns
- Common workflows and tasks
- Domain-specific context

## 🎓 Workshop Modules

### Introduction, VS Code, and Agents
- Setup, repository structure, VS Code, and agent capabilities
- Harness comparisons, interfaces, instructions, skills, privacy, and Writing with Agents

### Git
- Commits, branches, merges, worktrees, and conflict resolution

### GitHub
- Issues, project boards, pull requests, and collaboration

### Orchestration and Integrations
- Orchestration, independent review, and custom interfaces
- Refine, NotebookLM, Pangram, Granola, and Elicit
- MCP as a connection mechanism, followed by the Overleaf workflow

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

## 🎨 Branding

This template uses the **ASU + W. P. Carey School of Business** color palette:

| Color | Hex | Usage |
|-------|-----|-------|
| ASU Maroon | `#8C1D40` | Headers, primary accents, control group |
| ASU Gold | `#FFC627` | Highlights, footer accent, treatment group |
| ASU Dark Gray | `#484848` | Body text, secondary elements |

The analysis figures use these colors. The workshop slides retain the original Madrid theme.

---

**Happy Researching! 🔬**
