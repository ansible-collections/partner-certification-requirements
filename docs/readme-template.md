# Title of collection

The collection title should indicate, at a high level, the purpose of the collection.

> All links in the README must use full URLs and markdown syntax.
> Do not use relative links, as READMEs are rendered outside the repository on Red Hat Ansible Automation Hub.

## Description

- Describe what the collection contains, why it is relevant, who should use it, and what it allows the user to do.

## Requirements

- List any collection dependencies or Python packages.
- Include additional prerequisite tasks, if applicable.
- Do not include `pip install ansible` or `pip install ansible-core` commands.
  Red Hat does not support installing Python packages with `pip` and customers run `ansible-core` only in execution environments.
- If the collection contains validated content that requires community packages, state those requirements here and indicate they apply when installing from Galaxy or other sources.

## Installation

- Red Hat customers install certified collections from Red Hat Ansible Automation Hub.
- Red Hat does not support installing collections from GitHub.
- In addition to the boilerplate below, include any details specific to your collection, such as authentication steps required for installation.

### Installing a collection

Install this collection with the Ansible Galaxy command-line tool:

```bash
ansible-galaxy collection install NAMESPACE.COLLECTION_NAME
```

### Installing from a requirements file

You can include this collection in a `requirements.yml` file and install it with `ansible-galaxy collection install -r requirements.yml`:

```yaml
collections:
  - name: NAMESPACE.COLLECTION_NAME
```

### Installing a specific version

Use the following syntax to install version 1.0.0:

```bash
ansible-galaxy collection install NAMESPACE.COLLECTION_NAME:==1.0.0
```

See [using Ansible collections](https://docs.ansible.com/ansible/devel/user_guide/collections_using.html) for more details.

### Upgrading a collection

To upgrade the collection to the latest available version, run the following command:

```bash
ansible-galaxy collection install NAMESPACE.COLLECTION_NAME --upgrade
```

## Use cases

- Outline three to five common use cases for the collection, with informative examples of how it has been used or how it could be used.

## Testing

- List the platforms and product versions the collection supports.
- Note any known limitations or workarounds.
- If the collection includes example or test playbooks that users can run, mention them here.

## Contributing

- This section is optional.
- Include or link to contributor guidelines along with a code of conduct.
- Include pointers to project tags on the [Ansible Forum](https://forum.ansible.com/) along with any other relevant contact information or communication channels.

## Support

- All certified collections must include a support section that describes how customers can get help with the collection.

### Red Hat-managed collections

- Collections in the `ansible` or `redhat` namespaces, or collections managed by Red Hat teams, must identify which Red Hat group maintains the collection and how customers can open support issues using the **Create issue** link on Automation Hub.
- Use the following text, replacing `<product team name>` with the appropriate team:

```text
This collection is maintained by Red Hat <product team name>.

As Red Hat Ansible Certified Content, this collection is entitled
to support through Ansible Automation Platform (AAP) using the
**Create issue** button on the top right corner.
If a support case cannot be opened with Red Hat and the collection
has been obtained either from Galaxy or GitHub, there may be community
help available on the Ansible Forum (https://forum.ansible.com/).
```

### Third-party vendor collections

- Third-party vendor collections should include a support statement.
- Support statements should be clear that Red Hat customers are entitled to open support cases via the **Create issue** button on Automation Hub.

## Release notes and roadmap

- Link to the collection's release notes or changelog.
- If a public roadmap is available, link to it.
- Consider linking to the [Red Hat Ansible Automation Platform Life Cycle](https://access.redhat.com/support/policy/updates/ansible-automation-platform) page to help users understand the support timeline for the collection.
- Private repositories can include release notes in the README or add a changelog file to the collection tarball.
- Collections can add a changelog file to the docs/ directory in markdown format to display release notes in Automation Hub.

## Related information

- Where available, link to general usage documentation for collections or other documentation applicable to the technology or product this collection works with.
- Useful materials such as demos and case studies may be linked here as well.

## License information

- The collection must use an [OSI-approved license](https://opensource.org/licenses/).
- Make the license visible through the `license` field in `galaxy.yml`, the license type stated in the README, or a link to the license file in the README.
- For private repositories, state the license in the README and note that the full license text is included in the downloaded collection.
