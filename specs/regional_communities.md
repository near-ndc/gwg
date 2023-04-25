---
Spec ID: 2
Status: Draft
Category: NEAR Social
Created: 2023-04-19
Replaces: https://github.com/near-ndc/widget-specs/blob/main/specs/regional_communities.md 
Requires:
---

# Spec-2: Regional Communities Widget
This community-driven spec is a collaborative community-led effort to create a functional specification for a widget to be developed. The goal is to bring clarity and alignment to the deliverables for developers to deliver a functional widget that meets the requirements.

  
## Summary
This widget will help users find, join and interact with communities that are in their region, speaks their language, and/or are aligned with their interest. It provides a natural way of growing all the regional communities within NEAR, emphasising belonging and natural community growth rather than competition.

Regional Communities are a crucial component of growing the NEAR ecosystem. People don't join because of the tech. People join because of other people. People organize themselves and interact with each other. People crave networking and a sense of belonging. All of this can be done through regional communities. This spec for a widget enables an organically evolving structure of related commmunities, and it allows for creating varied and multifaceted communities such as (illustrative examples only):
- Near Stockholm "Degens" in Swedish
- Near Africa "DeFi and Refi" in English
- Near Global "Devs" in Spanish
- Near Florida "Gaming & Events" in Spanish
- Near Miami [all tags] in Spanish
- Near Miami [all tags] in English

  
## Other potential names for this widget:
List of possible names:
- My Communities
- My Community
- Regional Community
- Regional Communities
- Community Finder

  
## Context & Challenge
It's currently really easy to create a new community on near.social. All you have to do is create a new account with your community name and start promoing it. But this unstructured approach comes with a lot of challenges:
  - If you want to start a new community you have to start from scratch, and you have to build your own membership base from scratch.
  - If you're simply looking for a community to join, it's not easy to find one in the unstrucctured mess
  - There is competition by default". If two or more communities were formed with the same or similar scope (by accident or otherwise), then they are bound to try and attract member following from the same community base, potential members who werent interested in the choice from the beginning but just wanted to find their one "home"

Most communities form around some intersection of geography, language and vertical constellation / interest. But they are not getting any help in finding their place in these dimensions. Similarly, new users looking for a community to join have a hard time finding the right community in the right intersection.

There is no natural evoution provided for communities that grow "too large" or too diverse. If they want to split then the only option is to create a new sibling- or child-community, again from scratch. Similarly, there is no natural way of merging two communities without having to agree to delete one (with all it's history) and ask the members each to manually move to the new community.


## Scope and Requirements

Describe:
- Expected functionality.
- Potential security issues and requirements.
- User profile description. Who is the user? How she/he is expected to us it?
- Requirements, assumptions and dependencies (internal and external).
- Outline identified potential problems and roadblocks related to building the solution.
- Optionally: Budget limit.

### Scope
<!-- Define the scope and potential phases of the widget -->
In scope
- All geographies
- All languages
- All verticals
- All human users interested in joining, forming or managing communities of likeminded

Typical resons to come together in a community:
- Networking
- Learning from each other, discussing
- Support and help each other
- Find new friends, build meaningful relationship

What is NOT within the scope of regional communities? Groups that are not bulding lasting relationships, groups where the only purpose is to facilitate one-time or temporary transactions.
- Buy and sell groups
- Job listing / job search
- Gig economy

### Expected Functionality
<!-- What are the Minimal Viable Requirements (MV)  the widget should meet to be considered complete? -->
The minimum requirements the widget should meet include:
- Built on BOS / Alpha / Near.social
- Can have a single admin owner, several owners / admins, or a DAO as an owner
- Members can post messages within community
- Messages posted within communities that I follow will show up in my stream
- Supports all three dimensions
   - Geography as a hierarchy (each community has one geography, and has a parent with a higher level geography)
   - Language as a flat list, single-select
   - Consteallation as tags, multi-select
- Allows the owner to split the community on one of the dimensions
- Allows the owner to reassign ownership fully, and allows the owner(s) to give ownership rights to others

### Backwards Compatibility
All proposals that introduce backwards incompatibilities must include a section describing these incompatibilities and their severity. The doc must explain how to deal with these incompatibilities or the set of requirements to for the backward compatibility to be discussed in a submission. Submissions without a sufficient backwards compatibility treatise may be rejected outright.

## Phases
<!-- Do the project have multiple phases? Identify a high-level summary of each phase. -->

### Phase 1: MVP
- The app owner can create global parent communities for each Constellation
- Users can find their community, assign them selves membership permissionlessly (similar to "follow")
- Members can start posting messages to the Community board.
- Members can perform a sibling split along one of the three dimensions
- Members can perform a child split along one of the three dimensions, 
- Member executing the split will become the owner of the new Community

### Phase 2: Admin Functions
- Admins can assign other admins
- Users can request core memberships
- Admins can approve core memberships
- Admins can warn, silence and ban users

### Phase 3: Enable voting
- Members can request a vote on splitting the Community
- Members can launch simple EasyPolls
- Members can vote in a new core user
- Members can vote to warn / silence / ban an offending user


## Use Cases

## Actors
<!-- List all collections that will use the widget. -->
- Members
   - Admin members
   - Core members
   - Home members
   - Hangaround members
- Non-members
   - Non-member humans
   - Non-member users

## Actions
<!-- List the actions each collective will take individually. -->

### Find and Join a Community
Finding a community aligned with my interests should be very easy. It's a core concept of this widget and serves to get people into open and collaborative communities rather than creating competing factions.

Searching for communities should be possible through a few different ways
- Search by map. Zoom into a map and update the list of available communities accordingly
- Seach-as-you-type.
   - Search by fuzzy search of geographies. Start typing in a city, country or region and all available options are shown. 
   - Search by fuzzy search of constellations. Start typing in a constellation and all available options are shown.
- Select you language, which updates the available communities. Default language is English.
- Any combination of the above will further narrow the search


### Approve a new Community member
Approvind a new community member could be as simple as a "follow back" by the owner of the community or someone who has been given the keys to control the community account. 

It is recommended that only human-verified accounts be allowed to become members, as a minimum requirement.

A drawback of this approach is that there is no vote. Any single admin can follow or unfollow, which may be too arbitrary for some communities. Another drawback is that the "follow" feature would no longer be available to use for its originally intended purpose. A more structured approach to membership may have to be contemplated. Optins include:
- user follows the Community and automatically becomes a member as long as some criteria are filled (e.g. is human verified and accepts the code of conduct) => Preferred
- user applies for membership, followed by a majority vote to approve the application
- membership is open to anyone without approval
- membership is open to anyone, with the restriction that they can be a full member of one and only one community

This author recommends a combination, whereby there are four types of membership:
1. Home Membership - each user can define their one and only "home" membership = the community that is most closely aligned with them. This can be done without approval from the community, but each user can only select exactly one home community (or not make the selection).
2. Hangaroud Membership - any user can be a hangaround. This feature is similar to a standard "follow" and should be the default membership for most communities.
3. Core Member - the user has been approved in some way (by community vote or admin vote) to be a core member of the community. This option should not be a default option, but could be a possibility to enable for some communities that desire this option.
4. Admin Member - the user has admin rights for the group

It is this authors recommendation that commuinties be open for anyone to join and that applications are "accepted by default". If limitations are desired then it's better to use the "silence the member" feature than to go to "accepted pending approval" which signals a closed or restricted society.

### Split a Community
Instead of creating a Community from scratch, splitting an existing Community into two should be the default way of creating new communities. This is a core feature of the Community widget design.

When splitting a community, the key question to ask the user is this: "Along which dimension do you want the split to occur: Geography, Language, or Constellation?"
- If splitting along the Geography dimension then ask also if it's a sibling-split of child-split. 
   - Example of sibling-split: [Near Sweden] splits into [Near Sweden] + [Near Norway], which becomes the sibling Community with the same parent
   - Example of child-split: [Near Sweden] splits into [Near Sweden] + [Near Stockholm], which becomes the child Community of the preceeding community
- If splitting along the Language dimension then 
   - Simply ask which other language the new community should serve, which becomes a sibling Community. Example: [Near Switzerland English] splits into [Near Switzerland English] and [Near Switzerland German], both of which has the same parent [Near Eurppe English]
- If splitting along the Constellations dimension then
   - if there is already a constellation picked, then simply ask what constellation the new Community should serve and it becomes a sibling Community. Example: [Near Somalia DeFi] splits into [Near Somalia DeFi] + [Near Somalie Gaming]
   - if there was no prior constellation picked, then ask which Constellations the new Community should serve and becomes a child Community. Example: [Near Uganda] splits into [Near Uganda] + [Near Uganda NFT]
- The split has to be along at one and only one of the dimensions. The split cannot proceed unless there is an actual change proposed, one that will make the new Community different by design from the original Community from which it splits.

Any member can request a split, it must not be approved by the admins. 
- The members voting should be asked a few questions
   - Do you approve of this split proposal?
   - If so, would you want to become a member of the new Community? Would you voluenteer to also become and admin?
   - If so, would you also want to stay a member of the current community?
- It is this author's opinion that a minimum of three to five other members should approve the split and also wish to become a member of the new Community for it to take effect
- Once sufficiently approved, then the split should immediately be executed. It should not require admin involvement or approval, because we want the split to be a natural, organic and permissionless occurence.

The user requesting the split trigger an automatic vote to approve the split. If the request is approved then the original requestor will also be the first leader of the new community by default. 
 
After splitting the community, then each member should be given a choice as to which of the resulting communities they wish to belong to, or if they wish to be a member of both.

### Merge two Communities
We don't anticipate this to happen often, but it could be the case that two communities have shrinking membership and would like to merge to increase the total membership in one Community.

A merge proposal should be approved by majority vote in both communities before it is allowed to happen.

It's not easy to design rules for how the merge should be executed, based on the complexity of possible permutations of the pre-merge Communities. It seems plausible that merge power should not be given to regular users but could be given as an admin power to a dev / superuser. The alternative would be that merging not be supported, in which case the community will manually have to move from and abandon one community in favor of the other.

### Interact with my Community
Members should at minimum be able to post messages within the community which become publicly readable to anyone regardless of membership status, and where other members are allowed to comment on the message.

Messages posted on boards that I follow should show up in my personal feed in chronological order. But they don't show up in the feed of users who are not members and don't follow the community.

Members or admins (depending on Community settings) should be able to post polls for the community, which only community members are allowed to vote in.

As a member I should be able to see all other members listed in a sidebar, along with their membership / admin status.

### Ban a user from a Community
Banning is a strong power and should be used very restrictively. We suggest milder and more human forms of restricting users that are not following the code of conduct for a community. 
- Issue a warning for breach of code of conduct
- Temporarily silence the user for a day
- Temporarily silence the user for a week
- Silence the user until un-silenced (perhaps after taking some corrective action)
- Banning the user with chance of reapplying
- Banning the user with chance of reapplying (permanently)

It is this author's opinion that silencing the user is a much preferred method over banning them. Silencing allows the user to keep following the activitiy of the community and still feel like they belong there. It creates less animosity and makes the world a nicer place. Consider not implementing the banning feature.

These measures can be designed such that each increasing level of banning must be preceeded by the milder forms before it can be implemented. E.g. must silence the user for a day before can silence them for a week.

### Manage a Community
Communities should be open and welcoming, not closed for elite members only. We should design them such that members have as much powers as possible, and that admins are given as few god-like options as possible.

Some management functions include (non-exhaustive list):
- Add / change / delete Constellation tags of the Community (note: having no Constellations is the same as having all Constellation tags)
- Change the name of the Community
- Changing the code of conduct
- Changing the rules for gating and/or auto-approving membership
- Changing the annual membership fee
- Changing the Geographical parent 

One way to achieve decentralized leadership is to give admin powers to the community by majority vote, where any member can propose a vote and any member can vote on them, and where the proposal is automatically executed following a majority vote. 
- Consider making it a requirement that communities are owned and managed by an Astro-DAO with a minimum of 5 council members, rather than an individual owner.
- Consider forking the relevant parts of the Sputnik DAO codebase into this widget, to manage the Community by vote.

The question on who leads a community is often a contentious issue. Strong leaders can be super helpful but can also inhibit other aspiring leaders. Weak leaders can fail to get the community going. Corrupt leaders can squander away the money the community might have a stake in. It's not easy to design a generic tool that will allow the community to best choose their leader(s) across a variety of cultures and complex scenarios.

### Create a new Community
The widget design should inherently discourage users from creating new communities. Instead, users should be encouraged to...
- Find an existing community to join that fits their interest
- Find an existing community with approximate match, and suggest them to increase their scope to include their interest
- Find an existing community to join, and suggest they split out a child- or sibling communit that fits their interest

By taking the above actions, the following benefits would be realized:
- We discourage creating overlapping communities unneccessarily
- The new communities come with a default following and get a default parent or sibling
- Less need to start from scratch finding members, as a seed membership would come along from the preceeding community
- Create an audit trail of community growth
- Natural evolution and growth of the various dimeensions (geography, vertical, etc)

If the developers decide anyways to give an option to create a new community from scratch, then the following should be required actions:
- Select a geographical area that the community covers, selecting from a list of already existing areas, preferably from a hierarchy of existing areas (global-continent-country-region-municipality-city)
- Select which one language the community will be using
- Select which vertical constellation the community will be focused on (multiselect, optional). If no constellation is selected then the geographical area covered should be very small (i.e. country or below)
- The creator of the community becomes the default Council member by default

## Actor/Action Matrix
<!-- Describe which action is done by which actors. Feel free to use a table format or provide your own graphics. A "swimlane process chart" often works well here. -->
REPLACE THIS TEXT

|         | Admin | Member | Non-member Human | Non-member User |
| ------- | -------- | -------- | -------- | -------- |
| Find and Follow Community |          |          | Yes         | Yes         |
| Join a Community |          |          | Yes         |          |
| Approve a new Community member | Yes         |          |          |          |
| Split a Community | Yes         |          |          |          |
| Merge two Communities | Yes         |          |          |          |
| Interact with my Community | Yes         | Yes         |          |          |
| Ban a user from a Community | Yes         |          |          |          |
| Manage a Community | Yes         |          |          |          |
| Create a new Community |          |          | Yes         |          |

## Data Architecture
<!-- Describe the data architecture and principles -->

### Geographies
To prevent unmanageable complexity in the geography dimension, we propose that there should always be a "trunk" that sets the direction into narrower and narrower geographies, from which the language-branches and constellation-branches can expand. The trunk concept is the family of communities that don't have a constellation selected and that has English as their language. Only communities with these characteristics are allowed to create new "child" geographies. Conversely, any Commmunity that either has a non-english language or has narrowed down their Constellation will not be allowed to create new geographies. Instead they will be confined to only select pre-defined geographies from the trunk. 

We should create an initial set of "trunk" Communities
- Global
   - North America
      - Canada
      - USA
   - Asia
      - Indonesia
      - Japan
      - South Korea
      - Russia
      - Vietnam
   - South America
   - Africa
   - Europe
      - DACH
      - France
      - Portugal
      - Spain
      - Ukraine
   - Oceania

### Languages

English should be the default langugage for all new Communities.
- It should be possible for the Community admins to change the language
- When a member proposes as split they have the option to split due to wishing to cover a different language

The initial list of optional languages should include the following major crypto-dominant languages:
- Chinese
- French
- German
- Indonesian
- Japanese
- Portugese
- Russion
- Spanish
- Vietnamese

### Constellations (verticals)

The initial list of Constellations tags should include the following:
- Gaming
- NFTs
- ReFi
- DeFi
- Devs
- Governance
- Degens
- Social
- Events


## Consequences

This section describes the consequences, after applying the decision. All consequences should be summarized here, not just the "positive" ones.

### Positive

### Negative

### Neutral

## Open Questions and Comments

- potential future improvements
- summary of open discussion

## References

Are there any relevant PR comments, issues that led up to this, or articles
referenced for why we made the given design choice? If so link them here!

- First version of this document: https://github.com/near-ndc/widget-specs/blob/main/specs/regional_communities.md

## Changelog
2023-04-19: Document created
2023-04-24: Moved location, updated to new format 

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/)




  
  
  
