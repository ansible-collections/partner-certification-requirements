# Sanity testing requirements

Collections must pass `ansible-test sanity` checks for certification.

## Python boilerplate

The `future-import-boilerplate` and `metaclass-boilerplate` sanity tests require every non-empty `.py` file in the following directories to include the standard boilerplate:

- `plugins/modules/`
- `plugins/module_utils/`
- `tests/unit/plugins/modules/`
- `tests/unit/plugins/module_utils/`
- `tests/integration/targets/*/library/`

```python
from __future__ import absolute_import, division, print_function
__metaclass__ = type
```

These tests are gated on Python 2 support: they only apply when the collection declares support for Python 2.7 via `tests/config.yml`.
If your collection does not support Python 2.7 (see [Python version support](#python-version-support) below), these tests do not run and no boilerplate is required.

Files that are empty or consist entirely of variable assignments (documentation-only Python files) are also exempt.

## Sanity ignore files

Sanity ignore files must only contain entries that are permitted by the Ansible Lint [sanity rules](https://docs.ansible.com/projects/lint/rules/sanity/).
Invalid entries trigger `sanity[cannot-ignore]` errors and must be removed.

## Pylint checks

Ansible enforces pylint rules that differ from general Python conventions:

- **`disallowed-name`**: Using `_` as a variable name to capture unused return values is a common Python pattern but is not permitted in Ansible plugins and modules. See [this discussion](https://github.com/ansible/ansible/issues/79646) for background.
- **`unused-import`**: Remove unused imports from plugin and module code.

## Python version support

Python 2.7 is no longer supported by Red Hat Ansible Automation Platform and is not required for certified collections.
To declare the minimum Python version for your collection, add a `tests/config.yml` file with a `python_requires` setting.
See the [ansible.utils example](https://github.com/ansible-collections/ansible.utils/blob/main/tests/config.yml) for the expected format.

## Shell script checks

The `shellcheck` sanity test flags issues in shell scripts.
Address these issues where possible, or add them to your sanity ignore files if they cannot be resolved.

## Additional reference

- The [partner-certification-checker](tooling.md#certification-checker) provides a GitHub workflow that runs sanity and static analysis checks in CI/CD pipelines.
