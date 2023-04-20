# GWG proposals and design documents

This repository collects NDC GWG project design documents and proposals. Our focus is more on the NEAR ecosystem and governance side. The core blockchain and interface proposals should go to the NEPs.

The structure is inspired by [Ethereum Improvement Proposals](https://github.com/ethereum/EIPs) and [NEAR Enhancement Proposals](https://github.com/near/NEPs/). While EIPs have different [types](https://eips.ethereum.org/) (Core, Networking, Interface, ...) all in the same category (EIP), we propose to organize the directory with [categories](#categories) based on the outcome (project spec, RFP, general improvement).

Documents should not move between directories. Instead they should be linked. It will break the `git` traceability: Git keeps track of changes to files in the working directory of a repository by their name. When you move or rename a file, Git doesn’t see that a file was moved.

## Categories

### Improvement proposal

Improvement proposals record all design decisions and processes at GWG. A _proposal_ should provide:

- Context on the current state
- Proposed changes to achieve the goals
- Detailed reasoning
- Example scenarios
- Discussions of pros, cons, hazards and alternatives
- Discuss any possible roadblocks.
- follow the [IP Template](./TEMPLATE-IP.md)

### Spec

Spec is a document specifying a project. It may follow up with an [RFP](#request-for-proposal). If a project is known to be an RFP from the beginning, then it should go into RFP directly rather than Spec.

### Request For Proposal

**NOTE**: organization of this directory is still in progress. We need to figure out the best way to manage RFPs and consolidate between using this repository for RFPs or NEAR Social Dev Gigs Board.

---

A request for proposal is a document that a business drafts when that business is seeking out multiple bids for one (or multiple) outsourced projects. The goal of a RFP process is to find and select contractors capable and competitive to deliver the requested project with a professional and quality solution. The process makes the selection clearer and easier from the outset.

In addition to other templates, the document must provide:

- Scope of the project, to allow bidders evaluate the complexity and cost of the project.
- Rough timeline for posting the bids, making a decision and expected delivery time.
- Optionally: budget estimate (if it's known).

Once an RFP is approved, anyone can submit proposals.

### Submitting a bid for RFP

Unless noted otherwise in the RFP document:

1. Create a PR, in the description reference a
2. The submission should be a markdown document based on the [submission template](./TEMPLATE_SUBMISSION.md). The document should be saved as: `RFPs/submissions/rfp-<rfp-number>/<your-business-name>.md`
3. Ask for review, collaborate in a chat.

## Status of the documents

A Status may be Draft if we want to break discussion in few PRs to break down a longer process in few steps.
At the end of the process each design has to be either Accepted or Declined.
If a later design doc significantly changes or reverses a decision, it may be marked
as superseded" with a reference to its replacement.

```text
Draft | Review | Accepted | Rejected | Superseded
```

## Drafting a document

Each document should provide detailed description, including: expected functionality, requirements, assumptions, expected user profile, dependencies and possible outline some preferences related to the solution.

The current process for proposals are:

1. Discuss the need or the problem with the GWG community.
1. Evaluate how important it is. What are the consequences of not building it?
1. Once getting initial feedback, create an issue: this will allow to track the proposal from the draft to the finish line.
1. Asses if it's an Improvement Proposal, Spec or RFP.
1. Draft the scope, requirements, timeline, expected functionality etc...
1. Collect all of it in a new document:
   - Improvement Proposal must be saved as `improvement-proposals/ip-<number>-title.md` and based on the [IP template](./TEMPLATE-IP.md).
   - Specs must be saved as `specs/spec-<number>-title.md` and based on the [Spec template](./TEMPLATE-SPEC.md).
   - RFPs must be saved as `RFPs/rfp-<number>-title.md` and based on the [RFP template](./TEMPLATE-RFP.md).
1. Submit the new proposal using GitHub Pull Request.
   - Make sure the `<number>` is a not used sequence number within the directory. You can use the issue number for that.
   - Link all related improvement proposals (`ip-xyz`), specs (`spec-xyz`) or RFPs (`rfp-xyz`) as outlined in the related template.
   - Don't copy the content of a related proposal. Reference it, instead.
1. Each document draft may have few iterations (and few pull requests) before reaching a final status.
1. After successful review and approval, document status should be set to `approved`. At that stage, anyone can submit proposals.
1. Rejected proposals must have status set to `rejected`.

A proposal, once finalized, should not be significantly modified.
A proposal can be superseded by another proposal. When a design or a proposal is superseded, a reference to the new design should be added to its text.

Discuss proposals in [NDC Tools Telegram](https://t.me/c/1708163325/2318). Contribute to the proposal via standard GitHub pull requests to the main branch.

New to technical specs? Here are some resources to help you effectively create and leverage these documents:

- [A Practical Guide To Writing Technical Specs](https://stackoverflow.blog/2020/04/06/a-practical-guide-to-writing-technical-specs/)
