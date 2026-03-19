# Crab Monitoring Pipeline: Field Methods, Hardware, and Data Management

[![Deploy](https://github.com/globalwetlands/crab-survey-methods/actions/workflows/deploy.yml/badge.svg?branch=main)](https://github.com/globalwetlands/crab-survey-methods/actions/workflows/deploy.yml)
[![Automatic Release](https://github.com/globalwetlands/crab-survey-methods/actions/workflows/release.yml/badge.svg?event=push)](https://github.com/globalwetlands/crab-survey-methods/actions/workflows/release.yml)

This repository includes the text and code for rendering the book "Crab Monitoring Pipeline: Field Methods, Hardware, and Data Management", which includes survey methods, data preprocessing routines, and analysis tools for crab ecology.

Please click on the "Wiki" page for information on GLOW Crab Monitoring.

# Development

## Requirements:

This repository requires `Node > 20.17.0` in addition to the Python libraries listed in requirements.

Initialize book with `jupyter book init` - just once.

## Building outputs

List of all possible templates can be listed with `jupyter book templates list`.

PDF: `jupyter book build --pdf`

### Microsoft Word (DOCX)

MyST cannot use the same multi-chapter project export for DOCX as for PDF (`multiple articles are only supported for 'tex', 'typst', and 'pdf' exports`). This repo uses a dedicated aggregator, `book/13_word_export.md`, which `include`s each chapter. The DOCX renderer does not support the `{tableofcontents}` directive, so the landing-page prose lives in `book/includes/about-this-book.md` (included from `book/0_index.md` for the site and from `13_word_export.md` for Word).

From the repository root (with [MyST](https://mystmd.org/) available, e.g. `npm install -g mystmd` or `npx mystmd`):

```bash
npx mystmd build book/13_word_export.md --docx
```

Output: `_build/docx/crab-monitoring-pipeline.docx`.

You may see **duplicate identifier** warnings for figures (e.g. `pvc-rig`) because the same chapter is both a site page and inlined into the Word export; the build should still complete. If a future MyST version removes that, warnings may disappear.

### Setting GitHub pages

Run `myst init --gh-pages` for creating GitHub action.

# Contributing

## Creating tag and release

We used annotated tag which specifies the tag and message as follow:

```bash
git tag -a v0.0.1 -m "Release version 0.0.1"
git push origin v0.0.1
```
