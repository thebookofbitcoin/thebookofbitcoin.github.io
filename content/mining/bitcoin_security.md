# Bitcoin Network Security

The proof of work algorithm serves as the general foundation of Bitcoin's security. Using this algorithm, participants in the network can make informed decisions about the state of the Blockchain and thus incoming fund transfers because it can be easily determined that there was a cost paid to make an update to the Blockchain.

At a high level view of the system, more cost by a miner to create a history is used to build trust in that history. To encourage the miners to pay the cost, they are rewarded for their cooperation in the form of a block subsidy and transaction fees.

This cost and benefit system is somewhat analogous to how real world cooperation happens. When an unknown third party is seen to have to pay a high price for abuse, it is also seen as less likely that they will pay this price, so abuse is less expected.

Since the security system depends on miners paying a cost, it is very important to Bitcoin's utility that there be a sustainable commensurate reward to the desired cost, at least up until a certain limit beyond which increased security gives marginal returns.

## Block Subsidy

Bitcoin includes a bootstrapping element that solves two important problems at once, how to distribute the currency and how to provide for a high baseline level of security: the block reward. This is simply an amount of Bitcoin that is granted as a prize for winning a block. At the start of the Blockchain this reward was fifty coins, which worked out to an average yearly monetary base inflation of around twenty five percent, quite high when compared to a world currency. 

Bitcoin was not designed to permanently inflate however. The model for Bitcoin was gold, a limited substance to be used as a token for exchange over a long period of time. To follow this model, Bitcoin was designed to have a block subsidy that exponentially decreased over time: every four years the reward is cut in half. After the second half point, inflation cut to around twelve percent, along a pattern that should result in an inflation rate that falls well beneath one percent by around the year 2035.

This represents a major challenge to the currency. The Block subsidy has been seen as the major pillar of Bitcoin's utility, but it is a temporary pillar that must be replaced, otherwise the provable cost to mine may go down or become unpredictable, potentially reducing the utility of Bitcoin to such a great degree that normal commerce using Bitcoin becomes difficult or even almost impossible.

## Transaction Fees

In the long term, it is suggested and planned that transaction fees will take the place of the block subsidy to reward miners for paying the cost to mine. Transaction fees are a drastically different model for security, so there is much concern that they will not represent a sustainable method.

The users of Bitcoin can be thought of as living in two groups: spenders and savers. In the block subsidy phase of the network, it is the savers who ultimately pay the cost of the network security: their coin value is diluted over time as new coins become accessible through the subsidy. Transaction fees on the other hand shift the cost to be borne by spenders. In each case, one group gets a free ride, which is seen as less than ideal: ideally necessary costs are matched to benefiting parties as closely as possible.

The other main concern with transaction fees is that they may not be enough to provide a baseline level of security. In a far future state of technology where the marginal cost of a transaction is almost nothing, it could be seen that a miner would accept a transaction into his block for almost nothing. In that scenario, even large numbers of transactions might not net enough total reward to subsidize a healthy level of proof of work.

The standard answer to that quandary is that the marginal cost of a transaction must never be allowed to get too low. How that is achieved is a matter of much debate. There are broadly two answers: one is to ignore the problem until a later date, betting that the marginal cost in the near future is not near enough to zero to cause any issue. The other is that miners or the greater network could create an opportunity cost for transaction inclusion by setting a limit on the number of bytes that may enter a block. A limit was already set in place by Satoshi Nakamoto at one million bytes, although it is broadly seen, even by Satoshi's own quoted statements, as a limit that might be advisable to increase in the future.

It's generally seen that a transaction limit is the best known long term sustainable solution to providing for a proof of work reward. Not only is this solution not threatened by technological improvement that would render a marginal cost solution obsolete, it also solves another important network problem which is that the network's node operators bear a cost that is relational to the number of transactions allowed per second. Even further, it solves a greater design problem of creating a piece of software that can function for decades without changing quickly or even at all, and in the face of potentially hugely increased demands.

To guard against a potential situation in which fees are too high because the transaction limit is too low, off-chain transaction mechanisms may be developed, putting pressure on the miners and the network to lift the transaction volume to remain competitive.

## Alternative Security Funding

At the start of Bitcoin, there was no source of funding for the proof of work. Many things in the Bitcoin system are not even compensated at all at a basic level, such as relaying transactions. These things have worked even without compensation due to a latent level of altruism that members of the network exhibit. It's possible in the future that some mining would simply take place by default: excess energy draining off from overloaded grids, heaters and lightbulbs that ran their energy through a mining algorithm, and similar latent energy draws. With widespread, distributed use, no reward might be necessary to provide for all the security normal commerce would ever need.

Another mechanism proposed to pay for mining in a post-subsidy world is for interested parties to band together and pay the necessary amounts. The thinking behind this is that in the world, trade organizations exist to promote their common good. In the same way, large merchants might realize that the security of their payments required an upkeep. While this plan is possible, it also has a major sustainability critique: members of the merchant associations might not pay their dues. The problem is a classic free rider situation, so whether a cohesive group to pay for proof of work could be sustained is questionable.

