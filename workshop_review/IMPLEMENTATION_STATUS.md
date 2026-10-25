# Review status: October 25, 2026

This branch installs the first delivered workshop revision for local slide-by-slide review. The editable deck and 43-page PDF match the verified Library delivery. The source preserves the original Beamer style, updates the agent comparison, and adds the orchestration framework.

## Scientific example remains open

Tomas subsequently requested a stronger example involving mathematical derivation, implementation, independent validation, exhibits, and LaTeX draft integration. The README-based exercise in this first version is superseded as the proposed centerpiece. It remains visible here only so the delivered version and its diff can be reviewed; it does not satisfy that newer request.

The choice is between the proposed synthetic dynamic admissions/persistence example inspired by CuposBEA and an SRP-inspired preference/sampler example. No new model, simulation, or private research content has been added while that choice is pending.

The existing paper and analysis are preserved. Their outputs are existing teaching material, not newly validated results.

## Review and build

- Editable deck: tex/slides/workshop_slides.tex
- Feature comparison: tex/slides/comparison.tex
- Verified PDF: tex/slides/workshop_slides.pdf
- Change map, proposal, audit, official sources, and prior validation: workshop_review/
- Compare all committed changes: git diff main...HEAD
- Build only slides: make slides-only

The validation record in this directory describes the delivered output-copy version before repository installation. Repository preservation and installation verification are recorded separately in the execution task. No merge, push, PR, publication, or sharing change is part of this branch.
