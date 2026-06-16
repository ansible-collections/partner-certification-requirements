# Community and the Ansible package

Red Hat certification and the Ansible community package are related but separate.
Certifying a collection with Red Hat makes it available on Ansible Automation Hub for Red Hat customers.
Including a collection in the Ansible community package makes it installable via `pip install ansible` and visible on [docs.ansible.com](https://docs.ansible.com/).

## Where certified collection documentation is published

Certified collections are published on the [Red Hat Ecosystem Catalog](https://catalog.redhat.com/software/search?target_platforms=Red%20Hat%20Ansible%20Automation%20Platform&p=1).
Each certified collection has a public documentation page on this catalog.

The collection index on [docs.ansible.com](https://docs.ansible.com/projects/ansible/latest/collections/index.html) documents collections that are part of the Ansible community package, which is maintained by members of the Ansible community.
Red Hat certification does not automatically include a collection on `docs.ansible.com`.

## Ansible community package requirements

Inclusion in the community package is handled by the Ansible community independently from Red Hat certification.
The community package includes collections that contain plugins or modules; role-only collections and validated content are outside its scope.

Partners are encouraged to review and adopt [community collection requirements](https://docs.ansible.com/projects/ansible/latest/community/collection_contributors/collection_requirements.html) as good practices, even if there are no plans to request inclusion in the Ansible community package.
Many community requirements overlap with Red Hat certification requirements, including sanity testing, semantic versioning, changelog formatting, and documentation standards.

## Coordinating across both ecosystems

Collections that are both certified and included in the Ansible community package must meet two sets of requirements on two different schedules.
Understanding where these overlap and where they diverge helps avoid common friction points.

If your collection is included in the Ansible community package, please:

- Be responsive to requests from the [Ansible Community Steering Committee](https://docs.ansible.com/projects/ansible/latest/community/steering/community_steering_committee.html).
- Plan collection release schedules to accommodate the community package lifecycle.
- Participate in the Ansible community by joining the [Ansible Forum](https://forum.ansible.com).

> Feel free to use the [`red-hat-partner`](https://forum.ansible.com/tag/red-hat-partner) tag for discussions related to certified collections.
