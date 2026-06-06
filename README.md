# Mru — Whitepaper

![Repobeats analytics](https://repobeats.axiom.co/api/embed/009cc1162d69ac6e2bf428980838387913874c60.svg "Repobeats analytics image")

Source and PDF for the **Mru** whitepaper —
*A Fault-Tolerant Operating System for Thousand-Year Autonomous Operation*, by
Will Binns. The project lives at [`mru.space`](https://mru.space).

> Software that still runs a thousand years after we're gone.

## Abstract

No software system in human history has been designed to operate for centuries
without human intervention. The longest-lived systems we have built — deep-space
probes approaching fifty years of service, banking codebases approaching sixty —
survive only through continuous human maintenance. An interstellar probe
operating for 500 to 1,000 years cannot: its hardware is guaranteed to fail, its
power to decline, its memory to corrupt, and the light-delay makes human guidance
physically impossible.

This paper introduces **Mru**, an open-source operating system that treats this
physical decay not as an exceptional fault but as the governing design
constraint. It formalizes the stance as the *Degradation-First Principle* and
derives a layered architecture modeled on biological robustness: a minimal,
formally verified interpreter, replicated across reconfigurable hardware, that
executes behavior encoded as mutable data — the way DNA encodes behavior run by a
replicated molecular interpreter. On this kernel it builds hardware consensus
among failing nodes, knowledge triage, autonomous science, bandwidth-starved
communication, and bounded self-modification, validated in simulation grounded in
published radiation, power, and failure models.

## Read it

- **PDF:** [`mru.pdf`](./mru.pdf) in this repo, or the canonical copy at
  [mru.space/mru-whitepaper.pdf](https://mru.space/mru-whitepaper.pdf).

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
  month        = may,
  howpublished = {\url{https://mru.space}},
}
```

## Questions or contributions

Issues and PRs aren't open to the public on this repo, but we'd love to hear from
you — say hi on X at [@mrusystems](https://x.com/mrusystems) or email
[contact@mru.space](mailto:contact@mru.space).

## License & trademark

- **Whitepaper** (text, figures, and LaTeX/BibTeX source):
  [CC BY 4.0](./LICENSE) — share and adapt with attribution.
- The **Mru** name and logo are trademarks — see [TRADEMARK.md](./TRADEMARK.md).
  The code license/CC license cover the work itself, not the brand.

© Binns Pte. Ltd.
