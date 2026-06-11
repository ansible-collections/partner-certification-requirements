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

### Track both timelines

The Ansible community package follows its own release cadence with strict feature freeze dates.
These do not always align with Red Hat certification timelines.

For example, a new `ansible-core` version may be required by the community package weeks before certification communications address it.
If your collection is in both ecosystems, monitor both schedules so that compatibility work is not delayed.

### Stay responsive to community requests

The [Ansible Community Steering Committee](https://docs.ansible.com/projects/ansible/latest/community/steering/community_steering_committee.html) actively monitors collections in the package for maintenance signals such as recent releases, working CI, and responsiveness to issues.
Collections that appear unmaintained or that do not respond to community pings may be removed from the package.

If your collection is in both ecosystems, make sure someone on your team is watching for issues and pull requests from community members, not just from Red Hat.

### Release on time for feature freezes

The community package has a feature freeze before each major release.
Collections that miss the freeze may have their version pinned or their latest release excluded.

Plan your release schedule so that stable versions are available before the community package freeze, not just before the certification deadline.

### Subscribe to community communications

Certification communications from Red Hat and community announcements come through different channels.
To stay informed about the community package:

- Subscribe to the [Bullhorn newsletter](https://docs.ansible.com/ansible/devel/community/communication.html#the-bullhorn) for release announcements and important changes.
- Watch the [Ansible Forum](https://forum.ansible.com) for feature freeze dates, maintenance requests, and discussions about your collection.
- Follow the [ansible-community/ansible-build-data](https://github.com/ansible-community/ansible-build-data) repository for package build status and version constraints.

Missing a community announcement can lead to last-minute scrambles or broken package builds that affect all Ansible users.

## Getting involved in the Ansible community

Whether or not you pursue inclusion in the Ansible community package, there are many ways to participate in the Ansible community:

- Join the [Ansible Forum](https://forum.ansible.com) and use the [`red-hat-partner`](https://forum.ansible.com/tag/red-hat-partner) tag for certification discussions.
- Attend community events and working group meetings listed on the forum.
- Contribute to other projects in the [Ansible ecosystem](https://docs.ansible.com/ecosystem.html) as well as other collections.

For more information, see the [Ansible communication guide](https://docs.ansible.com/ansible/devel/community/communication.html).
