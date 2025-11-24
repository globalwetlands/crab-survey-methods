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

### Setting GitHub pages

Run `myst init --gh-pages` for creating GitHub action.

# Contributing

## Creating tag and release

We used annotated tag which specifies the tag and message as follow:

```bash
git tag -a v0.0.1 -m "Release version 0.0.1"
git push origin v0.0.1
```
