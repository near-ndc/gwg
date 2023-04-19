---
#: 1
Status: Approved
Category: NEAR Social
Created: 2023-03
Replaces: --
Requires: --
---

# NDC Dashboard widget

## Summary

The goal of this NDC Dashboard project is to create a foundational layer to help the community find, access, understand, and use the NDC.

The RFP was published on [gov.near.org](https://gov.near.org/t/ndc-dashboard-request-for-proposal/33080) and on [near.social](https://near.social/#/devgovgigs.near/widget/gigs-board.pages.Post?id=226)

Other potential names for this widget:

- NDC Dashboard
- NDC Gateway (?)

## Context

As governance processes of the Near Digital Collective (NDC) are coming closer to launching we need to create new functionality for users to visualize and interact with the NDC in a simple and yet meaningful way.

### What is the NEAR Digital Collective (NDC) and the Governance Working Group (GWG)?

The NDC, originally envisioned by Illia Polosukhin, the co-founder of NEAR Protocol, is now a fully fledged movement led by the NEAR Community. Its goal is to establish a community treasury and governance model that allows the ecosystem to collectively make decisions on everything from funding to elected representatives and more. It's a significant step towards creating a truly decentralized network.

## Scope of work

For the purposes of this spec, it can be assumed that the NDC will be made up of a number of Sputnik DAOs (or similar), each with a set of Elected Members and a set of Treasury Trustees. The initial list of DAOs can be assumed to be the following:

- Members voted in by general public vote

  - Council of Advisors
  - Transparency Commission
  - House of Merit

- Members voted in or assigned by other mechanisms (e.g. AstroDAO)
  - Community Treasury
  - Marketing DAO
  - Developer DAO
  - Creatives DAO
  - Governance Working Group

## Requirements

The solution should

- be built on Near Social as a page or widget
- support an ever-evolving structure of DAOs and SubDAOs
- allow all community members to read and engage with NDCs active proposals (e.g. upvote, comment, share)
- allow NDC DAOs’ members to vote on active proposals
- incorporate a “multi-dao dashboard” functionality, with clickable content that allow users to “drill down” into the various DAOs and their sub-DAOs
- incorporate a “single-DAO dashboard” functionality, with clickable content that allow users to “drill down” into the various components (e.g. active proposals, past proposals, treasury history, inbound funding history, outbound funding history, outbound funding leaderboard)
- enable different options depending on the user is a non-member vs. member of a specific DAO (e.g members can create proposals and vote on proposals, non-members cannot)

The solution should support a number of different metrics

- Treasury metrics graphed over time
  - Total / inflows / outflows
  - Total / allocated / unallocated
  - User can select to show values as USD or NEAR
- Proposal metrics filtered by time period (e.g. last 7 days / 30 days / 12 months)
  - Total number of proposals created / approved / rejected
  - Number of proposals created / approved / rejected, filtered by type of proposal
  - Approval Rate (approved / rejected / expired)
  - Approval Time
  - Members’ votes breakdown for a given proposal
- Member metrics
  - Member vote participation across proposals (created / voted yes / voted no / didn’t participate)
  - Most active members (per number of votes)
- Events feed
  - Proposal status (created, approved, rejected)
  - Payment (allocated / disbursed)
  - Vote (launched / approved / rejected / expired)
  - Member change (added / removed)
