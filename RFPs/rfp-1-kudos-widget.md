---
RFP ID: 2
Status: Published
Category: NEAR Social
Created: 2023-05-11
Replaces: 
Requires: spec-1-kudos.md
---

# RFP-2: Kudos Widget for NDC

## Summary

Request For Proposal

**NDC is looking for proponents to submit their proposals to develop a "Kudos" widget on near.social.**
  
## Spec
  
Kudos is a widget that will enable people to build on-chain reputation. The widget will allow any verified human to nominate, recieve, and interact with Kudos on Near Social. 

Special attention is required to spam protection in order to ensure that people percieve interacting with Kudos as a very positive experience. Key spam protection concepts include:

- setting preferences for who can send me kudos and who can comment on them
- allowing recipients to not accept and/or delete unwanted Kudos
- requiring that users are i-am-human-certified before they can send or comment on Kudos

Please refer to this link to see the full specification for this RFP: **[spec-1-kudos.md](https://github.com/near-ndc/gwg/blob/main/specs/spec-1-kudos.md)**

## Expected Timeline

1. Proponents post their intent to respond
    - Location: Comment on [NDC Gigs](https://near.social/#/neardigitalcollective.near/widget/Gigs)
    - Deadline: **Wednesday May 17, 2023**
2. Proponents post their questions
    - Location: Comment on [NDC Gigs](https://near.social/#/neardigitalcollective.near/widget/Gigs)
    - Deadline: **Wednesday May 17, 2023**
3. GWG Technical WG responds to questions 
    - Location: Comments on [NDC Gigs](https://near.social/#/neardigitalcollective.near/widget/Gigs)
    - Deadline: **Thursday May 18, 2023**
4. Proponents submit their Proposals 
    - Location: 
      - Create your own folder in [this structure](https://github.com/near-ndc/gwg/tree/main/RFPs/submissions/rfp-2-kudos) and upload your content there (pull request). 
      - A public post of your proposal is required, with the exception of commercial details.
      - Commercial details can be emailed separately to [neardigitalcollective at gmail dot com]
    - Deadline: **Sunday May 21, 2023**
5. A GWG Panel awards work to successful proponent
    - Location: Comments on [NDC Gigs](https://near.social/#/neardigitalcollective.near/widget/Gigs)
    - Deadline: **Tuesday May 23, 2023**
6. Expected delivery time: **June 23, 2023**

## Selection Criteria

The Governance Working Group will review these proposals and post an Attestation to the various proposals as part of making the selection. ‍ We may also select a runner-up in case the primary proponent does not pass KYC.

Evaluation criteria will include

- Solution architecture
- Team’s Technical Capabilities, completeness
- Team’s BOS experience
- Project approach (including post-go-live support)
- Total price
- Proposed Timeline
- Customer success practices

The GWG should either be consulted as part of the design of the widget, and/or reserves the right to approve the designs.
  
## Open Questions and Comments

The spec includes several mentions of "TODO". It is part of the scope of this RFP that proponents are responsible for completing them and submit any designs for review and approval. We will commit to prompt 24h review cycles (and in the absence of prompt reviews you are allowed to mvoe ahead with building)

The spec also contains a section with discussion on a few open questions. We would expect a succesful proponent to help us close these items in a collaborative way.

Three "flavors" of Kudos are discussed in the RFP. If timeline becomes a factor of concern then it is OK to deliver the "Recognize" and "Endorse" flavors later, as long as the "Nominate" flavor is delivered before June 23.

In the current design it is ok for devs to query the i-am-human registry individually. A future improvement potential will be to interact with an indexer rather than directly with the smart contracts.
  
  
## References

NA
  
## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
