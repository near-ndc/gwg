---
Spec ID: 1
Status: Review
Category: NEAR Social Widget
Created: 2023-04-21
Replaces: n/a
Requires: n/a
---

# Spec 1: Kudos Widget

## Overview

<!-- Objective. In a few sentences, describe the key system objectives. Tweet length executive summary. -->

Kudos is a widget to build a reputation. The widget will allow any verified human to nominate, recieve, and interact with Kudos on [Near Social ("NS")](https://near.social).

### Challenge

<!-- List the challenge(s) being solved by this widget. What is the problem? -->

The specific purpose of the Kudos widget is to crowd source reputation through gamification. Kudos needs to foster recognition and celebrations of individuals for their contribution to NEAR (in the context of nodes, projects, workgroups, collectives, etc).  

### Context

<!-- Stuff one needs to know to understand this doc: motivating examples, previous versions and problems, links to related projects/design docs, etc. You should mention related work outside of Google if applicable. Note: this is background; do not write about your design or ideas to solve problems here. -->

Reputation is a need in the context of NS. Kudos can be used to build reputation by issuing SBT.

Upvoting is required in various contexts on [NS](https://near.social). Once we have a solution that meets the requirements, the Kudos Widget will serve as a conventional implementation for anyone who wants to fork the widget for other purposes (such as governance nominations).

#### Web2 Inspiration

- Reddit
- StackOverflow
- [lemmy](https://lemmy.ml/)
- Open source
- [Kudos.com](https://www.kudos.com/platform/employee-recognition-software)

#### Web3 Inspiration

- [webuidl Kudos](https://near.social/#/webuidl.near/widget/Kudos)
  - Remove color background on each Kudo.
  - Move upvote button to the left of each row.
  - Use spacing that the input labels are clear which box they belong to.
  - Input a near name instead of a url.
  - Remove the follow/following button.
  - On submission text inputs do not clear out and the kudo does not appear.
  - Allow markdown in the accolade.
  - Preview of accolade. 
- [MetaStakingVote on NS](https://near.social/#/meta-pool-official.near/widget/MetaStakingVote)

#### Other potential names for this widget

- High Five
- Props

## Use Cases

<!-- Who is using this and what does it do? Leave "how" to the design/tech specification sections -->

### Actors / Actions

<!-- List the different groups of people that will use this widget and what each one can specifically do. If more clarity is needed you can include an actor/action matrix -->

**Visitor** no credentials, not logged in.

- View Kudos List
- View Kudos Detail
- Share Kudos (list and deep link to a Kudo detail)

**User** logged in to NS.

- Everything Visitors can do
- Comment on Kudos (if "all users can comment" is enabled by the recipient)
- React to Kudos 
- Upvote Kudos

**Verified Human** logged in user who has credentials issued by `i-am-human`.

- Everything Users can do
- Create new Kudos
- Recieve new Kudos
- Comment on Kudos (if "all verified human users can comment" is enabled by the recipient)

**Administrator** can take additional actions not availalbe to other actors.

- Everything Verified Humans can do
- Delete Kudos
- Change Settings
  - Create or remove sub-categories (aka tags)
  - Adjust experiation time of Kudos

### User Stories

Here are some user stories or use cases for the Kudos widget based on the provided text:

1. As a **visitor** (not logged in), I want to view the Kudos list, so I can see the various accomplishments and recognitions in the community.
2. As a **visitor**, I want to view Kudos details, so I can learn more about a specific Kudo and understand its context.
3. As a **visitor**, I want to share Kudos (list and deep link to a Kudo detail), so I can promote achievements and encourage others to engage with the community.
4. As a **logged-in user**, I want to comment on Kudos, so I can express my thoughts and engage with the community.
5. As a **logged-in user**, I want to react to Kudos, so I can show my appreciation and support for the accomplishments.
6. As a **verified human**, I want to create new Kudos, so I can recognize and celebrate the contributions and achievements of others in the community.
7. As a **verified human**, I want to receive new Kudos, so I can be acknowledged for my contributions and achievements.
8. As an **administrator**, I want to delete Kudos, so I can remove inappropriate or unwanted content from the platform.
9. As an **administrator**, I want to change settings, such as creating or removing categories, adjusting expiration time of Kudos, and deleting Kudos, so I can maintain a positive and productive environment for the community.

### Additional Features & Requirements

The following features will use the Social DB smart contract with the Kudos UI developed in Near Social.

#### Create a kudo

- Nominate any IAH verified account
- Notify the account of the Kudo via the Notifications API
- Send account SBT Badge for each Kudo.
- Display the Kudo as a post in the activity feed.
- Check that creator and reciever are registered with IamHuman.
- Account receiving a Kudo will get receive Near Social notification via Notifications API.

#### Interact with existing Kudo

- Upvote a Kudo
  - Any human can upvote a Kudo (only when Kudo is not expired). 
  - One account can upvote any Kudo only once.
  - Upvotes will be stored in the Social DB or in the Kudo SBT issuer.
- Comment on a Kudo
  - Any human can comment on a Kudo (even if a Kudo expired). 
  - Comments will be implemented using existing Near Social widget (and allow threading aka responses to comments).
- Check the actor is registered with IamHuman
- Share a Kudo (deep link)

#### Displaying All Kudos

- Show overview of all Kudos
- Sort Kudos by date, # of upvotes, # of comments
- Filter Kudos by expired or not, tags, "my kudos" (ones user has interacted with)
- Lead with the name of the person recieving the Kudo, then why.

#### Display Kudo details

- Show who, why, and the nominator
- Show all comments
- Show # of upvotes
- Show who upvoted

#### Kudo Categories

- SBT standard provides a notion of classes. We will use it to define Kudo categories. Initial set of categories is the following: 
- Kudos. Sub-categories include: Thank You! Good Job! Impressive! Excepional!
- Endorse. Sub-categories include: Developer, Community Builder, Product Lead, Marketer, Project Mgr, Sales, Researcher, Architect, Data Scientist, Creative ...
- Nominate. Sub-categories include: House of Merit, Transparency Commissson, Counsil of Advisors, Creatives DAO, Marketing DAO
- TODO: finalize the categories

#### Spam protection

- Using proof of personhood is not enough to protect a system from abuse. One user could attach a bot to his account and send thousands of kudos to other accounts (potentially to the same human account).
- We propose to limit that activity: Any human can send maximum 14 kudos per week. The quota will reset every Sunday at midday UTC (12:00). The quota will be a parameter and the admin will be able to change it in the future.
- The target user should be in control of the Kudos they recieve. Unwanted Kudos can be removed from display by either the nominee or nominator.
- The target user should also be able to set their preference to either auto-accept incoming Kudos to their profile, or require a manual review & approval before accepting incoming Kudos
- Kudo sender will have to set an expire time. To make it more useful, the contract will require that a minimum expire time is 1month.

## Tech Spec

<!-- How does the widget implement the features and requirements? Not every feature or requirement needs deep consideration here, but implementation considerations are discusssed they should be captured here. -->

### Smart Contract Functions

<!-- What functions and functionalities should the widget have -->
Kudos should support two main smart contract functions:

- isHuman (pseudocode example)

    ```
    token = sbt_tokens_by_owner("user.near", "gooddollar-v1.i-am-human.near", 1)
    if !token || token.metadata.expires_at < now {
      return NotAuthorized() // no token or token expired.
    }
    ```

- mintSBT (see NEP-393 for examples)

### Data Structures

### UML Diagrams

<!-- Include diagrams that best capture what needs to be built. Sequence, State, Interaction, Activity, Etc.-->
  
TODO: Include diagrams that best capture what needs to be built. Sequence, State, Interaction, Activity, Etc.
  
## Design Specification

<!-- UX and UI that affords all of the features and requirements. How it behaves and what it looks like. -->

### Wireframes / Screens

https://app.visily.ai/projects/68d0d584-1866-4343-86b5-d1ab1bdef11d/boards/464535

### UI Design

- Follow Near Social convention of using [Bootstrap](https://getbootstrap.com/) snippets and components. 
- Design for mobile first and desktop second.
- Ensure all designs meet A11Y requirements such as contrast by testing the widget with a tool such as [SiteImprove](https://chrome.google.com/webstore/detail/siteimprove-accessibility/efcfolpjihicnikpmhnmphjhhpiclljc), [Lighthouse](https://developer.chrome.com/docs/lighthouse/overview/), [Axe](https://www.deque.com/axe/), or [Wave](https://wave.webaim.org/).

### Dependent Widgets

<!-- Does the widget interact with other widgets? -->

- [Kudos.Styles](https://near.social/#/neardigitalcollective.near/widget/Kudos.Styles)
- [Common.Compose](https://near.social/#/neardigitalcollective.near/widget/Common.Compose)
- [Kudos](https://near.social/#/neardigitalcollective.near/widget/Kudos)
- [kudoBox](https://near.social/#/neardigitalcollective.near/widget/kudoBox)
- [FollowButton](https://near.social/#/neardigitalcollective.near/widget/FollowButton)
- [MainPage.Post.Header](https://near.social/#/neardigitalcollective.near/widget/MainPage.Post.Header)
- [MainPage.Post](https://near.social/#/neardigitalcollective.near/widget/MainPage.Post)
- [showCommentsButton](https://near.social/#/neardigitalcollective.near/widget/showCommentsButton)
- Notifications API

## Work Plan

### Phases

<!-- High-level summary of each phase (if the project does have multiple phases.)  -->

- Finalize SPEC including community feedback
- Call for Proposals and Award work
- TODO: Implementation
- TODO: Integrate with I-am-Human
- TODO: Integrate with SBT Standard

### Sprints

<!-- Break work down into week long chunks. If a team hasn't been identified then assume it will be an individual completing the work. Each sprint should include something which can be considered "Done" so that the product is usable as soon as possible and then recieves incremental improvements. -->

| Week # | Work to Complete |
| -------- | -------- |
|| Review existing solutions, Draft TDD |
|| Review & Update TDD Draft |
|| Publish TDD Draft to Github via PR, solicit wider feedback |
|| Merge TDD PR, call for proposals |
|| Review Proposals, award work |
|| UX improvements on top of existing Kudos Widget |
|| Display all Kudos |
|| Create Kudos |
|| Interact with Kudos |
|| Display details for a Kudo |
|| Tags / Categories |
|| SBT integration |
|| IAH integration |
|| Limit # of Kudos sent each week |
|| Kudos expire after X months |
|| Delete Kudos |
|| Administration features |
|| UX iteration that required smart contract |

### Audit

<!-- Identify if this widget needs an audit. Does it store sensitive information, transfer tokens, or have a middleware layer? Consult the Security Workgroup if needed. -->

Contract is low risk until reputation gained with Kudos grants access to funds without human approval. When we see significant adoption/integrations then we can dedicate funds for a formal audit. 

## Open Questions

<!-- Topics not covered in this document that need to be addressed in a meeting or async -->

Please include your knowledge & opinions via PR

**Q:** Should users be able to delete Kudos assigned to them? 

**A:** @starpause: To begin with I think it's good enough for administrators to have that right. It may be a feature that only admins can delete (in cases of behavior against COC) but it's still appropriate for a kudo to appear even if a nominee doesn't desire it. One hypothetical situation would be a nominee who wants one governance seat so they get nominated for that & want to delete their nominations for any other governance seat to improve their chances of their preferred seat, even though they would be a better fit for another seat.

@kazanderdad: I would prefer if the recipient of a Kudo had the opportunity to set their profile to either A) accecpt any kudos as received but with an option to remove unwanted kudos, or B) require my approval before an incoming Kudo is accepted. I would speculate that most people will allow incoming kudos, assuming that they are all positive, but that some people may wish to add a review step, perhaps after they had a negative esperience as targets of spam attacks. 

**Q:** Should we use Social DB for upvotes?

**A:**

**Q:** Should we issue SBT when someone gives a Kudo (Con: Feels spammy, costs more)? Or when someone claims their SBT after reaching a # of upvotes (Con: Less SBT will be issued)?

**A:** @kazanderdad: Simly counting and displaying the number of Kudos received can be achieved in other ways (e.g. indexing) and automated into a separate widget that folks can show on their profile page. Minting every kudo seems unneccessary. The reason a user might want to mint SBTs would be to increase reputation in a more meaningful way, to get access or unlock new opportunities. As such, minting Kudo SBTs should be implemented together with the concept of Categories, where the admin of a Cateogory can set the required count beore minting is allowed. Example: User requires 3 kudos in the "HoM Nominee" cateogry before they can mint an official "HoM Nominee" which unlocks them to become electable in votes. But the same user might require 20 "Dev Superstar" Kudos before they can mint a "Dev Superstar" SBT, which unlocks access to some exclusive club.

**Q:** What happens when a Kudo expires? 

**A:** @kazanderdad: I suggest they should be hidden from default view, but the UI allows users to change the filter and display them if needed.

**Q:** What happens when a Kudo is deleted? 

**A:** @kazanderdad: I suggest they should be removed entirely, no longer exist in the registry.

**Q:** What happens when a Kudo is not accepted by the recipient (assuming recipients has selected to not auto-accept incoming Kudos)? 

**A:** @kazanderdad: I suggest they should not be visible to anyone except the recipient. For the recipient they should appear in an inbound queue as "pending" to be either approved or deleted.

**Q:** Is commenting limited to verified humans?

**A:** @kazanderdad: Yes. I think of verified human as spam protection. There are several trolls on NS who will put out very negative comments. Kudo is supposed to be a very positive experience. If we allow anons to post negative comments then it will ruin it for many users. As a user of the Kudos widget I should be able to set who can comment: Only accounts that I follow, or only verified humans, or any account.

**Q:** Who would "follow a kudo" and why? What notifications would such a follow recieve? 

**A:** @kazanderdad: As the recipient I should by default be following my own Kudos, and this should result in all new comments showing up in my feed. If I follow another user, then the Kudos that they receive should also show up in my feed. Not sure if this means users should be able to follow an individual Kudo?

**Q:** Do we make one widget for Nominate, Recognize and Endorse, or should we rather make three different forks? 

**A:** @kazanderdad: The structure is remarkably similar between the three, so could easily be in one widget. However, the purposes are different, and in the spirit of composability I think I'd prefer to have three different forks with different names. The Kudos/Recognize categories should be pretty static over time, while the Endorse will change as new jobs emerge and for Nominate the categories could change with every new congress and every new DAO that wishes to use voting. Furthermore, the Nominate version of the widget may have added requirements, e.g. to facilitate interacting with the voting contract.

**Q:** What threshold can we define for when an audit is appropriate? 

**A:** TBD


## Glossary & References

<!-- Are there any relevant PR comments, issues that led up to this, or articles referenced for why we made the given design choice? Acryonyms or other terminology that could be misunderstood? -->

**Kudo** (_plural: Kudos_) is a form of a recommendation to share a gratitude or achievement shared between humans.

**I Am Human (IAH)** Protocol for verifying personhood. 

- [dApp on testnet](https://i-am-human-dev.netlify.app/) 
- [dApp source](https://github.com/near-ndc/i-am-human-dapp)
- [Protocol](https://github.com/near-ndc/i-am-human)

**Soul Bound Token (SBT)** Soulbound Tokens (SBT) are non transferrable NFTs that have a recoverability mechanism and a soultransfer mechanism. SBTs are well suited of carrying proof-of-attendence, proof-of-unique-human "stamps" and other similar credibility-carriers. See more here: https://github.com/near/NEPs/pull/393

**Near Social (NS)** We use NS to describe any Gateway built on BOS, such as https://near.org/ or https://alpha.near.org/ or https://near.social/#/. Read more about it here https://docs.near.org/bos/overview

**Widget** Technically a widget is the minimum unit of a frontend on BOS. Widgets are composable: they allow you to include an existing component (inclusive of other widgets) into your code, thus enabling to create complex applications by composing components.

## Changelog

<!--
Points for reviewers to consider:

- Be pragmatic: Is there enough information to begin coding? Practically, implementation will reveal the unforeseeable. This doc can evolve to record those issues/resolutions.
- Wide angle view: Do you know of overlapping projects? Are there OKRs or other non-technical forces that would push/pull priority?
- Optimization: Describe alternate approaches and why they are better. Use Caveats section for approaches under consideration, even if they are ultimately abandoned. 

--> 

**Authors & Reviewers:** @starpause, @robert-zaremba, @htafolla, @KazanderDad 
*Please insert your name here if you do review the document.*

| Ver. | Date       | Author          | Changes Made                             |
| ------- | ---------- | --------------- | ---------------------------------------- |
| 0.1.0   | 2023-04-21 | @starpause      | Initial draft of the document            |
| 0.2.0   | 2023-04-23 | @starpause      | Merged prior writting by @robert-zaremba from his [Github version](https://github.com/near-ndc/gwg/pull/1)                   |
| 0.3.0   | 2023-04-25 | @starpause      | Addressed review comments, formated sections to more closely match [template](https://github.com/near-ndc/gwg/blob/main/TEMPLATE-SPEC.md)    
| 0.4.0   | 2023-05-10 | @kazanderdad    | Clarifying some of the open questions, finalized doc for RFP

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
