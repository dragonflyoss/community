# Community membership

This doc outlines the responsibilities of contributor roles in Dragonfly. The Dragonfly project is subdivided into sub-projects under (predominantly, but not exclusively) nydus, nydus-snapshotter, api, docs, console and client. Responsibilities for roles are scoped to these sub-projects (repos).

| Role          | Description                                                                   | Requirements                                                                                | Privileges/Responsibilities                                                                                                      |
| ------------- | ----------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| Contributor   | Contributes code, documentation, or blog posts                                | Must have at least one merged pull request in a Dragonfly repository.                            | Listed as contributors for specific repositories on GitHub                                                                       |
| Member        | Actively contributes to the community and reviews PRs                         | Must have multiple contributions to the project. | Becomes a member of the Dragonfly GitHub organization                                                                                 |
| Approver      | Has the authority to approve contributions                                    | Experienced and active reviewer and contributor to a subproject.                            | Listed in the [CODEOWNERS](https://help.github.com/en/articles/about-code-owners) file on GitHub                                 |
| Maintainer    | Defines the direction and priorities for a subproject                         | Demonstrates responsibility and strong technical judgment for the subproject.               | Listed in the [CODEOWNERS](https://help.github.com/en/articles/about-code-owners) file, has GitHub Team and repository ownership |
| Administrator | Manages the GitHub Dragonfly organization, credentials, and related infrastructure | Highly experienced Dragonfly maintainer                                                          | Listed in the [CODEOWNERS](https://help.github.com/en/articles/about-code-owners) file, has GitHub Team and repository ownership |


## Contributors

We welcome everyone who is interested in Dragonfly to join us in contributing! 

Whether it's by submitting source code to the repository, updating documentation, writing technical blogs, or answering questions for the community on social platforms like DingTalk. Every contribution you make is vital to the development of the Dragonfly community.

For new contributors, we hope that our existing members will warmly lend a hand to help them familiarize themselves with the PR workflow and guide them to understand the relevant documents and communication channels. Let's work together to create a bright future for Dragonfly!

## Member

In the community, members are those participants who remain active over time and continue to contribute to the development of the community. They are authorized to work on issues and code submission requests (PRs) assigned to them, and are required to actively participate in various discussions in the community to ensure that they remain active contributors.
Role definition: A member of the Dragonfly GitHub organization.

### Requirements

- Enabling [two-factor authentication](https://help.github.com/articles/about-two-factor-authentication) for GitHub accounts
- Make multiple contributions to a project or community:
    - Submit or review a code submission request (PR) on GitHub.
    - Submit or review issues on GitHub.
- Actively participate in sub-projects or community discussions, such as attending meetings, participating in chats, etc.
- Join the community's [DingTalk](https://qr.dingtalk.com/action/joingroup?code=v1,k1,pkV9IbsSyDusFQdByPSK3HfCG61ZCLeb8b/lpQ3uUqI=&_dt_no_comment=1&origin=11) server to better interact with community members.
- Read and understand the [Contributor's Guide](https://github.com/dragonflyoss/dragonfly/blob/main/CONTRIBUTING.md): this is the basis for participating in the community.
- Actively participate in one or more sub-projects: make a concrete contribution to the development of the community by actually participating.
- Obtain sponsorship from two sponsors:
    - Sponsors must maintain close interaction with potential members, e.g., in the areas of code, design or proposal review, issue coordination, etc.
    - The Sponsor must be the approver or maintainer of the OWNERS file for at least one code repository in the Dragonfly organization.
- Submit an issue in the [Dragonfly/community](https://github.com/dragonflyoss/community/) repository: formally apply for membership by submitting an issue.
    - Make sure patrons follow the question: @mention patrons in the question so they can follow and participate in the discussion.
    - Complete the membership application checklist:
        - Preview and fill out the [membership application template](https://github.com/dragonflyoss/community/blob/master/issue-template/membership.md), making sure each item meets the requirements.
        - Provide a list of contributions that represent your work on the project.
- Get a confirmation response from your sponsor: Sponsors need to confirm their support for you by replying `+1` to the question.
- Your application will be reviewed by Maintainer, and any member of Maintainer can review the application and decide whether to add you as a member of the GitHub organization.

### Responsibilities

- Actively provide input in project goals, timeline and strategy discussions to help the project move forward effectively.
- Help new members familiarize themselves with the project structure and community norms, and assist them in completing their first contribution to ensure a smooth integration.
- Participate in community meetings on a regular basis to stay on top of project progress and community dynamics, and participate in discussions.
- Actively communicate on mailing lists, forums or chat platforms to share ideas and feedback and promote community collaboration.

## Approver

An Approver is a member who has the additional responsibility of reviewing and approving PRs that affect the project.

### Requirements

- Demonstrate expertise in the project code base and be able to develop a deep understanding of the code structure, logic and related technical details.
- Contribute consistently and with high quality to the codebase, ensuring that submitted code meets project standards and best practices.
- Gain the trust of maintainers and administrators to be able to provide accurate code review and approval comments.
- Be active as a reviewer for the codebase for a minimum of 1 month and have review or authorship of at least 5 substantive PRs in the codebase, with substantive areas defined by the maintainer (e.g., involving refactoring or adding new functionality, not just one line of code change).
- Nominated by the maintainer from the applicable code repository, the candidate is required to receive at least 2 affirmative votes from maintainers; if the repository has only one maintainer, one affirmative vote from that maintainer is required.
- If no other codebase maintainer objects within a week of the nomination, the candidate may be formalized into the appropriate role.

### Responsibilities

- Responsible for reviewing and approving pull requests (PRs) submitted by contributors and members to ensure that code changes meet project coding standards, do not introduce bugs, and contribute to project improvements.
- Controls project quality through code reviews, focusing on overall acceptance of contributions such as dependencies with other features, backward/forward compatibility, APIs and conventions.
- Helps to categorize issues and provide feedback for improvements, and approver status may be a prerequisite for accepting significant code contributions.
- Expected to respond to review requests in a timely manner, inactivity for more than 1 month may result in suspension until active again.
- Mentor contributors and reviewers to help them improve code quality and project participation.
- Has the authority to approve code contributions for acceptance, with the caveat that inactivity for more than 3 months may result in a vote by other maintainers or approvers to remove them from the role, rather than automatic removal.

## Maintainer

The Maintainer is an experienced and trusted member with in-depth knowledge of the project, including its architecture and design principles.Maintainers have the authority to merge PRs (Pull Requests) and are able to make major project decisions.

### Requirements

- Demonstrate sustained commitment to the project by demonstrating long-term activity and high-quality contributions including, but not limited to, development, testing, documentation, and problem solving. Ensure work product meets project standards.
- Deep understanding of the overall project architecture and design, able to clearly articulate its technical objectives and direction.
- In-depth understanding and practical experience in the technical areas of sub-projects (especially related programming languages), able to quickly locate and solve technical problems.
- Continuously contributes to the design and direction of projects, including writing and reviewing technical proposals.
- Actively initiates, participates in, and resolves project-related discussions (e.g., emails, GitHub issues, meetings, etc.) to drive efficient issue resolution.
- Strong commitment to the goals and values of the project, ensuring that individual contributions are aligned with overall project goals
- Drive continuous improvement of the project by presenting general issues and requirements for discussion as part of the specification project.
- Nominated by existing project maintainers or administrators and discussed and approved by the team before becoming a core contributor.

### Acceptance

Maintainers are foremost and first contributors that have dedicated to the long term success of the project. Contributors wishing to become maintainers are expected to deeply involved in tackling issues, contributing codes, review proposals and codes for more than two months.

Maintainership is built on trust. Trust is totally beyond just contributing code. Thus it is definitely worthy to achieving current maintainers' trust via bringing best interest for the project.

Current maintainers will hold a maintainer meeting periodically. During the meeting, filtering a list of active contributors that have proven to invest regular time on project over the prior months. From the list, if maintainers find that one or more are qualified candidates, then a proposal of adding maintainers can be submitted to GitHub via a pull request. If a vote of at least 50% agree with the proposal, the newly added maintainer must be treated valid.

### Responsibilities

- Approve and merge pull requests to ensure timely integration of high-quality contributions.
- Maintain the overall integrity of the codebase by verifying that changes meet quality, stability, and performance standards.
- Manage the release process and ensure that documentation is up-to-date to support users and contributors.
- Help shape the project’s technical vision and roadmap, ensuring alignment with long-term goals and community needs.
- Promote effective communication and collaboration among community members to foster a healthy and productive environment.

## Administrator

An Administrator has the highest level of access and responsibility in the project. They manage overall project governance, ensure adherence to policies, and resolve conflicts within the community.

### Requirements

- Demonstrated significant contributions and leadership within the project over time.
- Possesses in-depth knowledge of how to effectively manage and support an open-source community.
- Earned the trust and respect of both the community members and existing administrators.
- Selected through a consensus decision-making process by the current administrators.

### Responsibilities

- Oversee the configuration and access control of project tools and repositories to ensure smooth operations and secure collaboration.
- Monitor adherence to legal requirements and organizational guidelines to maintain the integrity and sustainability of the project.
- Address Code of Conduct violations and resolve disputes to foster a respectful and inclusive community environment.
- Support the process of electing new leadership roles or implementing changes to the project’s governance framework to ensure fair representation and effective decision-making.

## Inactive members

In the Dragonfly GitHub organization, we understand that active participation is essential to maintaining a healthy community, but we also understand that members' focus may change over time, and we don't expect them to be active all the time. However, as a member of the organization, you will be given elevated privileges that should not be used by those who are not familiar with the current state of the Dragonfly project.

Therefore, if a member leaves the project for a long period of time without any activity, they will be removed from the Dragonfly GitHub organization. If these members wish to rejoin, they will need to complete the organization membership application process again once they are familiar with the current state of the project.

### How inactivity is measured

Members of the Dragonfly organizations are considered inactive if they have made no contributions across any organization within the past 3 months.

Members who have been away from the project for an extended period without any activity will need to re-familiarize themselves with the current state of the project before they can effectively contribute again.

## Inactive maintainers

Existing maintainer can been removed from the active maintainer list. If the existing maintainer meet one of the conditions below, any other maintainers can proposed to remove him from active list via a pull request:

A maintainer has not participated in community activities for more than last three months;
A maintainer did not obey to the governance rules more than twice;
After confirming conditions above, in theory maintainer can be removed from list directly unless the original maintainer requests to remain maintainer seat and gets a vote of at least 50% of other maintainers.

If a maintainer is removed from the maintaining list, other maintainers should at a column to the alumni part to thank the contribution made from the inactive maintainer.