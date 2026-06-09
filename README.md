# Red Hat Partner Collection Certification Requirements

[![Discuss on the Ansible Forum](https://img.shields.io/badge/Ansible%20Forum-Partner%20Certification-%235cbec1?logo=discourse)](https://forum.ansible.com/tag/red-hat-partner)

This project outlines certification requirements for Ansible content collections on [Red Hat Ansible Automation Hub](https://console.redhat.com/ansible/automation-hub).

You can view the latest deployed version of the certification requirements at: [docs.ansible.com/projects/partner-certification-requirements/](https://docs.ansible.com/projects/partner-certification-requirements/)

## Community standards

This project abides by the following policies:

* [Ansible Code of Conduct](https://docs.ansible.com/projects/ansible/devel/community/code_of_conduct.html)
* [Ansible Community Policy for AI-Assisted Contributions](https://docs.ansible.com/projects/ansible/devel/community/ai_policy.html)

## Communication

The [Ansible Forum](https://forum.ansible.com) is the best place to ask questions, share feedback, and discuss certification requirements.
Use the [Project Discussions](https://forum.ansible.com/c/project/7) category with the [`red-hat-partner`](https://forum.ansible.com/tag/red-hat-partner) tag for topics related to this project.

* [Posts tagged with 'red-hat-partner'](https://forum.ansible.com/tag/red-hat-partner): subscribe to participate in partner certification conversations.
* [Get Help](https://forum.ansible.com/c/help/6): get help or help others. Please add the `red-hat-partner` tag when starting new discussions.
* [Bullhorn newsletter](https://docs.ansible.com/ansible/devel/community/communication.html#the-bullhorn): used to announce releases and important changes.
* [Social Spaces](https://forum.ansible.com/c/chat/4): gather and interact with fellow enthusiasts.
* [News & Announcements](https://forum.ansible.com/c/news/5): track project-wide announcements including social events.

For more information about communication, see the [Ansible communication guide](https://docs.ansible.com/ansible/devel/community/communication.html).

## Contributing to this project

We are very happy to receive contributions from Red Hat partners and the wider Ansible community in any form!

### How to open an issue

If you want to report a problem or request an update to the requirements, please:

1. Search in the [issues](https://github.com/ansible-collections/partner-certification-requirements/issues) for similar reports or requests.
1. If there are no similar issues, open a new one by clicking the `New issue` button.

### Contributor guidelines

To learn how to contribute to this project, see the [Contributor guidelines](CONTRIBUTING.md).

### Building the docs locally

This project uses [nox](https://nox.thea.codes/) to manage documentation builds and checks:

```shell
nox                  # run default sessions (spelling + build)
nox -s build         # build the MkDocs site (strict mode)
nox -s spelling      # spell-check docs with codespell
```

## Governance

To reach the project team, start a discussion in the [Project Discussions](https://forum.ansible.com/c/project/7) category on the Ansible Forum with the [`red-hat-partner`](https://forum.ansible.com/tag/red-hat-partner) tag.
Feel free to create a [post](https://forum.ansible.com/new-topic?title=topic%20title&body=topic%20body&category=project&tags=red-hat-partner) with questions or if you have anything on your mind!

See [MAINTAINERS.md](MAINTAINERS.md) for information about project maintenance.

## License

[GNU General Public License v3.0](COPYING)
