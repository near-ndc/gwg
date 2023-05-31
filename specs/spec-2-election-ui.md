---
Spec ID: 2
Status: Review
Category: NEAR Social
Created: 2023-05-25
Replaces: n/a
Requires: n/a
---

# Spec-2: Election UI

## Summary

<!-- One page high-level overview; put details in the specification section and background in the previous section. Should be understandable by a new engineer or reader who isn't already working on the project. Short summary in layman terms. -->
<!-- List the challenge(s) being solved by this widget. What is the problem? -->

The Election UI provides an interface for people to see the status of current + past NDC Congressional Body elections. This includes the candidates and votes that have been cast. 

Canidates are presented in the Election UI after they've been nominated via [Kudos](https://github.com/near-ndc/gwg/blob/main/specs/spec-1-kudos.md) (or a Nominate specific fork of Kudos). After an election the winning candidates are assigned seats in NDC congress.

## Motivation

<!-- Context one needs to know to understand this doc: motivating examples, previous versions and problems, links to related projects/design docs, etc. You should mention related work outside of NEAR if applicable. Note: this is background; do not write about your design or ideas to solve problems here. What's the "historical" context? Why do we need a new project? Identify the problems and the needs. -->

The following is to provide context for the electing the NDC Congressional Bodies, which are the House of Merit, Transparency Commission, and Council of Advisors. Voting is conducted by verified humans in the NDC (denoted as members of the Voting Body).

The overall governance flow:

1. **Nomination process**, which involves a self vote (based off of kudos) and accompanying attestation and a kudo + attestation by another voting body members
2. **Election process** (the scope of this RFP), which involves voting body members having x amount of credits per congressional body and congressional 
3. **Congress in session**: when the elected congressional members make decisions during their bi-annual tenure in their body including passing setup packages, approving budget of constellations etc. 

We are assuming stage changes: Nomination -> Election -> Congressional Onboarding are done manually, (ex; by the governance working group) as opposed to automatically updated by cross contract calls. Each part of the process, which is not manually handled, will be on-chain. Automation will be worth building once we've proven the system works via manual effort. 

Mechanisms of Nomination are out of scope as are mechanisms of assigning congress seats. We do need a way to clearly communicate who has been elected to congress seats.

## Use Cases

<!-- Who is using this and what does it do? Leave "how" to the design/tech specification sections. If the solution doesn't help these people achieve their goal then the project isn't successful, even if it fills all of the specified technical requirements. -->
<!-- List the different groups of people that will use this widget and what each one can specifically do. If more clarity is needed you can include an actor/action matrix. List all users and their types. List the actions each collective will take individually. User profile description. Describe which action is done by which actors. Feel free to use a table format or provide your own graphics or bundle the description in the Actions section. A "swimlane process chart" often works well here. -->

Actions are broken down by actors:

- Voter
- Candidate
- Watchdog (no IAH credentials)

These user stories illustrate the needs and desires of the actors rather than perscribing how the actors will achieve their goals.

### Voter

#### Outside of Election UI but still in BOS

- I want to be notified when the election opens and notified when the election is about to close directly on BOS [notification widget].
- I want to know about upcoming elections and their dates. 

#### Viewing a Live Election

- I want to see all the candidates for each congressional body, so I know my options.
- I want to see current voting results, so I know everything is happening on chain.
- I want to see how many candidates I can vote for per congressional body, so I know how to select candidates.
- I want to see my past votes casted for each congressional body, so I know who I voted for.
- I want to understand the time frame I'm looking at defined both in terms of Congressional # and year.
- I want to see the results of an election after it was over with transaction history, so there is accountability after the election.

#### Voting in a Live Election

- I want a cart of candidates, so I can organize who I am voting for before I cast a vote on chain.
- I want to be able to vote on each Congressional body one at a time so I don’t have to make the entire decision at once.
- I want to be able to toggle between Congressional bodies so I can more easily choose candidates and my vote status.
- I want to see how many votes I have cast and have left for each congressional body, to better allocate my votes and understand the quadratic voting process.
- I want to learn about quadratic voting because it's new to me.
- I want to easily increment and decrement the votes I've assigned to each canidate. 
- I want to know when I've used up all of my votes so I don't case more votes than I have (Disabled UI, toast notification)
- I want to save my progress for voting/cart, so I can resume + calculate quadratic voting strategy at a later vote without having to submit the whole decision.
- I want to see time until the next Congressional election after a vote is over, so I can plan to run for upcoming congressional elections.
- I want to see past election results (even if its first vote - show no past election), so I can gauge the electorate’s sentiment.

#### Viewing Election Candidates

- I want to see a candidate profile (Near Social) and the platform they used to nominate themselves (nomination mechism).
- I want to see a candidate's past congressional history on profile (past roles, proposals, and complaints), so I can audit their past performance.
- I want to see the profile + attestation (queried from the nomination process) for a candidate so I can see social proof for why someone was elected.
- I want to see what DAOs a candidate is in even if they are not part of NDC, in order to understand what communities they are a part of.

#### Runoffs

- I want to know whether the election resulted in any tie, and what are the clear next steps to finalizing runoff.

### Watchdog

- I want to see details about the ongoing election to judge if it's worth my time and effort to join the NDC and be heard. 

### Candidate

- I want elections to be relatively short so that the time I spend campaigning can be focused. 
- I want to see how much of the voting body has voted in total so I can plan campaign efforts.

### Additional Features & Requirements

<!-- Optionally, describe: Expected functionality, Security issues/requirements, Assumptions/dependencies (internal and external), Potential problems/roadblocks, Budget concerns. -->

- Edit profile in the scope of near social profile
- Results -> green check mark
- Votes can not be changed once cast, but can be changed before they are. 

## Tech Spec

<!-- How does the product implement the features and requirements? Not every feature or requirement needs deep consideration here, but implementation considerations are discusssed they should be captured here. -->

### Smart Contract Functions / Indexing / Backend

<!-- What functions and functionalities should the widget have -->

Election UI will need to query the following information from [https://github.com/near-ndc/voting-v1](https://github.com/near-ndc/voting-v1):
- list of elections
  - houses up for vote.   
    - candidates for each house
    - votes

### Data Structures

### UML Diagrams

<!-- Include diagrams that best capture what needs to be built. Sequence, State, Interaction, Activity, Etc.-->

### Technical Dependencies 

Voting Contracts @ https://github.com/near-ndc/voting-v1

## Design Specification

<!-- UX and UI that affords all of the features and requirements. How it behaves and what it looks like. -->

### Wireframes / Screens

- [2023-05-30 v0.1.0](https://www.figma.com/file/OTKmz4ga22khc2vtWPFkzB/Election-UI-Wireframe?type=design&node-id=102%3A2&t=rNzg02hFvCuYLv9a-1)
  - Desktop Voting for review
  - Roughed out Desktop Profile & Desktop Admin

### UI Design

Follow the NDC Brand Book in line with Material Design, falling back on vanilla [Bootstrap](https://getbootstrap.com/).

![Primary and Secondary NDC Colors in a Material Design Pallet](https://i.imgur.com/Rzx9XnX.jpg)

### Dependent Widgets

<!-- Does the widget interact with other widgets? -->

- Kudos Widget
- Near Social Profile

## Open Questions and Comments

<!-- Topics not covered in this document that need to be addressed in a meeting or async. Potential future improvements, Summary of open discussion. -->
### Open

### Resoloved

- **Q:** How long is the election voting window? If no comment: 8 days (long enough that someone can take a week vacation and still participate in governance). 
  - **A:** Election timing will be retrieved from the smart contract. It will be set on the smart contract by NDC administrators.  
- **Q:**Considering votes are on-chain and don’t lack privacy, should we be able to see votes? In the spec above we are assuming yes. Going off of this, we are unclear on whether a voting body member can override their vote for a congressional body before the deadline as it would make the vote even more susceptible to swindling.
  - **A:** Yes, we will be displaying votes
- **Q:** One of the biggest challenges for NDC Voting body members is to notify them of a vote. THis brings an overall question of outside of BOS Push notification, and what point of the I-AM-HUMAN onboarding flow will users optin and enable Web2 notifications (in a GDPR compliant fashion) so we can remind them of voting (and other NDC critical updates) outside of BOS. This may result in a separate spec for overall NDC GDPR Compliant Notifications
  - **A:** We will use standard BOS notifications.
- **Q:** What is our runoff policy? 
  - **A:** An administraotr will begin a new runoff election in the case of a tie. Starting elections is handled entirely on the contract side via CLI. The voting administrators will be a list of addresses on the voting contract who have permissions to call these functions. 
- **Q:** Can election results be vetoed? How does that work?
  - **A:** If this is possible it will happen off chain as the NDC administrators are filling congress seats based on election results.  
- **Q:** Do we need to pull details on candidate platform in original RFP from nomination process? Or just link to it? 
  - **A:** MVP approach can be to link. Nice to have is a profile page that can be used to see relevant information for any candidate or voter.

## Glossary & References

<!-- Are there any relevant PR comments, issues that led up to this, or articles referenced for why we made the given design choice? Acryonyms or other terminology that could be misunderstood? -->

- [Voting process deep dive](https://docs.google.com/document/d/1Vuo8Zi9d1beJ9oKPeWh95BORkQvnCu6PFDemhZvqk5Q/edit)
- [NDC Product Book](https://docs.google.com/document/d/1w_wfRfp-ISH7g-zu7vAFULVvRNwyLGwNIDC1EBkxvu0/edit)
- [NDC v1 Smart Contracts](https://github.com/near-ndc/voting-v1)
- [Figma Designs v1](https://www.figma.com/file/JqeSbADxp3PNEcycCpIYfd/Election-UI?type=design&node-id=0-1&t=fc1tAPlqA8oVPwu8-0)

## Changelog

<!--
Points for reviewers to consider:

- Be pragmatic: Is there enough information to begin coding? Practically, implementation will reveal the unforeseeable. This doc can evolve to record those issues/resolutions.
- Wide angle view: Do you know of overlapping projects? Are there OKRs or other non-technical forces that would push/pull priority?
- Optimization: Describe alternate approaches and why they are better. Use Caveats section for approaches under consideration, even if they are ultimately abandoned. 
*Please insert your name here if you do review the document.*
--> 

**Authors & Reviewers:** @starpause 


| Ver. | Date       | Author          | Changes Made                             |
| ------- | ---------- | --------------- | ---------------------------------------- |
| 0.1.0   | 2023-05-25 | @starpause      | Initial draft of the document            |


## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
