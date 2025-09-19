# Dragonfly Community Membership

- [How We Make Decisions](#how-we-make-decisions)
  - [Solving Conflicts](#solving-conflicts)
  - [Handling Abstentions](#handling-abstentions)
- [Managing Membership](#managing-membership)
  - [How to Become a Member](#how-to-become-a-member)
  - [How to Become an Approver](#how-to-become-an-approver)
  - [How to Become a Maintainer](#how-to-become-a-maintainer)
  - [Removing Inactive Member/Approver/Maintainer](#removing-inactive-memberapprovermaintainer)
  - [Voluntary Departure](#voluntary-departure)
- [CNCF Requests and Communications](#cncf-requests-and-communications)
  - [CNCF-Related Decisions](#cncf-related-decisions)
  - [Process for CNCF Requests](#process-for-cncf-requests)
    - [Initiating CNCF Communications](#initiating-cncf-communications)
    - [Decision Making and Approval](#decision-making-and-approval)
- [Governance and Project Goal Changes](#governance-and-project-goal-changes)
  - [Types of Governance Changes](#types-of-governance-changes)
  - [Governance Change Process](#governance-change-process)
    - [Proposal and Discussion Phase](#proposal-and-discussion-phase)
    - [Decision and Implementation](#decision-and-implementation)
- [Election Process](#election-process)
  - [Election Additional Remarks](#election-additional-remarks)
    - [Maximum Representation](#maximum-representation)
    - [Vacancies](#vacancies)
- [Demonstrating: Adding a New Member](#demonstrating-adding-a-new-member)
  - [Step 1: Nomination](#step-1-nomination)
  - [Step 2: Community Discussion](#step-2-community-discussion)
  - [Step 3: Community Meeting and Voting Initiation](#step-3-community-meeting-and-voting-initiation)
  - [Step 4: Voting Process](#step-4-voting-process)
  - [Step 5: Results and Onboarding](#step-5-results-and-onboarding)

As a proud member of the CNCF, the Dragonfly project follows the [CNCF Code of Conduct](https://github.com/cncf/foundation/blob/master/code-of-conduct.md).

This document explains the responsibilities that come with different contributor roles in the Dragonfly community. Our project is organized into several sub-projects, including (but not limited to) nydus, nydus-snapshotter, api, docs, console, and client. The responsibilities for each role are tied to these specific sub-projects and their repositories.

For a full breakdown of the roles, responsibilities, and qualifications for our community members, please check out our [Contributor Ladder](COMMUNITY_LADDER.md).

## How We Make Decisions

Dragonfly is an open-source project that thrives on transparency. Our repository is the single source of truth for everything—our values, designs, documentation, roadmap, and interfaces.

In short, every decision is made by updating the project. Any change, big or small, that impacts Dragonfly follows these simple steps:

- **Step 1**: Open an issue in the relevant repository to propose a change or raise a concern.
- **Step 2**: Discuss the issue in the comments.
- **Step 3**: Merge or close the issue based on community consensus.

For most issues (excluding those to add new Maintainers):

If we have fewer than seven active Maintainers, an issue can be merged if:

- At least one active Maintainer comments "LGTM" (Looks Good To Me).
- No other Maintainers object to the change.

For the purpose of this document, an "active Maintainer" is defined as a Maintainer who has participated in community activities (such as reviewing PRs, participating in meetings, or contributing to discussions) within the past 3 months.

Additionally, when we have fewer than seven active Maintainers, we might use a "lazy consensus period" for significant issues. This means that after an issue gets initial approval, we'll hold it for a set amount of time (like 7 days) to give everyone a final chance to discuss it. If no one objects, it can be closed. If issues come up, we'll resolve the concerns and then proceed and move forward.

### Solving Conflicts

In the rare event of a disagreement among Maintainers that can't be resolved through discussion, we will use a voting process to reach a decision. The voting process is as follows:

1. Any Maintainer can call for a vote by creating a new issue in the relevant repository, outlining the conflict and proposed solutions.
2. All active Maintainers will be notified and given a chance to vote.
3. The outcome will be determined by a simple majority (more than 50%) of the votes cast.

### Handling Abstentions

If a Maintainer chooses to abstain from voting on a particular issue, their abstention will not count towards the total number of votes cast. The decision will be based solely on the votes of those who actively participate in the voting process.

## Managing Membership

Our Members (and Maintainers/Approvers) share the responsibility for the project's success. In general, they:

- Are accountable for the project's outcomes.
- Are invested in the long-term improvement of the project.
- Dedicate time to all the necessary tasks, not just the fun ones.

Members often work hard behind the scenes, and their efforts aren't always visible. While it's easy to get excited about new features, it's just as important—and often more challenging—to handle bug fixes, small improvements, stability optimizations, and all the other foundational work that keeps the project strong.

### How to Become a Member

Members start out as dedicated contributors who are committed to the long-term success of the project. If you're aspiring to become a Member, you should be actively involved in resolving issues, contributing code, and reviewing proposals and pull requests for at least three months.

Membership is built on trust, and that goes beyond just writing code. You earn the trust of the current Members by consistently acting in the best interest of the project.

New Members are nominated by an existing Approver or Maintainer (through an issue) and need at simple majority vote from the current eligible voters to be approved.

For details on how Members are selected and their terms, see the [Election Process](#election-process).

### How to Become an Approver

Based on the [election process](#election-process), add additional requirements:

1. Get nominated by an existing Approver or Maintainer.
2. Must document your contribution history and explain why you're suitable for this role, while listing the specific areas you want to be responsible for.
3. Approval must be given by at simple majority（more than 50%）of current Maintainers only.

For more details on how Approvers are selected and their terms, see the [Election Process](#election-process).

### How to Become a Maintainer

Based on the [election process](#election-process), add additional requirements:

1. Must be an existing Approver for at least 3 months.
2. Get nominated by an existing Maintainer.
3. Be approved by a supermajority vote (at least 65% of current Maintainers).

For more details on how Maintainers are selected and their terms, see the [Election Process](#election-process).

### Removing Inactive Member/Approver/Maintainer

An existing Member/Approver/Maintainer can be removed from the active list if they are no longer meeting the expectations of the role. If a Member/Approver/Maintainer meets one of the following criteria, any other Member/Approver/Maintainer can propose their removal through a pull request:

- They haven't participated in community activities (such as reviewing PRs, participating in meetings, contributing to discussions, or submitting code) for more than three months.
- They have violated the governance rules more than twice, with documented evidence of violations.

Once the conditions are confirmed, the Member/Approver/Maintainer can be removed following the same voting thresholds as their election. The affected individual has the right to appeal the decision within 14 days by creating an issue in the community repository, which will trigger a review process by the current Maintainers. If someone is removed, we'll add them to an emeritus section in this document to recognize their past contributions.

### Voluntary Departure

If a Member (or Maintainer/Approver) wishes to voluntarily step down from their position, they may do so at any time by creating an issue in the community repository notifying the community of their departure. In this case:

1. Create a departure notice by following these steps:
   - Post an issue in the community repository by following the [departure template](./.github/ISSUE_TEMPLATE/departure.md)
   - Notify at least 7 days before your last day
   - Specify your exact departure date
2. Provide transition details
   - Share handover information
   - Explain any ongoing responsibilities

The departure will be publicly announced and remain visible for at least 7 days. During this period:

- No formal voting required
- The departing Member(or Maintainer/Approver) should include any relevant handover information in their notification
- Other Members should acknowledge the departure with a thank you message
- The departing Member(or Maintainer/Approver) will be added to the emeritus section of this document to honor their contributions

After the departure date, the Member(or Maintainer/Approver) and their GitHub ID will be moved to the emeritus section in the specific file to honor their contributions. And the Maintainer team will remove the departing Member(or Maintainer/Approver) from the Dragonfly GitHub Organization if necessary.

Those processes ensure proper handover and recognition while providing sufficient notice to the community.

## CNCF Requests and Communications

As a CNCF project, Dragonfly maintains an active relationship with the Foundation.

### CNCF-Related Decisions

CNCF-related requests that impact the project require community involvement, including:

- Project status changes (incubation, graduation)
- Resource requests and TOC interactions
- CNCF program participation
- Official statements and responses

### Process for CNCF Requests

#### Initiating CNCF Communications

1. **Proposal**: Any Maintainer creates an issue with label `cncf-request` including description, rationale, and timeline
2. **Discussion**: 7-day minimum community discussion period
3. **Review**: Maintainers discuss in bi-weekly meeting
4. **Other Considerations**: Any other relevant factors or context

#### Decision Making and Approval

We make the decision based on our [defined roles in the document](#how-we-make-decisions).

## Governance and Project Goal Changes

Significant changes to governance structure or project direction require special consideration to ensure community alignment.

### Types of Governance Changes

This process applies to:

- **Governance Document Updates**: Major revisions to governance, membership, or ladder documents
- **Decision-Making Changes**: Modifications to voting thresholds or consensus mechanisms
- **Role Structure Changes**: Adding/modifying community roles or responsibilities
- **Project Goal Changes**: Updates to mission, vision, or strategic direction
- **Repository Structure Changes**: Significant reorganization of project repositories
- **Other Major Changes**: Any other changes with substantial community impact

### Governance Change Process

#### Proposal and Discussion Phase

1. **Proposal**: Any Maintainer creates an issue with label `governance-change` including:
   - Description of proposed changes
   - Rationale and expected benefits
   - Impact analysis and migration plan
2. **Discussion**: Make community discussion in the issue to gather feedback
3. **Voting**: Voting by our [defined roles in the document](#how-we-make-decisions)
4. **Documentation**: Create a Pull Request to update governance documents to reflect changes, and mention the related issue
5. **Announcement**: Publicly announce changes and notify in our bi-weekly community meeting

#### Decision and Implementation

We make the decision based on our [defined roles in the document](#how-we-make-decisions).

## Election Process

The candidates in the election must explain their past contributions to the project and community, as well as their future plans, while also presenting their campaign reasons and clear intentions.

To become a Member, follow these steps:

1. Contributors may create a nomination issue using the [nomination template](./.github/ISSUE_TEMPLATE/nominate.md) in the community repository.
2. (Optional) If you are not comfortable creating the nomination issue yourself, you can reach out to an existing Approver or Maintainer to help you with the nomination. The Approver and Maintainer lists can be found in the [Approvers.md](roles/Approvers.md) and [Maintainers.md](roles/Maintainers.md) files.
3. While the nomination issue is open, the community can discuss the nomination in the issue comments.
4. The nomination issue remains open for 7 days for community discussion and feedback.
5. The nominee must attend our next bi-weekly community meeting with a quick self-introduction and provide a summary of their contributions.
6. If there are no objections from eligible voters during the discussion period and community meeting, the Maintainer Team starts the voting process in the nomination issue.
7. The member election is voted on by current Maintainers and Approvers in the issue, and a simple majority (more than 50%) is needed to pass the election.
8. If approved, a Maintainer creates a PR to update the [membership registry](roles/Members.md) list.
9. The PR must meet these requirements before merging:
    - Link to the nomination and voting issue
    - Get at least 2 "LGTM" reviews from existing Approvers or Maintainers
10. Once merged, the Maintainer team adds the new Member to the Dragonfly GitHub Organization.

The process is similar for becoming an Approver or Maintainer, with additional requirements which are detailed in the [Contributor Ladder](COMMUNITY_LADDER.md).

Furthermore, to ensure a fair and transparent election process, Dragonfly holds below elections for the specific roles:

<!-- markdownlint-disable -->

| Role       | Nomination Period | Voting Period | Eligible Voters                   | Voting Requirements    |
| ---------- | ----------------- | ------------- | --------------------------------- | ---------------------- |
| Member     | 7 days            | 7 days        | Current Maintainers and Approvers | Simple majority (>50%) |
| Approver   | 7 days            | 14 days       | Current Maintainers only          | Simple majority (>50%) |
| Maintainer | 7 days            | 14 days       | Current Maintainers only          | Supermajority (≥65%)   |

<!-- markdownlint-restore -->

- **Nomination Period**: The nominator creates an issue that remains open for 7 days to allow community discussion.

- **Discussion Phase**: The nomination issue remains open for community discussion and feedback during the nomination period.

- **Voting Period**: After the discussion phase, the voting period begins. The vote must start by Maintainers. The vote must remain open for:
  - Member election: 7 days
  - Approver or Maintainer election: 14 days

- **Voting Eligibility**:
  - For Member Vote: Current Maintainers and Approvers may vote
  - For Approver or Maintainer Vote: Only current Maintainers may vote

- **Voting Requirements**:
  - For Member Vote: Simple majority (more than 50%) of eligible voters required to pass
  - For Approver Vote: Simple majority (more than 50%) of current Maintainers required to pass
  - For Maintainer Vote: Supermajority (at least 65%) of current Maintainers required to pass

- **Results and Implementation**: Votes are counted and the highest vote recipients are selected for the respective roles. Election outcomes are documented in meeting summaries, and new nominees will be added to the GitHub Organization by the Maintainers Team.

- **Role List**: The list of current Members, Approvers, and Maintainers is maintained in the [Members.md](roles/Members.md), [Approvers.md](roles/Approvers.md), and [Maintainers.md](roles/Maintainers.md) files respectively.

### Election Additional Remarks

#### Maximum Representation

To ensure balanced representation, no more than four active Maintainers may be from the same company. If more than four candidates from one company are elected, only the top four vote recipients will serve, with additional slots filled by the next highest vote recipients from other organizations.

#### Vacancies

If an elected Maintainer leaves, the candidate with the next most votes from the previous election will be offered the seat. This continues until the seat is filled.

If this fails, a special election will be held using the eligible voters from the most recent election. A Maintainer elected in a special election serves the remainder of the term for the person they're replacing.

## Demonstrating: Adding a New Member

**Background**: Jane Doe has been contributing to the Dragonfly project for 3 months, consistently submitting bug fixes, documentation improvements, and participating in community discussions.

### Step 1: Nomination

- Jane creates a nomination issue herself using the [nomination template](./.github/ISSUE_TEMPLATE/nominate.md) in the community repository, or alternatively, existing Maintainer John Smith helps her create the nomination.

### Step 2: Community Discussion

- The nomination issue remains open for 7 days for community discussion
- Community members provide feedback and ask questions in the issue comments
- Jane responds to questions about her commitment and future plans
- During this period, eligible voters (current Maintainers and Approvers) can raise any concerns or objections.

### Step 3: Community Meeting and Voting Initiation

- Jane attends the next bi-weekly community meeting for a quick self-introduction and provides a summary of her contributions.
- If there are no objections from eligible voters during the meeting, a Maintainer starts the voting process in the nomination issue.

### Step 4: Voting Process

- We use [gitvote](https://github.com/cncf/gitvote) for automated vote counting
- Eligible voters: Current Maintainers and Approvers for Member election
- Voting takes place for 7 days using GitHub issue reactions (👍 for yes, 👎 for no, 👀 for abstain)
- Simple majority (more than 50%) of eligible voters is required for approval

### Step 5: Results and Onboarding

- Vote results are announced: 5 yes, 1 no, 1 abstain (71% approval - passes)
- Jane is officially welcomed as a new Dragonfly Community Member
- A Maintainer creates a pull request to update the `roles/Members.md` file and for the others to review
- Once the PR is merged, the Maintainer team adds Jane to the Dragonfly GitHub Organization with appropriate permissions
- A welcome message will post in the next community meeting summary.
