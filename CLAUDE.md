# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This repository defines the **Red Hat partner collection certification requirements** for Ansible content collections on Red Hat Automation Hub. It is a documentation-only project -- no application code. The output is a MkDocs site published to docs.ansible.com/projects/partner-certification-requirements/ and an LLM-consumable `llms-full.txt` file. Both are generated from the same Markdown source files in `docs/`.

## Build and Lint Commands

All tasks use [nox](https://nox.thea.codes/). Default sessions are `spelling` and `build`.

```shell
nox                              # run default sessions (spelling + build)
nox -s build                     # build the MkDocs site (strict mode)
nox -s spelling                  # spell-check docs with codespell
nox -s formatters_check          # check Python formatting (black)
nox -s commitlint -- origin/main..HEAD  # validate commit messages (CI only, requires git history)
```

There are no application tests -- CI runs spelling, formatting, commitlint, and a strict MkDocs build.

## Commit Messages

Commits must follow [Conventional Commits](https://www.conventionalcommits.org/) format, enforced by commitizen via pre-commit hook and CI.

## Architecture: Dual-Output Documentation

The `mkdocs.yml` file drives two outputs from the same source:

1. **Site navigation** (`nav:` section) -- what humans see on docs.ansible.com.
2. **LLM text** (`llmstxt` plugin `sections:`) -- what gets concatenated into `llms-full.txt` for AI-based certification reviewers.

`docs/review_summary.md` defines the review output table format. It is included in `llms-full.txt` but deliberately excluded from `nav:` (it is LLM-only instructions). A missing row means that requirement gets no explicit pass/fail in review output.

### When adding or removing a certification requirement

All four steps are required to keep the dual outputs in sync:

1. Create or update the Markdown file in `docs/`.
2. Add/remove it from `nav:` in `mkdocs.yml`.
3. Add/remove it from the `llmstxt` plugin `sections:` in `mkdocs.yml`.
4. Update the corresponding row in `docs/review_summary.md`.

## Certification Review Skill

`.claude/skills/certification-review.md` is a Claude Code skill that reviews Ansible collections against these requirements. It fetches `llms-full.txt` at runtime, so it never needs updating when requirements change -- all changes are contained in `docs/` and `mkdocs.yml`.

## Dependencies

Requirements are pip-compile managed in `requirements/`. Each nox session has a corresponding `.in` (direct deps) and `.txt` (locked) file. A shared `constraints.in` pins cross-cutting versions.
