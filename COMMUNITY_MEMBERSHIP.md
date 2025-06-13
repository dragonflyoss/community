# Dragonfly Community Membership

As a CNCF member project, the Dragonfly project follows the [CNCF Code of Conduct](https://github.com/cncf/foundation/blob/master/code-of-conduct.md).

This document outlines the responsibilities of contributor roles in Dragonfly. The project is divided into sub-projects (primarily, but not limited to) nydus, nydus-snapshotter, api, docs, console, and client. Responsibilities for roles are tied to these sub-projects (repos).

## The Table of Contents

- [The Table of Contents](#the-table-of-contents)
- [The Roles of Our Membership](#the-roles-of-our-membership)
  - [Contributor](#contributor)
    - [Responsibilities](#responsibilities)
    - [Requirements](#requirements)
  - [Member](#member)
    - [Responsibilities](#responsibilities-1)
    - [Requirements](#requirements-1)
  - [Approver](#approver)
    - [Responsibilities](#responsibilities-2)
    - [Requirements](#requirements-2)
  - [Maintainer](#maintainer)
    - [Responsibilities](#responsibilities-3)
    - [Requirements](#requirements-3)
- [How to Make Decisions](#how-to-make-decisions)
- [The Maintainership Mangement](#the-maintainership-mangement)
  - [Adding Maintainers](#adding-maintainers)
  - [Removal of Inactive Maintainers](#removal-of-inactive-maintainers)
  - [Promotion](#promotion)
    - [How Promotions Work](#how-promotions-work)
  - [Resignation](#resignation)
    - [How Resignation Works](#how-resignation-works)

## The Roles of Our Membership

We have four levels of responsibility:

- Contributor
- Member
- Approver
- Maintainer

### Contributor

A Contributor is anyone who has contributed to the project by submitting code, issues, or participating in discussions.

#### Responsibilities

- Submit code changes via pull requests (PRs).
- Raise issues for bugs, enhancements, or discussions.
- Participate in code reviews when requested.
- Follow the project's Code of Conduct and contribution guidelines.

#### Requirements

- Have a GitHub account.
- Sign the Contributor License Agreement (if applicable).
- Adhere to the project's coding standards and guidelines.

### Member

A Member is a Contributor who has demonstrated long-term commitment through consistent, high-quality contributions and active community participation.

#### Responsibilities

- Fulfill all responsibilities of a Contributor.
- Join project planning and decision-making processes.
- Mentor new contributors.
- Actively engage in community meetings and discussions.

#### Requirements

- A track record of contributions (e.g., code, reviews, discussions) over at least 3 months.
- Invitation from a Maintainer, based on community consensus.
- Ongoing adherence to the project's Code of Conduct.

### Approver

An Approver is a Member with the added duty of reviewing and approving PRs that impact the project.

#### Responsibilities

- Fulfill all responsibilities of a Member.
- Review and approve PRs from Contributors and Members.
- Ensure changes meet coding standards, avoid introducing bugs, and benefit the project.
- Help triage issues and provide feedback on improvements.

#### Requirements

- Proven expertise in the project’s codebase.
- Consistent, high-quality contributions.
- Trusted by Maintainers to deliver reliable reviews and approvals.

### Maintainer

A Maintainer is an experienced, trusted Member with deep knowledge of the project’s architecture and design principles. They have authority to merge PRs and guide major decisions.

#### Responsibilities

- Fulfill all responsibilities of an Approver.
- Merge PRs to the main branch.
- Maintain the codebase's overall quality, stability, and performance.
- Coordinate releases and update documentation.
- Shape the project's technical direction and roadmap.
- Foster communication and collaboration in the community.

#### Requirements

- A history of long-term, high-quality contributions and leadership.
- In-depth understanding of the project’s architecture and design.
- Strong commitment to the project's goals and values.
- Nominated and approved by existing Maintainers.

## How to Make Decisions

Dragonfly is an open-source project that embodies openness. The repository serves as the single source of truth for all aspects, including values, design, documentation, roadmap, and interfaces.

In essence, every decision is an update to the project. Any changes, big or small, that affect Dragonfly must follow these steps:

- Step 1: Open a pull request.
- Step 2: Discuss the PR in comments.
- Step 3: Merge or close the PR based on consensus.

For PRs (except those adding Maintainers):

- If there are fewer than seven active Maintainers, a PR can be merged if:
  - At least one active Maintainer comments "LGTM";
  - No other Maintainers object.

Additionally, when there are fewer than seven active Maintainers, a "lazy consensus period" can be used for significant PRs: after initial approval, hold the PR for a predefined time (e.g., 7 days) to allow final reviews. If no objections arise, it can be merged; otherwise, resolve issues before proceeding.

## The Maintainership Mangement

Maintainers share responsibility for the project's success. In general, they:

- Share accountability for the project's outcomes;
- Make a long-term investment in improving the project;
- Dedicate time to all necessary tasks, not just the most appealing ones.

Maintainers often work diligently, though their efforts may not always be immediately recognized. It's straightforward to focus on exciting features, but equally important—and more challenging—to handle bug fixes, minor improvements, stability optimizations, and other foundational work that sustains the project.

### Adding Maintainers

Maintainers start as dedicated contributors committed to the project's long-term success. Those aspiring to become Maintainers should actively engage in issue resolution, code contributions, proposal reviews, and code reviews for at least two months.

Maintainership is based on trust, which goes beyond code contributions. Earning the trust of current Maintainers involves consistently acting in the project's best interest.

New Maintainers are nominated by an existing Maintainer (via a PR) and require a supermajority vote from current Maintainers for approval. Similarly, Maintainers can be removed by a supermajority vote of existing Maintainers or may resign by notifying any Maintainer.

### Removal of Inactive Maintainers

Existing Maintainers can be removed from the active list if they no longer meet the role's expectations. If a Maintainer meets one of the following conditions, any other Maintainer can propose removal via a pull request:

- Has not participated in community activities for more than three months;
- Has violated governance rules more than twice;

Once the conditions are confirmed, the Maintainer can be removed unless they request to retain their role and receive at least 50% approval from other Maintainers. If removed, add them to an alumni section in this document to acknowledge their past contributions.

### Promotion

Promotion to higher roles (e.g., from Contributor to Member, Member to Approver, or Approver to Maintainer) is based on merit, trust, and sustained contributions. This process encourages growth while maintaining community standards.

#### How Promotions Work

- **Eligibility**: Individuals must meet the requirements of the next role, as outlined in their respective sections. For example, a Contributor needs at least 3 months of consistent contributions to be considered for Member.
- **Nomination**: Current role holders or Maintainers can nominate candidates based on observed performance. Nominations are made via a PR to this document or a dedicated community issue.
- **Review and Approval**: The nomination is discussed in community meetings or PR comments. It requires a supermajority vote from Maintainers (e.g., at least 50% approval from active Maintainers for roles up to Approver; for Maintainer, follow the process in "Adding Maintainers").
- **Timeline**: Promotions are reviewed quarterly to ensure timely recognition of contributions.
- **Benefits**: Promoted members gain access to more responsibilities, such as decision-making or mentoring, which helps build skills and community leadership.

This mechanism promotes fairness and transparency, rewarding those who actively contribute to the project's success.

### Resignation

Team members, including Contributors, Members, Approvers, and Maintainers, may choose to resign from their roles at any time. This mechanism ensures a smooth exit process while preserving community goodwill.

#### How Resignation Works

- **Notification**: Individuals should notify the community by submitting a PR to this document or raising an issue, clearly stating their intent to resign and the effective date.
- **Transition**: For roles like Approver or Maintainer, they must hand over any ongoing responsibilities, such as open PR reviews or project tasks, to ensure continuity. Maintainers should coordinate with the team to reassign duties.
- **Documentation**: Update relevant sections of this document to reflect the change, such as removing the individual from role lists.
- **Alumni Recognition**: Resigned members can be added to an alumni section if they request it, to thank them for their contributions and keep the door open for future involvement.
- **Cooling-Off Period**: After resignation, individuals may rejoin as a Contributor after a minimum 30-day period, subject to Maintainer approval, to maintain fairness.

This process respects personal circumstances and encourages positive community relationships.
