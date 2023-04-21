---
#: 1
Status: Review
Category: NEAR Social
Created: 2023-04-05
Replaces: --
Requires: --
---

# RFP 2: Kudos

# Summary

Kudo is a widget to build a reputation using SBT tokens and a network effect. Kudo is a form of a recommendation to share a gratitude or achievement shared between humans.

This widget will allow any verified human to give any other verified human a Kudo.

## Context

The goal of this widget is to foster and improve recognition and celebrations of individuals, nodes, projects, workgroups or collectives for their contribution to NEAR.
This will server as a fundamental MVP for Reputation and Badges and create a general widget that can be forked and used for many use cases

Other potential names for this widget:

- High Five
- Props

## Scope and Requirements

Kudo is a Soulbound Token. **ONLY Human Verified accounts** (through `i-am-human`) can issue and receive a Kudo.

Sending and receiving Kudos is a form of building up a social reputation and a recognition. However there are potential risks that the system will be misused.

### Kudo categories

SBT standard provides a notion of classes. We will use it to define Kudo categories. Initial set of categories is following: Developer, Community, Manager, Showman, ...

TODO: finalize the categories

### Spam protection

Using proof of personhood is not enough to protect a system from abuse. One user could attach a bot to his account and send thousands of kudos to other accounts (potentially to the same human account).
We propose to limit that activity: Any human can send maximum 14 kudos per week. The quota will reset every Sunday at midday UTC (12:00). The quota will be a parameter and we will be able to change it in the future.

Moreover, user should be in control of his Kudos. He will have a full right of removing an unwanted Kudo.

Kudo sender will have to set an expire time. To make it more useful, the contract will require that a minimum expire time is 1month.

### Smart contract management

Kudo contract will define a set of administrators which will be able to:

- create or remove categories
- adjust min expire time

### NEAR Social Use Cases

We define the following features which will use the Social DB smart contract with UI developed in Near Social:

- Account receiving a Kudo will get receive Near Social notification via Notifications API.
- Upvote a Kudo.
  Any human can upvote a Kudo (only when Kudo is not expired). One account can upvote any Kudo only once.
  Upvotes will be stored in the Social DB or in the Kudo SBT issuer (TODO: check what's better).
- Comment on a Kudo
  Any human can comment on a Kudo (only even if a Kudo expired). Comments will be implemented using existing Near Social widget.
- Near Social widget to show a Kudo with all comments.
- Follow Button to receive notification on new comments for a given Kudo.

### Phases

Finalize the features and UX for launch, complete integrations to IamHuman and SBT standard.
A prototype exists and @starpause will finalize the spec and ux design.

- Finalize UX design add a table view
- Integrate with IamHuman
- Integrate with SBT Standard

Any account registered on BOS/NEARSocial/Discovery will be able to use the widget to send Kudos

### UI

TODO: link to the screens

- [UI designs](https://app.visily.ai/projects/68d0d584-1866-4343-86b5-d1ab1bdef11d/boards/464535).

#### Dependent Widgets

[Kudos.Styles](https://near.social/#/neardigitalcollective.near/widget/Kudos.Styles)
[Common.Compose](https://near.social/#/neardigitalcollective.near/widget/Common.Compose)
[Kudos](https://near.social/#/neardigitalcollective.near/widget/Kudos)
[kudoBox](https://near.social/#/neardigitalcollective.near/widget/kudoBox)
[FollowButton](https://near.social/#/neardigitalcollective.near/widget/FollowButton)
[MainPage.Post.Header](https://near.social/#/neardigitalcollective.near/widget/MainPage.Post.Header)
[MainPage.Post](https://near.social/#/neardigitalcollective.near/widget/MainPage.Post)
[showCommentsButton](https://near.social/#/neardigitalcollective.near/widget/showCommentsButton)

## Open Questions and Comments

- Should we use Social DB for Kudo Upvote?

## References

## Changelog

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
