# Static analysis requirements

Certification requires collections to pass Ansible Lint scans with the [production profile](https://docs.ansible.com/projects/lint/profiles/#production).

## Rules that cannot be skipped

The following rules are enforced during certification and must not appear in `skip_list` or `.ansible-lint-ignore`:

- `risky-shell-pipe`
- `command-instead-of-shell`
- `meta-no-info`
- `package-latest`
- `no-handler`
- `meta-runtime[unsupported-version]`
- `no-changed-when`
- `risky-file-permissions`
- `command-instead-of-module`
- `unnamed-task`

Skipping these rules can mask issues that affect reliability or security in production environments.

### `meta-runtime[unsupported-version]`

This rule flags collections where `requires_ansible` in `meta/runtime.yml` includes unsupported versions of `ansible-core`, even as a lower bound.
Keeping `requires_ansible` current ensures that collections are validated against supported `ansible-core` versions.

Enforcement may vary depending on context.
Collections tightly coupled to `ansible-core` release cycles, such as those in the `ansible` and `redhat` namespaces, may have more flexibility.
For partner collections, updating the `requires_ansible` to reflect currently supported `ansible-core` versions is expected as part of certification.

## Rules that should be addressed

The following rules do not block certification but should be resolved in subsequent releases:

- `var-spacing`
- `empty-string-compare`
- `role-name`
- `fqcn-builtins`
- `var-naming[no-role-prefix]`
- `key-order`
- `fqcn[action]`
- `name`

Violations in the [min](https://docs.ansible.com/projects/lint/profiles/#min) and [basic](https://docs.ansible.com/projects/lint/profiles/#basic) profiles generally relate to code quality and formatting and are treated similarly.

### Skipping `var-naming`

Older collections frequently include `var-naming` in their skip lists.
This is generally acceptable for collections past version `1.0.0`.
For new collections, consider addressing the underlying naming issues instead.

If you need to customize variable naming conventions, you can configure the rule in `.ansible-lint` as described in the [var-naming documentation](https://docs.ansible.com/projects/lint/rules/var-naming/#settings).

## Notable rule violations

Some rule violations are particularly significant:

- [ignore-errors](https://docs.ansible.com/projects/lint/rules/ignore-errors/): Can hide failures and cause unpredictable behavior. Replace `ignore_errors` directives with `failed_when` or `changed_when` error handling.
- [schema](https://docs.ansible.com/projects/lint/rules/schema/): Can cause runtime failures. The `schema[meta]` violation in particular affects the integrity of collection metadata.
- Missing `meta/main.yml` in roles: Every role directory must include a `meta/main.yml` file with role metadata. Missing metadata can trigger lint warnings and affects how Automation Hub displays role information.

## Ansible Lint configuration

Including an `.ansible-lint` configuration file in a collection tarball is allowed for certified collections.
The file can be used for downstream tooling or CI pipelines, provided it does not skip or exclude required certification checks.

When configuring `.ansible-lint`, keep the following in mind:

- **`skip_list`**: Must not include any of the enforced rules listed above.
- **`exclude_paths`**: Must not exclude content directories such as `plugins/`, `roles/`, or `extensions/`. Excluding non-content directories such as `changelogs/`, `extensions/molecule/`, `.github/`, and `docs/` is acceptable.
- **`profile`**: Must be set to `production` or omitted.

### `no-log-password`

This rule is not included in any Ansible Lint profile and runs only if explicitly enabled in the `.ansible-lint` configuration.
Partner teams should include `no-log-password` in `warn_list` as a security practice.

### Example `.ansible-lint` configuration

```yaml title=".ansible-lint"
--8<-- "docs/.ansible-lint"
```

Only skip cosmetic rules such as YAML formatting.
If your collection has a large number of cosmetic failures, this approach is preferable to leaving them unaddressed.

## Excluding directories and files from collection builds

You can use the `build_ignore` section in `galaxy.yml` to exclude certain directories and files that do not contain user-facing content from collection tarballs:

```yaml title="galaxy.yml"
build_ignore:
  - tests/integration
  - tests/unit
  - extensions/molecule
  - changelogs
  - docs
  - collections
  - .github
  - .ansible
  - .tox
  - .venv
  - .agents
  - .claude
  - .vscode
  - .pytest_cache
  - .pre-commit-config.yaml
```

## Additional reference

- The [partner-certification-checker](tooling.md#certification-checker) provides a GitHub workflow that runs sanity and static analysis checks in CI/CD pipelines.
