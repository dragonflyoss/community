# Dragonfly Community Membership

- [How We Make Decisions](#how-we-make-decisions)
- [Managing Membership](#managing-membership)
  - [Adding New Member/Approver/Maintainer](#adding-new-memberapprovermaintainer)
  - [Removing Inactive Member/Approver/Maintainer](#removing-inactive-memberapprovermaintainer)
  - [Voluntary Departure](#voluntary-departure)
- [Election Process](#election-process)
  - [Maximum Representation](#maximum-representation)
  - [Vacancies](#vacancies)
  - [Demonstrating: Adding a New Member](#demonstrating-adding-a-new-member)

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

Additionally, when we have fewer than seven active Maintainers, we might use a "lazy consensus period" for significant issues. This means that after an issue gets initial approval, we'll hold it for a set amount of time (like 7 days) to give everyone a final chance to discuss it. If no one objects, it can be closed. If issues come up, we'll resolve the concerns and then proceed and move forward.

## Managing Membership

Our Members share the responsibility for the project's success. In general, they:

- Are accountable for the project's outcomes.
- Are invested in the long-term improvement of the project.
- Dedicate time to all the necessary tasks, not just the fun ones.

Members often work hard behind the scenes, and their efforts aren't always visible. While it's easy to get excited about new features, it's just as important—and often more challenging—to handle bug fixes, small improvements, stability optimizations, and all the other foundational work that keeps the project strong.

### Adding New Member/Approver/Maintainer

Member/Approver/Maintainer start out as dedicated contributors who are committed to the long-term success of the project. If you're aspiring to become a Member/Approver/Maintainer, you should be actively involved in resolving issues, contributing code, and reviewing proposals and pull requests for at least two months.

Membership is built on trust, and that goes beyond just writing code. You earn the trust of the current Member/Approver/Maintainer by consistently acting in the best interest of the project.

New Member/Approver/Maintainer are nominated by an existing Member/Approver/Maintainer (through an issue) and need a supermajority vote from the current Maintainers to be approved. Similarly, Member/Approver/Maintainer can be removed by a supermajority vote, or they can choose to step down by creating an issue to let any other Member/Approver/Maintainer know. For details on how Member/Approver/Maintainer are selected and their terms, see the [Election Process](#election-process).

### Removing Inactive Member/Approver/Maintainer

An existing Member/Approver/Maintainer can be removed from the active list if they are no longer meeting the expectations of the role. If a Member/Approver/Maintainer meets one of the following criteria, any other Member/Approver/Maintainer can propose their removal through a pull request:

- They haven't participated in community activities for more than three months.
- They have violated the governance rules more than twice.

Once the conditions are confirmed, the Member/Approver/Maintainer can be removed. If someone is removed, we'll add them to an alumni section in this document to recognize their past contributions.

### Voluntary Departure

If a Member wishes to voluntarily step down from their position, they may do so at any time by creating an issue in the community repository notifying the community of their departure. In this case:

1. Create a departure notice
   - Post an issue in the community repository
   - Notify at least 7 days before your last day
   - Specify your exact departure date
2. Provide transition details
   - Share handover information
   - Explain any ongoing responsibilities

The departure will be publicly announced and remain visible for at least 7 days. During this period:

- No formal voting required
- The departing Member should include any relevant handover information in their notification
- Other Members should acknowledge the departure with a thank you message
- The departing Member will be added to the alumni section of this document to honor their contributions

After the departure date, the Member and their GitHub ID will be moved to the emeritus section in the [MAINTAINERS.md](MAINTAINERS.md#emeritus-maintainers) file to honor their contributions. This process ensures proper handover and recognition while providing sufficient notice to the community.

## Election Process

The candidates in the election must explain their past contributions to the project and community, as well as their future plans, while also presenting their campaign reasons and clear intentions.

Dragonfly holds below elections for the specific roles:

| Role       | Nomination Period | Voting Period | Eligible Voters                   | Voting Requirements |
| ---------- | ----------------- | ------------- | --------------------------------- | ------------------- |
| Member     | 7 days            | 7 days        | Current Maintainers and Approvers | Simple majority     |
| Approver   | 7 days            | 14 days       | Current Maintainers only          | Simple majority     |
| Maintainer | 7 days            | 14 days       | Current Maintainers only          | Supermajority       |


- **Nomination Period**: Nominees are introduced during bi-weekly community meetings with an overview of their contributions. Following the meeting, nominees create an issue that remains open for 7 days to allow community discussion.

- **Discussion Phase**: Each nomination is reviewed in at least one bi-weekly community meeting where members can provide feedback and ask questions about the candidate's qualifications.

- **Voting Period**:
  - Member elections: 7 days
  - Approver or Maintainer elections: 14 days

- **Voting Eligibility**:
  - For Member: Current Maintainers and Approvers may vote
  - For Approver or Maintainer: Only current Maintainers may vote

- **Voting Requirements**:
  - For Member: Simple majority (>50%) of eligible voters required to pass
  - For Approver: Simple majority (≥50%) of current Maintainers required to pass
  - For Maintainer: Supermajority (≥65%) of current Maintainers required to pass

- **Results and Implementation**: Votes are counted and the highest vote recipients are selected for the respective roles. Election outcomes are documented in meeting summaries, and new nominee will added to the GitHub Organization by the Maintainers Team.

### Maximum Representation

To ensure balanced representation, no more than four active Maintainers may be from the same company. If more than four candidates from one company are elected, only the top four vote-getters will serve, with additional slots filled by the next highest vote recipients from other organizations.

### Vacancies

If an elected Maintainer leaves, the candidate with the next most votes from the previous election will be offered the seat. This continues until the seat is filled.

If this fails, a special election will be held using the eligible voters from the most recent election. A Maintainer elected in a special election serves the remainder of the term for the person they're replacing.


### Demonstrating: Adding a New Member

**Background**: Jane Doe has been contributing to the Dragonfly project for 3 months, consistently submitting bug fixes, documentation improvements, and participating in community discussions.

**Step 1: Nomination**
- Existing Maintainer John Smith opens an issue titled "Nomination: Jane Doe for Member"
- The issue includes:
  - Jane's GitHub handle and contact information
  - Summary of her contributions over the past 3 months
  - Links to her pull requests and issue discussions
  - Justification for why she should become a Member

**Step 2: Community Discussion**
- The nomination issue remains open for 7 days
- Community members provide feedback and ask questions
- Jane responds to questions about her commitment and future plans
- The nomination is discussed during the next bi-weekly community meeting

**Step 3: Voting Process**
- After the discussion period, eligible voters (current Maintainers and Approvers) cast their votes
- Voting takes place for 7 days using GitHub issue reactions (thumbs up for yes, thumbs down for no, and eyes for abstain). We are using [gitvote](https://github.com/cncf/gitvote) automated vote counting.
- Simple majority (>50%) is required for approval

**Step 4: Results and Onboarding**
- Vote results are announced: 5 yes, 1 no, 1 abstain (71% approval - passes)
- Jane is officially welcomed as a new Dragonfly Community Member
- She is added to the GitHub organization with appropriate permissions
- Her information is updated in the `MEMBERS.md` file by the Maintainers Team
- A welcome message is posted in the next community meeting summary




