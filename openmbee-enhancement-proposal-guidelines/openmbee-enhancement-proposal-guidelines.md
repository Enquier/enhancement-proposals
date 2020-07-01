# OpenMBEE Enhancement Proposal (OEP) Guidelines

**Note**: This OEP repo is the **canonical "source of truth"** for individual OEPs,
the OEP process, and activity on OEPs.

## Goals of the OEP process

OpenMBEE uses the **OpenMBEE Enhancement Proposal** process (OEP)
to address distributed collaboration and experimentation.
The primary guiding principle of the OEP process is to
encourage collaboration and discussion as early as possible in the lifecycle
of a major proposed change in OpenMBEE, with the goal of preventing costly rework,
competing ideas, and unnecessary forking or fragmentation of ideas.

Several sub-goals exist for this process:

- **Maximize success of large proposals** that get stalled in the wrong venue (e.g. a single PR comment thread)
- Provide a **better alternative to “piecemeal” development** where multiple PRs
  to build an end-to-end set of functionality are split across multiple GitHub
  project without broad consensus, context, or guidance.
- Provide a **clear, time-limited, and authoritative process for work proposals**,
  to facilitate funding conversations.  (e.g. provide a concrete artifact to reference
  in a grant proposal, roadmap item, etc.)
- Provide a **consolidated “stream” of all proposals across the entire OpenMBEE community**
  that contributors of all levels can monitor and selectively engage in.

## Tenets of the OEP process

The OEP process operates under the following tenets:

- **The OEP process is intended for changes of non-trivial scope.**
  “Non-trivial” is addressed below in the “OEP / Not-a-OEP Rubric” of this document.

- **The OEP process naturally complements the PR process, but does not replace it.**
  A thoroughly-reviewed and approved OEP is a valuable reference during a PR to
  reduce friction, reduce time-consuming context sharing, and encapsulate decisions
  and other discussions.  Moving a premature PR into a OEP should be a lightweight
  process that doesn’t cause friction for the contributor.

  For example, GitHub issue and PR templates across the entire OpenMBEE project should have
  references to the OEP process as a possible outcome of a given PR.

- **There is one OEP repository, all OpenMBEE-governed projects must use it.**
  To faciliate the easiest possible adoption and high visibility of ideas, a
  single OEP repository will be used.  Even if a OEP only applies to a single organization.

- The OEP process **has multiple valid use cases**.  Each use case might have a
  slightly different expected workflow.  Some expected use cases include:

  - Non-trivial feature proposals within a single component that would benefit from
    process.  (e.g., a non-trivial change to MBEE Core Framework (MCF) that would benefit from
    formal process within the MCF project)
  - Non-trivial features or improvements that span multiple projects (i.e an enhancement to View Editor that requires API or Data Format changes).
  - Any proposed changes to published APIs or core specifications (e.g., nbformat)
  - Changes to the OEP process itself.
  - Launching a major project in the OpenMBEE GitHub organization.


## OEP Submission Workflow

The following sections describe the major checkpoints in the OEP process.
Note that at any time, the OEP author may withdraw their OEP (and if it has
been added to the README, its status becomes "withdrawn").

### Phase 1: Pre-proposal

This is the least formal stage of any OpenMBEE enhancement proposal. During this
phase, discussions on the mailing list, community forum, in-person, on github issues
are all fine to gauge community interest, feasibility, consequences, and to
scope out technical impact and implementation details.

In order to transition out of the pre-proposal stage, the following checklist must be complete:

1. **Create a GitHub issue**  in the OpenMBEE Enhancement Proposals repo that
 1. Briefly outlines the proposal
 2. Suggests a review team (optional)
 3. Declares why it should be a OEP (See the “OEP / Not-a-OEP Rubric” below.)
2. **Identify a Shepherd** to see the process through. (Shepherds are assigned
   on a round-robin basis from a set of interested engaged volunteers).
3. **Decide if it's a OEP** according to the criteria listed above. The Shepherd decides if the OEP criteria have been met.

**If it's a OEP**. The OEP author creates a new PR with the contents of the OEP proposal. See [this markdown template](OEP-TEMPLATE.md) for a suggested structure of the pull-request.

Subsequent discussion and decisions about the OEP will happen in that PR, and
we now **Move to the RFC phase**.

**If it’s not a OEP**. The shepherd provides a reason for why the issue
doesn't meet OEP criteria, and closes the issue.

### Phase 2: Request for Comments for the OEP

Phase two begins when **the OEP author submits a draft of the OEP as a PR to the OEP repository**.
The Shepherd assigns a number to the OEP according to the pull-request number, and updates
the README of the OEP repository with information about the now in-progress OEP.
The Shepherd then works with the OEP author to
**identify and notify relevant individuals in the OpenMBEE community to review and comment**.

Once this group has been notified, the OEP process enters the RFC phase.

During the **Request For Comment (RFC) phase**, the proposal is iterated on with
feedback from the Review Team and the community at large. The Shepherd helps engage
the Review Team and encourage productive discussion. After the Review Team members
have signed off on the OEP, with the criteria that there are no major objections,
and at least some of the Review Team are in favor, the Shepherd initiates the Final Comment Period.

In the **Final Comment Period (FCP)**, the community at-large has at least 10 calendar days
to provide any final comments on the OEP. A OEP may revert back to RFC if
objections from the community are supported by the Review Team.

At the end of the FCP, the OEP is either:

* **approved**, in which case the PR is merged and work may commence on implementing the OEP (see Phase 3, below)
* **rejected**, in which case the PR is closed
* asked to return to the RFC phase.

In each case, the OEP's status should be updated in the README of the
`enhancement-proposals` repository.

### Phase 3: Work Commences

Once a OEP has been merged into the `openmbee/enhancement-proposal` repository,
implementation can commence on the OEP. The OEP author does not need to implement the OEP themselves.

If the OEP requires one or more pull-requests to be implemented, the author of the PRs should
provide a reference to the OEP so that reviewer has background context on the OEP.
As the OEP is being implemented, the OEP text should be amended with with addendums to
denote the progress of the implementation using the following stages.

1. In progress implementation via (list of PRs).
2. Fully implemented via (list of PRs).

If in the course of implementation, it is discovered that the implementation needs to
be radically different from what was defined in the original OEP, then a pull
request is submitted to modify the original OEP with the new necessary implementation,
and a note citing the need for a modification to the OEP.
This pull request should be re-approved by the original review team.

### OEP Pathways and Status

Below is a rough guide that describes the OEP process and its possible pathways.

```
                      +-----------+
                      |           |
                      | withdrawn |
                      |           |             +-----------+
                      +-----------+             |           |
                  OEP may be withdrawn          |  rejected |
                      at any stage              |           |
                                                +-----^-----+
                                                      |
                                                +------+------+
  +--------------+   +-----------+             |             |            +-------------+   +-----------+
  |              |   |           |             | Request for |            |             |   |           |
  | pre-proposal +---> submitted +------------->  Comments   +------------> in progress +---> completed |
  |              |   |           |  identify   |    (RFC)    |  approved  |             |   |           |
  +--------------+   +-----------+   review    |             |            +-------------+   +-----------+
                                      team     +------+------+
```


## What qualifies as a OEP?

This section contains a set of principles to help determine when something is a OEP.
These should be used to determine when something becomes a PR during the OEP
pre-proposal stage, as well as to determine when a PR becomes a OEP at an individual repo level.

**Principles to follow**

Below are a few example guidelines to follow when deciding if an idea should include
a OEP (If yes, it requires a OEP). Under each question is a relevant example proposal.

- Does the proposal/implementation require PRs across multiple repositories?
  - **Example:** Defining a new Id format for use by API
- Does the proposal/implementation PR impact multiple repositories, or have widespread community impact?
  - **Example:** Updating the JSON Models emitted by MMS
- Does the proposal/implementation change an invariant in one or more repositories?
  - **Example:** TBD
- Does the proposal/implementation create a new concept that will impact multiple repositories?
  - **Example:** Diagram interchange
- Does the proposal involve creating a new repository or sub-project?

## The OEP public archive

A public website contains a readable archive of all OEP proposals.
It contains list of all OEPs that have entered a "final" state
(e.g., "Completed", "Withdrawn", "Rejected"). The content of each OEP will
be displayed in a readable fashion. When a OEP enters into a final state, it
is added to this website.

Note that the OEPs themselves contain the content, while the website is just a
quick way to display them in a reading-friendly format.

## Background

For a background of the OEP process, and recent efforts to improve it, see
[the meta-OEP readme](../00-oep-process/oep-process.md).

