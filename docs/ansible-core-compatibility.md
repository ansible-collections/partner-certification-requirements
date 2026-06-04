# Ansible core compatibility requirements

Collections must declare `ansible-core` compatibility using the `requires_ansible` key in `meta/runtime.yml`.

The value must specify a supported `ansible-core` version as a lower bound.
See the [Ansible Automation Platform lifecycle](https://access.redhat.com/support/policy/updates/ansible-automation-platform#coreversion) page for currently supported `ansible-core` versions.

## Setting `requires_ansible`

The `requires_ansible` value is a PEP 440 version specifier that defines which `ansible-core` versions the collection supports.

The lower bound must be a supported `ansible-core` version. For example:

```yaml
requires_ansible: ">=2.16.0"
```

An upper bound is optional:

```yaml
requires_ansible: ">=2.16.0,<2.19.0"
```

Collections that target a higher minimum version are also acceptable.
For example, if supported versions start at `2.16.0`, a collection can declare `requires_ansible: ">=2.18.0"`.

## Technology preview versions

Versions of `ansible-core` released as a [Technology Preview](https://access.redhat.com/support/offerings/techpreview) are not supported for certification.

Collections must not declare a Technology Preview version of `ansible-core` as the minimum value of the `requires_ansible` key.
For example, `ansible-core` version 2.19 is a Technology Preview release only and collections cannot be certified with `requires_ansible >= 2.19.0`.

For more information about Technology Preview versions, refer to [Current AAP and Ansible Core lifecycles](https://access.redhat.com/support/policy/updates/ansible-automation-platform#coreversion).
