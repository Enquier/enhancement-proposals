---
title: OpenMBEE Enhancement Proposal
authors: |
  Charles Galey ([openmbee@gmail.com](mailto:openmbee@gmail.com))
issue-number: 01
pr-number: 01
date-started: "2020-06-30"
type: P - Process
---

# OpenMBEE Enhancement Proposal

## Background

OpenMBEE has no existing *formal* process for adopting, discussing and scheduling major efforts across it's various tools and repositories. As part of the formal adoption of OpenMBEE by NumFocus we have continuously run into issues describing and harmonizing OpenMBEE's various **Major** development efforts. After research into internal Lockheed Martin and similar "Bootcamp" style processes we discovered an existing repository and process for this which was adopted by Project Jupyter. Called “Jupyter Enhancement Proposals” or JEP for short. The repository is here:

<https://github.com/jupyter/enhancement-proposals>

From Project Jupyter we learned that:
> The format was originally used by [IPython (IPEP)](https://github.com/ipython/ipython/wiki/IPEPs:-IPython-Enhancement-Proposals) and continues to be used by the [Python Core language (PEP)](https://www.python.org/dev/peps/). As currently envisioned, JEPs are written documents, in the form of a Pull Request to this repo, which describes significant proposed units of work on the projects. The README of the repo summarizes this as:
>
> >“Jupyter Enhancement Proposals will be used when presenting changes or additions that affect multiple components of the Jupyter ecosystem OR changes to a single key component.”

They also had some lessons learned that led them from their previous process to the current one:
> Since the JEP process was created, Jupyter has grown in the number of users, diversity of usage cases, number of contributors, and number of repos/org. For a variety of reasons, the JEP process has not scaled with this growth. The current situation is characterized by:
>
> 1. Given the scope of development, it is difficult to follow all of the activity;
> 2. As a result, most decisions are made in a distributed manner by local teams of contributors working on particular repos and orgs (hub, lab, ipython, jupyter-widgets, etc.); as a consequence:
> 3. Distributed decisions that affect the project as a whole are made, without all relevant parties being able to participate and contribute.
> 4. This is leading to fragmentation and slow progress in project wide concerns, such as the core protocols and standards of Jupyter.
> 
> As a result, there is a need to revitalize and reorganize an efficient and robust centralized proposal and decision making process for major work units across the project.

## Goals and Tenets

OpenMBEE should adopt the OpenMBEE Enhancement Proposal process (OEP) to address distributed collaboration and experimentation as the community scales in the dimensions of contributors, components, and lines of code.  At a high level, the primary guiding principle of the OEP should be to encourage collaboration (especially to provide a forum/view into the multiple "private" corporate code-bases that are providing periodic drops) and this means we can have discussions as early as possible in the lifecycle of a major proposed change in OpenMBEE, with the goal of preventing costly rework, competing ideas, and unnecessary forking or fragmentation of ideas. The OEP [is a formal write-up that] summarizes the problem, constraints, solution, challenges, and limitations of each proposal. This document is a key element of Project Jupyter's JEP and other Basecamp-like processes and is developed, matured, and evaluated (through the RFC process) as part of a defined workflow.

Several sub-goals exist for this process:

- **Maximize success of large proposals** that get stalled in the wrong venue (e.g. a single PR comment thread)
- Provide a **better alternative to “piecemeal” development** where multiple PRs to build an end-to-end set of functionality are split across multiple GitHub project without broad consensus, context, or guidance.
- Provide a **clear, time-limited, and authoritative process for work proposals**, to facilitate funding conversations.  (e.g. provide a concrete artifact to reference in a grant proposal, roadmap item, etc.)
- Provide a **consolidated “stream” of all proposals across the entire OpenMBEE community** that contributors of all levels can monitor and selectively engage in.

With that in mind, the OEP process wil operate under the following tenets:

- **The OEP process is intended for proposed changes of non-trivial scope.**  “Non-trivial” is addressed below in the “OEP / Not-a-OEP Rubric” of this document.  If proposals that go through the OEP process do not receive the benefits listed above, the OEP process should be amended to better scope what applied.

- **The OEP process naturally complements the PR process, but does not replace it.**  A thoroughly-reviewed and approved OEP is a valuable reference during a corporate code-drop or Github PR to reduce friction, reduce time-consuming context sharing, and encapsulate decisions and other discussions.  Moving a premature PR into a OEP should be a lightweight process that doesn’t cause friction for the contributor.

  - GitHub issue and PR templates, for example, across the entire OpenMBEE project, should have references to the OEP process as a possible outcome of a given PR.

- **There is one OEP repository, all OpenMBEE-governed projects must use it.**  To faciliate the easiest possible adoption and high visibility of ideas, a single OEP repository will be used.  Even if OpenMBEE eventually fractures across multiple organizations there will be only one OEP repository.

- The OEP process **has multiple valid use cases**.  Each use case might have a slightly different expected workflow or base OEP template.  Some expected use cases include:

  - Non-trivial feature proposals within a single component that would benefit from process.  (e.g., a non-trivial change to the MBEE Core Framework (MCF) that would benefit from formal process within the MCF project)
  - Non-trivial features or improvements that span *multiple* projects.
  - Any proposed changes to published APIs or core specifications (i.e. MMS API)
  - Changes to the OEP process itself.
  - Creating a new GitHub repo in the official OpenMBEE org


## OEP Submission Workflow

### Phase 1: Pre-proposal

This is the least formal stage of any OpenMBEE enhancement proposals. During this phase, discussions on the mailing list, in-person, on github issues are all fine to gauge community interest, feasibility, consequences, and to scope out technical impact and implementation details.

In order to transition out of the pre-proposal stage, the following checklist must be complete:

1. A github issue on the OpenMBEE Enhancement Proposals repo is created that
2. 1. Briefly outlines the proposal

   2. Suggested review team (optional)

   3. Why it should be a OEP

   4. 1. See the “OEP / Not-a-OEP Rubric” below.
3. A *Shepherd* is identified to see the process through. (Shepherds are assigned on a round-robin basis from a set of interested engaged volunteers).
4. A number is assigned to the OEP to track it through the rest of the process.

Outcome:

The Shepherd decides if the OEP criteria have been met.

- *It's a OEP!* Please create a new PR with the OEP contents using template X.  On that basis, you can resolve this issue unless you have further questions.*
- *It’s not a OEP*. (Provide reasons and close the issue.)

### Phase 2: RFC for the OEP

Submission: The author submits an initial draft of the OEP as a PR to the OEP repository starting from the relevant template decided in the pre-proposal stage. The Shepherd assigns a number (the GitHub PR number? A sequential number? Perhaps the number isn't assigned until the OEP is merged?). The Shepherd assigns a Review Team.

Request For Comment (RFC) phase: The proposal is iterated on with feedback from the Review Team and the community at large. The Shepherd helps engage the Review Team. After the Review Team members have signed off on the OEP, with the criteria that there are no major objections, and at least some of the Review Team are in favor, the Shepherd initiates the Final Comment Period.

Final Comment Period (FCP): The community at large has 10 calendar days in which to provide any final comments on the OEP. A OEP may revert back to RFC if objections are supported by the Review Team. If not reverted to the RFC phase, the OEP is approved at the end of the FCP.

### Phase 3: Work Commences

Once a OEP has been merged into the `openmbee/enhancement-proposal` repository, development work can commence on the OEP. As the implementer(s) is submitting a pull request or pull requests in relation to the OEP, they should provide a reference to the OEP so that reviewer has background context on the OEP.

As the OEP is being implemented, the implementer(s) are submitting pull requests for the OEP, they should update the OEP with addendums to denote the progress of the implementation using the following stages.

1. In progress implementation via (list of PRs).
2. Fully implemented via (list of PRs).

If in the course of implementation, it is discovered that the implementation needs to be radically different from what was defined in the original OEP, then a pull request needs to be submitted to modify the original OEP with the new necessary implementation and a note citing the need for a modification to the OEP. This pull request should be re-approved by the original review team.

If in the course of the implementation, the implementer(s) can choose to withdraw from the original OEP if they are no longer interested in implementing the OEP or see infeasibilities in the OEP.

### Paths of the status of OEPs

![img](https://docs.google.com/a/safia.rocks/drawings/d/s9fsfcbWM0mamBZBDJpK0sA/image?w=583&h=255&rev=154&ac=1&parent=16xa1DSH0lN6lY-EzyyGOzaZlcQc1ZT8HEeDc3uyrwcI)

## What qualifies as a OEP?

This section contains a set of principles to help determine when something is a OEP. The principles will be used to determine when something becomes a PR during the OEP pre-proposal stage, as well as to determine when a PR becomes a OEP at an individual repo level.

**Principles to follow**

Below are a few example guidelines to follow when deciding if an idea should include
a OEP (If yes, it requires a OEP). Under each question is a relevant example proposal.

- Does the proposal/implementation require PRs across multiple orgs?
  - Defining a unique cell identifier
- Does the proposal/implementation PR impact multiple orgs, or have widespread community impact?
  - Updating nbformat
- Does the proposal/implementation change an invariant in one or more orgs?
  - Defining a unique cell identifier
  - Deferred kernel startup
- Does the proposal/implementation create a new concept that will impact multiple repositories?
  - Sandboxed cell outputs
- Does the proposal involve creating a new repository or subproject?

## Distribution

This section describes how information about the OEP process (e.g., new OEPs, updates to
current OEPs, etc) is communicated to the community.

Note: This OEP repo is the **canonical "source of truth"** for individual OEPs, the OEP process, and activity on OEPs.

### The OEP public archive website

A public website contains a readable archive of all OEP proposals.
It contains list of all OEPs that have entered a "final" state
(e.g., "Completed", "Withdrawn", "Rejected"). The content of each OEP will
be displayed in a readable fashion. When a OEP enters into a final state, it
is added to this website.

Note that the OEPs themselves contain the content, while the website is just a
quick way to display them in a reading-friendly format.


## Glossary

- **OpenMBEE Enhancement Proposal (OEP)**: A written document that describes a proposed unit of significant work on OpenMBEE.

- **Contributor**: The person (or persons) who is submitting the OEP. The implementation of a OEP may be done by others if so approved.

- **Shepherd**: A senior OpenMBEE contributor who guides the **OEP Contributor** through the pre-proposal, submission, review, approval process of a OEP.

- **Review Team (RT)**: A group of OpenMBEE contributors, with expertise in a particular area of the project, that reviews OEPs related to that area.

- **Final Comment Period (FCP)**: A finite-time, pre-approval period for the community to make final comments.

- OEP Statuses:

  - Inactive
  - Submitted
  - Assigned
  - Rejected
  - Postponed
  - Withdrawn
  - Approved
  - In progress
  - Completed
