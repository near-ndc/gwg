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

## Scope of Work

Finalize the features and UX for launch, complete integrations to IamHuman and SBT standard.

## Requirements

- Tag any BOS/NEARSocial/Discovery account
- Notify the account of the Kudo via the Notifications API
- Upvote a Kudo
- Comment on a Kudo
- Show all comments
- Integration with IamHuman
- Send account SBT Badge for each Kudo

### Phases

A prototype exists and @starpause will finalize the spec and ux design.

- Finalize UX design add a table view
- Integrate with IamHuman
- Integrate with SBT Standard

## Use Cases

Any account registered on BOS/NEARSocial/Discovery will be able to use the widget to send Kudos

## Actions

- Send Kudo
- UpVote
- Comment
- Share

## Tech Spec

### Functions

- isHuman
- mintSBT

### Process Flows

> REPLACE THIS TEXT

### Screens

> REPLACE THIS TEXT

### Dependent Widgets

<!-- Does the widget interact with other widgets? -->

##### Main

[Kudos.Styles](https://near.social/#/neardigitalcollective.near/widget/Kudos.Styles)

[Common.Compose](https://near.social/#/neardigitalcollective.near/widget/Common.Compose)
[Kudos](https://near.social/#/neardigitalcollective.near/widget/Kudos)
[kudoBox](https://near.social/#/neardigitalcollective.near/widget/kudoBox)
[FollowButton](https://near.social/#/neardigitalcollective.near/widget/FollowButton)
[MainPage.Post.Header](https://near.social/#/neardigitalcollective.near/widget/MainPage.Post.Header)
[MainPage.Post](https://near.social/#/neardigitalcollective.near/widget/MainPage.Post)
[showCommentsButton](https://near.social/#/neardigitalcollective.near/widget/showCommentsButton)
