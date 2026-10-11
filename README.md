<p align="center">
  <a href="https://mru.space">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://mru.space/assets/readme/mru-github-dark.gif">
      <img src="https://mru.space/assets/readme/mru-github-light.gif" alt="Mru" width="120" height="120">
    </picture>
  </a>
</p>

# Mru whitepaper

Source and PDF for the **Mru** whitepaper,
*A Fault-Tolerant Operating System for Thousand-Year Autonomous Operation*, by
Will Binns. The project lives at [`mru.space`](https://mru.space).

> Systems that still run a thousand years after we're gone.

## Versions

- **1.1.1, October 2026**: archived on Zenodo,
  [doi:10.5281/zenodo.23305299](https://doi.org/10.5281/zenodo.23305299). Fixes the
  layout of Figures 4, 5, 7 and 8, four references and one heading, and updates
  the author's email. The text is the same as 1.1.
- **1.1, October 2026**: archived on Zenodo,
  [doi:10.5281/zenodo.20580927](https://doi.org/10.5281/zenodo.20580927). Adds related work on
  degradable systems and spacecraft redundancy management, the first evidence
  for the Layer 1 policy (Dusk and the Mru Flight bench), and an errata section
  that lists every change from 1.0 and why.
- **1.0, May 2026**: archived on Zenodo,
  [doi:10.5281/zenodo.20579438](https://doi.org/10.5281/zenodo.20579438).

## Abstract

No software system in human history has been designed to operate for centuries
without human intervention. The longest-lived systems we have built (deep-space
probes approaching fifty years of service, banking codebases approaching sixty)
survive only through continuous human maintenance. An interstellar probe
operating for 500 to 1,000 years cannot: its hardware is guaranteed to fail, its
power to decline, its memory to corrupt, and the light-delay makes human guidance
physically impossible.

This paper introduces **Mru**, an open-source operating system that treats this
physical decay not as an exceptional fault but as the governing design
constraint. It formalizes the stance as the *Degradation-First Principle* and
derives a layered architecture modeled on biological robustness: a minimal,
formally verified interpreter, replicated across reconfigurable hardware, that
executes behavior encoded as mutable data, the way DNA encodes behavior run by a
replicated molecular interpreter. On this kernel it designs hardware consensus
among failing nodes, knowledge triage, autonomous science, bandwidth-starved
communication, and bounded self-modification, with a plan to validate them in
simulation grounded in published radiation, power, and failure models.

Version 1.1 adds the first evidence, for one part of one layer: a Monte Carlo
simulator of the Layer 1 redundancy policy and a measured prototype of its
decision core, both on general-purpose processors. Layers 0 and 2 to 5 are not
built.

## Read it

- **PDF:** [`mru.pdf`](./mru.pdf) in this repo, or the canonical copy at
  [mru.space/mru-whitepaper.pdf](https://mru.space/mru-whitepaper.pdf).
- **Archived record:** [Zenodo](https://zenodo.org/records/23305299)
  ([doi:10.5281/zenodo.23305299](https://doi.org/10.5281/zenodo.23305299)).
  The concept DOI [10.5281/zenodo.20579437](https://doi.org/10.5281/zenodo.20579437)
  always resolves to the latest version.

## Repository layout

```
mru.tex   # LaTeX source (article class, 10pt, A4)
mru.bib   # BibTeX bibliography
mru.pdf   # compiled paper (committed for convenience)
```

## Building from source

Requires a TeX distribution (TeX Live / MacTeX). The paper uses BibTeX
(`\bibliographystyle{ieeetr}`), so run the standard four-pass build:

```sh
pdflatex mru
bibtex   mru
pdflatex mru
pdflatex mru
```

Or, more simply, with `latexmk`:

```sh
latexmk -pdf mru.tex
```

Build artifacts (`*.aux`, `*.bbl`, `*.log`, …) are git-ignored.

## Citing

If you reference this work, please cite it (and see [TRADEMARK.md](./TRADEMARK.md)
on use of the name):

```bibtex
@misc{binns2026mru,
  author       = {Binns, Will},
  title        = {Mru: A Fault-Tolerant Operating System for
                  Thousand-Year Autonomous Operation},
  year         = {2026},
  month        = oct,
  version      = {1.1.1},
  doi          = {10.5281/zenodo.23305299},
  howpublished = {\url{https://mru.space}},
}
```

## Questions or contributions

Issues and PRs aren't open to the public on this repo, but we'd love to hear from
you. Email [contact@mru.space](mailto:contact@mru.space).

## License & trademark

- **Whitepaper** (text, figures, and LaTeX/BibTeX source):
  [CC BY 4.0](./LICENSE): share and adapt with attribution.
- The **Mru** name and logo are trademarks. See [TRADEMARK.md](./TRADEMARK.md).
  The code license/CC license cover the work itself, not the brand.

© Binns Pte. Ltd.
