# Proof of Stake

The Bitcoin Blockchain's security model rests on a pillar known as *proof of work*, a protocol in which updates require provable expenditure of resources. In proving the expenditure of resources, two limitations are imposed: time is required to prove a significant expenditure, and the expenditure has no other purpose than to be spent. Addressing those limitations has been the subject of much thought and effort, and the **proof of stake** system has been proposed as an alternative, although no workable system of proof of stake has been devised and there are strong doubts as to its feasibility at all.

In an advanced proof of work system like Bitcoin, minor elements similar to proof-of-stake are used to add additional security on top of the pure proof of work. Bitcoin miners must invest millions of dollars in their equipment, must study Bitcoin and commit and develop fixed resources to their mining operations beyond electricity, must wait sixteen hours to trade their mining rewards, in an ongoing process that ties a miner to the fate of Bitcoin. Bitcoin in the past has also experimented with proof-of-stake signaling using *coin age*, the time since funds last moved. At one point it was thought that this signal might be used to determine transaction priority.

## Motivation for Proof of Stake over Proof of Work

Proof of work requires that work be done to satisfy that a double spend be costly. However proof of stake argues that this cost might be a waste. Given a small set of stakeholders who are financially invested in the health of their investment, maybe simply trusting in their prudent judgement would be warranted? If true, this would save a great deal of energy expenditure. Energy creation and use generally carries a negative connotation due to its common correlation with abuses of the environment. Although Bitcoin's design merely favors the least expensive source of energy possible, many power creation methods create unwanted externalities of cost, making energy itself a loaded word.

In a proof of work design, miners are not trusted, only their work, as verified by cryptographic math. Given that the work takes time, this introduces a cost to using the system: waiting for sufficient work. Proof of stake argues that trusting individuals based on their stake vastly increases the speed of proof: miners merely signal their view, their identity serving as their proof, without any significant time restriction.

Proof of work designs generally use a rewards based system based on time decreasing rewards, as a bootstrapping method to quickly create enough security for transacting. But this limited variable may also serve to mask a lurking challenge, what happens after the rewards disappear? Merely the presence of this quandary presents a challenge to the confidence in Bitcoin: fees amount to a variable seen to easily change or never be sufficient, with potentially destructive consequences. In a proof-of-stake system, the purpose of a block reward is muted, removing a variable to consider when thinking about the long term future of the system.

An additional proof of work issue in the long term is the anticipation of a phase in which renting proof of work becomes possible. An attacker who might rent enough hash power to double spend their transactions might be able to shield themselves from the future repercussions a standard miner with their own hash power equipment would suffer. If proof of stake could be made to work, attackers might find acquiring a majority stake made them prohibitively exposed to future downturns in the currency value, dis-incentivizing them from exhibiting behavior detrimental to the currency value.

From a valuation perspective, proof of work may be seen to present a constant negative pressure on the valuation. Miners are incentivized to compete to the edge of profitability, meaning that fees and block rewards must trend towards a real world exchange, meaning value must be constantly exiting the system, pushing the currency valuation ever downwards. A proof of stake system might be more static without the need for a real world exchange to keep it in operation.

## Methods of Proof of Stake

Proof of stake is the type of concept where people try to work backwards from an idea that would potentially fix issues, to figuring out how that idea might be made to work. Over time much effort and code has gone into writing proposals and preparing proofs of concept, but no generally accepted method to making proof of stake work has ever been achieved.

Generally all methods of proof of stake confront a basic issue straight away: reproducing the randomness of a proof of work's miner selection process. All proof of stake methods use some arbitrary random element to select stakeholders to be chosen to update their ledgers. One implementation is to give each stakeholder a counter since their last block, progressively increasing a chance to win a block. This method incentivizes coin age. 

An alternative version of proof of stake is to hold miner elections using stake voting. The elected miners are then sorted randomly for mining blocks. This method can be problematic if a bloc of miners uses social engineering to convince the stakeholders they should be awarded mining power.

## Proof of Stake Problems

The principle proof of stake issue is that without a specific cost to create a double spend attack, merchants cannot really rely on a quantifiable incentive against them occurring. Even more troubling, given a disagreement between multiple competing chains, stakeholders have no need to only select a single chain to vote for, making for a potential voting deadlock. This issue is known as the *nothing at stake problem* and no direct solution has ever been suggested, however many mitigating tactics have been proposed and implemented.

Another significant problem with proof of stake is the coin distribution problem. In a proof of work, an open process may take place over decades where coins are distributed to anyone who cares to mine. In a proof of stake, how to distribute the coins equitably? No equitable answer has been presented, but two practical solutions have appeared: depending on an initial mining period for distribution and selling the initial coins in an initial coin offering.

An initial coin offering suggests an inequitable distribution, so these offerings are seen as potentially unfair or centralizing. Wealth itself is often seen to be inherently centralizing over time, so proof of stake may easily follow the general pattern of wealth: a power law distribution of block updating invested in minute upper echelon.

A critical problem with proof of stake is the issue with defeating a fifty one percent attack. In a proof of work system, a nuclear option to prevent miners betraying the user base is the option to simply alter the proof of work to shake up the composition of miners. In a proof of stake system, miners and owners of the currency are equivalent, meaning that the alteration of the stakeholders requires massive and complex disruption to the composition of coin ownership.

Some proof of stake proposals promote the position that developers themselves represent a check in the system. In these proposals developers broadcast to nodes trusted block checkpoints, preventing long chain reorganization attacks. This however creates an extreme point of centralization around the developer, a point of weakness for these systems since developers may easily be complicit in an attack. 

