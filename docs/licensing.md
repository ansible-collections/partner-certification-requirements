# Licensing requirements

Collections must be licensed under an [OSI-approved license](https://opensource.org/licenses/).
Consult your own legal counsel for guidance on choosing a license.

The license must be visible to users through at least one of the following:

- The `license` or `license_file` field in `galaxy.yml`, which makes the license type visible on [Red Hat Ansible Automation Hub](https://console.redhat.com/ansible/automation-hub).
- The license type stated in the README, for example Apache-2.0.
- A link to the license file in the README.

## `license` and `license_file` in `galaxy.yml`

The [`galaxy.yml`](https://docs.ansible.com/ansible/latest/dev_guide/collections_galaxy_meta.html) file supports two mutually exclusive fields for specifying the license:

- The `license` key contains a list of [SPDX license identifiers](https://spdx.org/licenses/); for example, `GPL-3.0-or-later`.
- The `license_file` key specifies the path to a license file included in the collection; for example, `LICENSE`.

Either the `license` or `license_file` field must be populated in `galaxy.yml`.
