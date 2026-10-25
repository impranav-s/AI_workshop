# Research Project Template: Git, GitHub, and Agentic AI Workshop

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This repository serves as a **template for reproducible research projects** created by **Tomas Larroucau** and accompanies the workshop: *"Git, GitHub, and VS Code: Agentic AI for Project Management and Research Productivity."*

## 🎯 Purpose

This template demonstrates best practices for:
- **Version control** with Git and GitHub
- **Reproducible data analysis** workflows
- **Integration of AI coding agents** (GitHub Copilot, local AI assistants)
- **Collaborative research** through issues, pull requests, and project boards
- **Automated workflows** for analysis and document compilation

## 📁 Repository Structure

```
AI_workshop/
├── AGENTS.md                      # Instructions for AI coding agents
├── Makefile                       # Automation workflow
├── README.md                      # This file
├── mindmap.html                   # Interactive project visualization (Open in browser)
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

For the local documentation exercise, use VS Code, Git, and a local copy of this repository. Use one authenticated agent if available, or inspect the prepared diff with a partner. Python, LaTeX, and MCP are not required for editing the README.

A GitHub account is needed for hosted collaboration. Check your chosen agent's current access and limits before the session; Copilot access, provider subscriptions, and API billing are separate routes.

### Optional full project build

The full workflow needs Python with `scripts/requirements.txt`, a LaTeX distribution, and Make. Set up an isolated Python environment:

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r scripts/requirements.txt
make check-env PYTHON=python
make all PYTHON=python
```

On Windows, use `.venv\Scripts\activate` to activate the environment and ensure Make is available in the shell. Use a supported Python version compatible with your installed packages.

Read the Makefile before running a target: `make slides` and `make paper` depend on `update-outputs`, which runs analysis. For a slide-only edit with existing assets, run `pdflatex -halt-on-error -interaction=nonstopmode workshop_slides.tex` twice from `tex/slides`. A successful document build does not establish the correctness of the analysis.

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

### Module I: Git, GitHub, and VS Code Fundamentals
- VS Code as an integrated development environment
- Git basics: commits, branches, merges
- GitHub workflows: pull requests, issues, project boards
- Collaborative development practices

### Module II: Agentic AI Integration
- VS Code Chat modes: Ask, Edit, Agent
- GitHub Copilot in the cloud and locally
- AI-assisted code review and refactoring
- Complementary tools: Refine, NotebookLM, Elicit

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

The Beamer slide theme and matplotlib figures apply these colors consistently across all generated artifacts.

---

**Happy Researching! 🔬**
