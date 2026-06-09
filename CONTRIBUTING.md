# Contributing to this project

Thank you for your interest in improving the Red Hat partner collection certification requirements!
We welcome contributions from Red Hat partners and the wider Ansible community.

This project is [GPL-3.0 licensed](COPYING) and accepts contributions through GitHub pull requests.

## Getting started

### Prerequisites

You need the following tools:

- Python 3
- [nox](https://nox.thea.codes/)
- [pre-commit](https://pre-commit.com/)

### Setting up your environment

1. Fork and clone the repository.

1. Create and activate a virtual environment:

   ```shell
   python3 -m venv venv
   source venv/bin/activate
   ```

1. Install pre-commit hooks:

   ```shell
   pip install pre-commit
   pre-commit install
   pre-commit install --hook-type commit-msg
   ```

   The hooks run automatically on each commit and check for trailing whitespace, YAML validity, Python formatting with [black](https://black.readthedocs.io/), and [Conventional Commits](https://www.conventionalcommits.org/) message format.

### Building the docs locally

Use [nox](https://nox.thea.codes/) to build and check the documentation:

```shell
nox                  # run default sessions (spelling + build)
nox -s build         # build the MkDocs site (strict mode)
nox -s spelling      # spell-check docs with codespell
```

Review the built site locally before submitting a pull request.

## Writing documentation

This project follows the [Ansible documentation style guide](https://docs.ansible.com/projects/ansible/latest/dev_guide/style_guide/index.html).
The sections below call out the most important guidelines for this project.
Refer to the full style guide for comprehensive details.

### One sentence per line

Write one sentence per line in the Markdown source.
Do not wrap lines at a fixed column width or join multiple sentences on a single line.

One sentence per line makes diffs easier to read, simplifies reviews, and reduces merge conflicts.

### Accessibility

Documentation should be accessible to all readers.

- Use descriptive link text that conveys the target content.
  Avoid bare URLs and vague phrases like "click here" or "this page."
- Do not include screen captures of terminal output.
  Use code blocks instead.
- Write image alt text that describes the meaning of the image, not just its appearance.
- Avoid instructions that rely solely on visual cues such as color, shape, or position on the page.

### Style basics

- Use active voice, present tense, and address the reader as "you."
- Use sentence case for all headings.
- Avoid Latin abbreviations.
  Write "for example" instead of "e.g." and "in other words" instead of "i.e."
- Avoid heading levels deeper than `####`.
  If you need more nesting, consider splitting the content into separate pages.

## How to contribute

### Reporting issues

If you want to report a problem or request a change to the requirements:

1. Search the [existing issues](https://github.com/ansible-collections/partner-certification-requirements/issues) for similar reports.
1. If none exist, open a new issue with a clear description.

### Submitting a pull request

1. Create a branch from `main` for your changes.
1. Make your changes, following the writing guidelines above.
1. Build and spell-check the docs locally with `nox`.
1. Commit your changes with a [Conventional Commits](https://www.conventionalcommits.org/) message.
   The pre-commit hook validates the format automatically.
1. Open a pull request with a clear description of the change and why it is needed.

### Reviewing pull requests

You can also contribute by reviewing open pull requests.
Check for clarity, correctness, style guide adherence, and accessibility.

## Commit messages

This project uses [Conventional Commits](https://www.conventionalcommits.org/) format, enforced by a pre-commit hook.

```
docs: add dependency requirements section
fix: correct broken link in licensing page
```

## Certificate of Origin

By contributing to this project you agree to the Developer Certificate of Origin (DCO).
This document was created by the Linux Kernel community and is a simple statement that you, as a contributor, have the legal right to make the contribution.
See the [DCO](DCO) file for details.

## Communication

Have questions or want to discuss a contribution?
Join the [Ansible Forum](https://forum.ansible.com) and use the [`red-hat-partner`](https://forum.ansible.com/tag/red-hat-partner) tag.
