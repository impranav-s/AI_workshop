# Validation record

- Final deck: 43 pages (29 teaching, 14 reference), 16:9, fixed date October 26, 2026.
- Build: `make slides-only`; two successful pdflatex passes with `-halt-on-error`.
- Final LaTeX log: zero warnings, overfull boxes, or underfull boxes.
- Every final slide rendered at 2x scale and visually inspected. The final pass covers pages 1–43. Tables, flow diagrams, screenshots, body text, and footers fit.
- PDF text bounds: no text outside the page; no empty pages.
- Internal project/build navigation links and external source annotations are present in the PDF.
- Source diff and classroom README diff each pass `git apply --check` against the baseline.
- Original checkout status and hashes of the original README, Makefile, deck source, modified PDF, and untracked CLAUDE.md remain unchanged.
- The full research pipeline and the live provider sessions were not run. Existing research outputs are included as baseline teaching material, not newly validated results.

Final PDF SHA-256: `95da29c8e00c86d97b16a0cf750e88a0e2146d650af3c2d9d8a55dc6f1f80abf`

The editable source bundle includes the original text baseline, the full source diff, a slide-by-slide change map, the proposal, official-source notes, a small demo diff, and existing research files for the optional robustness audit.
