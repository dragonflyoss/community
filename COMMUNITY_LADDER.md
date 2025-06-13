# Dragonfly Contributor Ladder

Here's the complete document outlining the contributor roles and responsibilities within the Dragonfly open source project. This document serves as a guide for contributors to understand their roles, expectations, and how they can progress within the community.

- [Contributor Ladder](#contributor-ladder)
  - [Contributor](#contributor)
  - [Member](#member)
  - [Approver](#approver)
  - [Committer](#committer)
- [General Guidance on Contributions and Expectations](#general-guidance-on-contributions-and-expectations)

## Contributor Ladder

This document defines the contributor roles within our open source project, outlining the responsibilities, qualifications, and privileges associated with each role.

Contributors typically start at the base level and progress as their engagement and impact on the project grow. We encourage and support your journey up the contributor ladder!

Each role is described with three key aspects:

- Responsibilities: Tasks and duties expected at this level.
- Qualifications: Criteria or requirements to achieve this role.
- Privileges: Rights and benefits granted to contributors at this level.

Roles and responsibilities may evolve as the project grows. The final decision on role assignments rests with the project Committers.


### Contributor

A Community Contributor is anyone who adds value to the project through direct contributions, which may or may not involve code. This role often includes new or occasional contributors.

* Responsibilities:
    * Adhere to the project's [Code of Conduct](CODE_OF_CONDUCT.md).
    * Follow the contribution guidelines for the project (e.g., [Contribution Guide](CONTRIBUTING.md)).

* Qualifications:
    * Open to anyone participating in the community.
    * Contributions can include:
        * Engaging in community discussions (e.g., forums, Slack).
        * Reporting bugs or submitting feedback.
        * Testing releases and providing reviews.
        * Contributing to documentation.
        * Attending or speaking at community events.
        * Submitting occasional pull requests (PRs).
        * Helping other users or answering questions.
        * Promoting the project publicly.

* Privileges:
    * Can be assigned to issues and request reviews for contributions.

This is the starting point for becoming an Organization Member.

### Member

An Organization Member is a consistent contributor who actively participates in the project. They have elevated privileges in project repositories and are expected to act in the best interest of the community.

* Responsibilities:
    * Maintain regular contributions to the project.
    * Complete tasks or initiatives they volunteer for.

* Qualifications:
    * Demonstrated successful contributions, including at least one of:
        * Submitted or reviewed PRs.
        * Resolved issues or bugs.
        * Equivalent impactful contributions.
    * Actively contributing to a project area where Organization Member privileges are beneficial.

* Privileges:
    * Ability to trigger CI/CD pipelines.
    * Leave reviews and comments on PRs.
    * Recommend other Community Contributors for Organization Member status.
    * Nominate themselves for higher roles as outlined in project governance.

* Promotion Process:
    1. Submit a PR to the member management file (e.g., [members.yaml](ladder/members.yaml)).
    2. Obtain approval from at least two existing Organization Members with "LGTM" comments and final merge by a Committer.


### Approver

A Approver is responsible for specific areas of the project (e.g., code, docs, tests) and plays a critical role in ensuring the quality of contributions in those areas by reviewing and approving changes.

* Responsibilities:
    * Regularly review PRs related to their area of expertise.
    * Follow the project’s [review guidelines](link-to-review-guide).
    * Assist other contributors in becoming Reviewers.
    * Provide feedback on project feature proposals or design documents.

* Qualifications:
    * Must be an Organization Member.
    * Proven track record of high-quality reviews.
    * Deep understanding of their specific area (e.g., through contributions or issue resolution).
    * Commitment to maintaining responsibility for their designated area.
    * Supportive of new and occasional contributors, helping refine PRs for merging.

* Privileges:
    * GitHub permissions to approve PRs and modify labels in their specific areas.
    * Ability to recommend and review other Organization Members for Approver status.

* Promotion Process:
    1. Submit a PR to the team or member management file for the specific review area (e.g., [teams.yaml](link-to-teams-file)).
    2. Receive approval from at least two existing Committers.

Automated tools may assign PRs to Approvers based on their defined areas of responsibility.

### Committer

A Committer holds significant trust within the project, with privileges to merge code, vote on project matters, and guide the project’s direction. This role reflects a deep commitment to the community.

* Responsibilities:
    * Mentor new contributors and Committers.
    * Engage in strategic and policy discussions for the project.
    * Participate in voting on key project decisions as per governance rules.
    * Approve promotions to various roles within the project.

* Qualifications:
    * Detailed in the project’s [governance document](./GOVERNANCE.md) under commit access criteria.
    * Supportive of new contributors, aiding in refining contributions.
    * Demonstrates independent judgment for the project’s benefit, beyond personal or employer interests.
    * Actively mentors others in the community.

* Privileges:
    * Merge code into project repositories.
    * Represent the project publicly as a Committer.
    * Engage with external bodies (e.g., CNCF) on behalf of the project.
    * Nominate new Committers.

* Promotion Process:
    1. Nomination by an existing Committer via a PR to the governance or member file.
    2. Approval through a supermajority vote (e.g., 2/3 of active Committers) as defined in project governance.

Committers contributing to core code are automatically part of the project’s Code Team if defined.


## General Guidance on Contributions and Expectations

We welcome contributions in the form of PRs, issues, and feature proposals. For new contributors, starting with small, meaningful changes is recommended. These are easier to review and help you understand the project’s processes and expectations.

As an open source project, response times for reviews may vary due to the availability of Committers and Approvers. Building trust through consistent, smaller contributions or constructive feedback on others’ work can accelerate recognition and progression.

Every merged contribution commits the project to long-term maintenance. As such, larger changes require not only effort but also a proven track record to assure the community of your ongoing support for maintaining those changes.

Remember, _["no is temporary, yes is forever."](https://www.oreilly.com/library/view/hands-on-design-patterns/9781789135565/3f396314-dac8-446c-ab02-768ae91296fa.xhtml)_ 🙇‍♂️