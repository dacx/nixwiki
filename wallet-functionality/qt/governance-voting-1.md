---
description: How to use your QT wallet to vote on proposals
---

# Governance Voting

NIX incorporated its decentralized off-chain governance system on May 25th, 2019. Creating an off-chain governance model allows for a light-weight method of governance by ensuring that users who secure the network have a say in the direction NIX takes. This system prevents unnecessary blockchain data storage while at the same time maintaining transparency.

Discussions concerning governance proposals can often be found in the \#governance [Discord server chat](https://discordapp.com/invite/HGuvDTW).

{% hint style="danger" %}
**Caution:** Please remember that anybody willing to spend 50 NIX can create a proposal. It is up to you to decide if the individual who created the proposal is trustworthy and will follow through with their stated intentions. **Please vote wisely!**
{% endhint %}

## Casting Your Vote

In order for a proposal to pass, 2 requirements from the voting community must be met within 15 days. These are:

1. At least 50% of eligible votes are cast.
2. At least 75% of cast votes are in favor.

Voting is currently only available using the QT wallet. To be eligible for voting on a proposal you must be staking from a bech32 address which begins with "nix1" and/or running a Ghostnode prior to the date the proposal you'd like to vote on was submitted. Staking from a p2sh address beginning with "N" does not qualify for voting so as to keep those stakers who do not wish to participate in voting from affecting the 50% cast votes requirement.

### Vote Weight

Your vote weight is determined by your  "nix1" \(Bech32 address\) staking/LPoS contract and/or Ghostnode rewards. The more rewards you earn, the higher your vote weight will be. In order to be eligible to vote, you must have received a reward within 30 days prior to the creation of a Governance Proposal. Your weight is then calculated by the total amount of rewards received by each qualified address for a total of 46 days prior \(30 days during eligibility period, plus 15 days for voting, and an additional 1 as a cushion\). 

![Click on the Governance Button](../../.gitbook/assets/qt-governance.png)

![Click on the &quot;Refrest List&quot; button to populate/refresh the proposal list](../../.gitbook/assets/qt-gov-refresh.png)

After navigating to the Governance section and populating/refreshing the proposal list, you may then select a specific proposal and review it by clicking on the "Expand Details" button. Once you've decided whether or not to support the proposal, make sure that proposal is selected then click either the "Vote Against" or "Vote For" button. You will then be prompted to enter your wallet password, after which your vote weight will be added to your selection.

## Creating A Proposal

Visit the [Governance Proposals page](../../github-and-feedback/governance-proposals.md).

## More Information

A list of active, accepted and rejected proposals can be [found here](https://governance.nixplatform.io/#/proposals).  
Also, you can find a detailed [Governance pdf here](https://nixplatform.io/wp-content/uploads/2019/02/NixGovernance.pdf).

