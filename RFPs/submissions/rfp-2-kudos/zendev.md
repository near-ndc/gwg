---
RFP ID: 2
Status: Published
Category: NEAR Social
Created: 2023-05-25
---

# RFP-2: Kudos Widget for NDC

## Summary
App build on BOS, using SocialDB. It will integrate i-am-human. So idea is no metter how many wallets user create, user account will depeand of i-am-human contract 
The widget will allow any verified human to nominate, recieve, and interact with Kudos on Near Social. 

## Context 
On the blockchain-based social platform, Near Social, users need a way to recognize, appreciate, and validate each other's contributions in a consistent, tamper-proof, and meaningful way. The challenge lies in the lack of an integrated, on-chain mechanism to manage and verify such reputation indicators.

Furthermore, spamming is a significant issue in digital reputation management, which, if not addressed adequately, can degrade the quality of interactions and user experience. Users need the ability to control who can acknowledge their contributions and comment on them to maintain a positive and spam-free environment.


## Proposal 

App will have dynamic fields and protected routes based on Users role
We will have 4 roles
 - Visitor 
 - User
 - Humans
 - Admin ( I will need some clarifications for this role) 


App will be created on BOS using SocialDB.
This app will contain 
- Homepage (
  -- Dynamic Header
  -- About Kudos ( What & Why )
  -- List of latest kudos (aprox 20/30 per page)
  --Kudos filters ( kudos can be filtered by tag or user )
)
-- Single Kudos page 
-- Create New Kudos 
-- Profile Page   
-- Admin Profile Page/Settins 

**Diagram with users flow & app permisions can be found [here](https://miro.com/app/board/uXjVMGLmjJ4=/)**


## Expected Timeline

I will split this kudos task in 2 versions. 
First version will have basic functionalities. 
Second version will have extra functionalities, such as notifications, admin page improvement, animations, expiration time. 

### Version 1
1. Design ( Mobile/Tablet/Desktop) UI & UX 
  - 2 Weeks - 400 NEAR
2. Setup Project 
  - define how interface will looks in SocialDB ( SocialDB )
  - define routes ( BOS )
  - define Widgets ( BOS )
  -- 2 days 
3. Homepage
  - What is Kudos + Recent Kudos List - 1 week
  - Filters (1 week) 
  - Search (1 week)
  -- 2 - 3 weeks 500 NEAR 
4. Single Kudos Page
  - Infos about single Kudos
  - if user is one who created it it can be editable 
  - share link 
  - upvote/reaction
  - should user be able to remove upvote
  - - 2-3 weeks ( Blockchain + BOS) 350
5. New Kudos Page 
  - Form where user can create new kudos
  - define tags / categories
  - - 2 weeks ( Blockchain + BOS) 350
6. Profile Page
  - Received Kudos
  - Pending Kudos
  - Created Kudos -> Edit kudos 
  - Filters 
  - 3 weeks ( Blockchain + BOS) 400 NEAR
7. Header + Footer 
  - Dynamic renders based on props ( BOS )
  - - 1 week 150 NEAR 
8. Settings & Admin page
  - Need to figure out some things about it
  - will we have predefined tags
  - who can become admin 
  - how you can become admin 
  - what do you have when you are admin
  - how you stop beeing admin 
  - - approx 2 weeks 500 NEAR 
9. 5. Limit # of Kudos sent each week
  - Create limit for each user, create modals/popovers when user reach the limit (BOS + Blockchain)
  - 1 week  - 200 NEAR 
10. Delete Kudos - we need to define who can delete kudos and how
11. Include SBT - Need more info about it 


**Diagram with users flow & app permisions can be found [here](https://miro.com/app/board/uXjVMGLmjJ4=/)**

Aprox time for desigh: 2 weeks - 400-500 NEAR 
Aprox time for development (for things which we know): 14 weeks -> 2 devs ( 7-8 weeks each ) -  2300 NEAR 

Price and time frame are not fixed, after clarifications we can talk more about it. But this is like initial offer

**Please be aware that it is not our full-time commitment. We will be dedicating approximately 15-20 hours per week to the development and implementation of the Kudos widget. Consequently, some phases of the project may require a slightly extended timeframe to ensure that the work is of the highest quality and meets all specifications and requirements**


### V2 
Plans for version 2 are 
1. Notifications ( we can use pagoda console to get info when someone create kudo and inform receiver )
2. Gamification, for each received kudos/upwotes/reaction you can get points.
3. Send account SBT Badge for each Kudo
4. expiration time of kudos -> I think that we will need backend here for cron job, so question is who will host backend, can we do this in decentralized way, etc. 
5. Administration features ( not sure what will admin has )
6. Transitions & animations ( depeands of keyframes on BOS, currently I find out that it doesn't work on BOS)


**We can move tasks from V2 to V1 or the opposite.**

# Team 

Currently my plan is to have 3 people on this gig. 
1. Senior designer who will design ( My colleague, working with me for 3 yrs )
2. Frontend Developer ( My colleague, working with me for 5 yrs now. we are well-coordinated and work great together  )
3. Myself ( Discord & Telegram: ZenDev, twitter: https://twitter.com/CryFamBrother )


## Open Questions and Comments

1) What is more preferred - to use SocialDB or create own smart contract ?
2) Difference between tags & categories
3) Explanation about admin role
4) Notifications. If we want to use Notifications API from web browser we will need backend. 
5) Expiraton -> For counting time we will need cron job, so again we will need some backend. Who is owner of it, but maybe there is solution on NEAR chain which I am not avare of.
6) Can we get some assistance from Near Social team? 
7) Can we use pagoda console? ( not sure why that will be problem but good to know at the beginning) 
8) How actually SBT will be connected with kudos, and where it will be minted. 


## Final Thoughts
I perceive this project as a unique opportunity to extend my expertise in BOS and SocialDB technologies. The Kudos widget, beyond being just a project, offers the potential to create something exceptional that will be directly used and appreciated by the user community on Near Social.

The implementation of this widget aligns with my professional objectives, allowing me to contribute significantly to the user experience and overall ecosystem. The realization that I am creating something that will enhance user interactions and recognition on the platform is highly motivating.

Furthermore, this project stands as a stepping-stone for my growth as a developer . The goal is not merely to deliver a successful project but also to contribute to the strengthening of our digital community. 


## References
[Widgets on Near Social](https://near.social/#/mob.near/widget/ProfilePage?accountId=7418d5cb7d7657e526b8bccf28750939105828d0f5b34a7254bd107477d84a2c) 

[paperboat](http://paperboat-dev.breyta.is/) - NFT Portfolio & analytics tool. Currently only accessable with our NFT, feel free to ping me if you want to check it out 

[ratsja](https://breyta.is/work/ratsja/) - Ratsjá uses neural networks to analyze all news on online media in Iceland: Who is involved, in which sector etc. With further training, the neural network can detect attitudes towards the subject of the news and also send users a message if the news about the company goes viral on social media.
