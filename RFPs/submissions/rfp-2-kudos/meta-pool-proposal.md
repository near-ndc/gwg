# 🏗  KUDOS widget for NDC - Meta Pool Submission

# RFP-2 Meta Pool

## 👨‍🏫 Introduction & Motivation

A reputation system is mechanism designed to assess and quantify the trustworthiness, reliability, or quality of entities, such as users or services within a given network or community.
Reputation is a need in the context of Near Social. Kudos can be used to build reputation by issuing SBT.

One of the challenges for a reputation system is to be sybil resistance, that is a to be resistance to sybil attacks, which involves an user forging multiple identities to manipulate reputation scores, for example.
By incorporating proof-of-personhood mechanism (i-am-human) in multiple stages we can prevent fraudulent activities and keep the protocol secure.

Another challenge to face for the reputation system is to be spam free. Using proof of personhood is not enough to protect a system from abuse.
There are many alternatives to adress that, we propose the following.

* Limit that activity: Any human can send maximum 14 kudos per week. The quota will reset every Sunday at midday UTC (12:00). The quota will be a parameter and the admin will be able to change it in the future.
* The target user should be in control of the Kudos they recieve. Unwanted Kudos can be removed from display by either the nominee or nominator.
* The target user should also be able to set their preference to either auto-accept incoming Kudos to their profile, or require a manual review & approval before accepting incoming Kudos
* The target user should be able to set their preferences to accept incoming Kudos from endorsed users, that is users that already have a specific endorsed sub-category, eg: Developer, Community Builder, Product Lead, Marketer, Project Mgr, Sales, Researcher, Architect, Data Scientist, Creative ... 

## 🏗 Proposed Solution

Implement an app that will manage diffent kinds of Kudo categories:

1. "Standard Kudo" for general social awarding. Sub-categories include: Thank You! Good Job! Impressive! Excepional!...
2. "Endorse Kudo" for attestation on specific skills. Sub-categories include: Developer, Community Builder, Product Lead, Marketer, Project Mgr, Sales, Researcher, Architect, Data Scientist, Creative ...  
3. "Nominate Kudo" for nominating your self of backing someone else in their candidacy for some sub category. Sub-categories include: House of Merit, Transparency Commissson, Counsil of Advisors, Creatives DAO, Marketing DAO

App will provide views/pages for 3 differents roles:

* Visitors
* Users
* Admin

## Timeline and deliverables

Within 1 month, we will have:
A fully functional Kudos app, will provide views for the Users, Admin and Visitors. 
A fully functional Kudos creation for Standard, Endorse and Nominate categories.
A fully functional implementation of a custom Notification feed. Allowing Kudos comments and upvotes.
A fully functional integration with I Am Human (IAH) Protocol for verifying personhood.
A fully functional implementation for Kudos minting into SBT.

### End of week 1

* Scheduled some meetings with the NDC team and/or IAH team to review the proposal and ensure technical awareness to complete an architecure design. 
* UX review on top of existing Kudos Widget
  
### End of week 2

* UX - Design explorations
* Smart contract implementation
* First version of 

## End of week 4

* UX, branding and visuals
* Final version of Kudos app

# Budget

$ 11,800 - Payment for development efforts (frontend and contracts). Estimated a total of 280 hours.
$ 2,800 - Payment for designer efforts on UX, product branding and visuals. Estimated 80 hours.

## References

* Meta Pool website
* Meta Staking Vote on Near.social - inspired the Kudos widget
* Common Components Library - won the 1st prize on Near Social Hackathon.
* Badges Back Office - a solution for issuing and managing badges on Near.Social

**Badges Back Office** is a prototype solution for issuing and managing all your badges in one place, which can serve as a use case for building on chain reputation on Near.social community.

It features include:

* Viewing badge information
* Identifying badge owners
* Assigning badges using advanced people search queries
* Creating new badges
* Editing badge data
* Our previous work on BOS has provided us with valuable insights and knowledge that can be leveraged to enhance the proposed solution. We believe that our diverse range of experiences and achievements uniquely position us to deliver an exceptional outcome for this project.
