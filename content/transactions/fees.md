# Transaction Fees

Every Bitcoin transaction submitted to the network to be included in a block may include a fee amount to be claimed by the miner who is the first in the enduring Blockchain history to mine a block with the transaction included. In addition to incentivizing miners to include transactions, fees allow prioritization across the network and disincentive network abuses.

Fees work through a clever system where transactions may include more input funds than they output. Miners may then take the excess inputs and add those funds to their reward transaction, making for an efficient and simple system for representing the wealth transfers

## Benefits of Fees

Although the Bitcoin design attempts to encourage the inclusion of transactions in blocks by minimizing the cost to include transactions in blocks, miners sometimes skip all transactions in a block. Fees act as a financial motivator for miners to include transactions. Fees also act as a small incentive for network nodes to relay to the miners, in that they represent a participatory effort towards the network security, which relies on the shared expense of the proof of work.

The Bitcoin Peer to Peer Network is a shared resource that anyone may access and utilize as much as they see fit. However it is also a limited resource, there is a finite capacity of transactions that the network may relay. When the capacity of the relaying network starts to be challenged, nodes use fees to determine priority of service to requests. This either routes the most important, high value transactions through first, or creates a bidding war and thus a high expense between the attacker and all the rest of the network who wish for their traffic to be relayed. Miners use fee bidding as well: to avoid a deliberate denial of service on blocks by filling them with irrelevant transaction, an attacker must outbid the totality of the network, an expensive proposition.

Fees have [long been seen](http://nakamotoinstitute.org/bitcoin/#selection-185.5-188.0) as the answer to the [sustainability of the network](http://satoshi.nakamotoinstitute.org/emails/cryptography/9/) going into a future where the limited supply of Bitcoin erases the block subsidy from the miner's blocks. [Rewarding miners](https://bitcointalk.org/index.php?topic=48.msg329#msg329) to an adequate level for secure trade is vital to the utility of the network, and transactors benefit directly from that security, so in a sense the transactors are paying to sustain the resource they use.

## History of Fees

In the first versions of Bitcoin, the protection against network abuse were hard limits. In Satoshi Nakamoto's Bitcoin GUI, it wasn't possible to send any Bitcoin amount lower than 0.01. He never altered that limit. Satoshi added hard limits to free transactions and rolled out logic for fees to be based on transaction size in November of 2010. Transaction fees were pitched as an auction: a sustainable system to always allow the highest priority transactions a clear and accessible path to inclusion.

As the years passed by and Bitcoin's network usage experienced the demands of a dynamic audience, fees continued to evolve. Free transactions, the norm at the start, began to pose a challenge to the network due to abuse. In response, a priority system was devised to use the time since the funds had moved, or *coin age*, as a signal to determine abusive rapid fund movers and de-prioritize them. To prevent resource hungry tiny micro-transactions Bitcoin Core moved to a policy where transactions were forced to send amounts higher than a hard coded minimum amount.

The restrictions posed by fees complicated network function. Although fees became more and more pressing to prioritize transactions, the rapid price shift in Bitcoin meant that developers could not keep up with constantly manually setting default fees. Bitcoin Core version 0.10.0, released in February of 2014, solved this issue by dynamically adjusting the fee limits against soft totals, making all fees into pure auction elements. A dynamic fee estimator replaced a static recommendation tool, to present a sustainable fee solution for the indefinite future.

In later versions, the dynamic fee estimation grew more accurate, but also more pressing. As transaction volume grew, so did the importance of proper fee selection to avoid stuck transactions. Miners took note of transaction fees as well, mostly abandoning the coin-age priority system in favor of a straightforward fee maximizing algorithm. In 2016's version 0.12.0 free transactions using the priority system were disabled by default, signaling a start to a future of mandatory fees and a simplification of the transaction inclusion model.

## Network Fee Behavior

Even though Bitcoin Core's fee strategy switched to dynamic fees in version 0.10.0 there remains various overrides and safety defaults. A fallback static default fee is set for situations where block estimates are not available. A maximum transaction fee is set to prevent accidents. A minimum transaction fee is set to put a low baseline fee amount, which also prevents dust transactions from creating outsize network costs.

All of the default fees and overrides may be configured using the Bitcoin Core *bitcoin.conf* file or execution options and are not consensus critical, they may be determined independently by every full node. Full nodes also use these values for routing logic and to resist denial of service issues. For example, full nodes will relay small fee transactions, but only up to a configurable limit of fifteen kilobytes per second to put a barrier on abuse of the transaction relaying system.

## Fee Prediction Services

- 21 Bitcoin Fees, also known as *Cointape*: https://bitcoinfees.21.co/
- Bitcoin Fees Project: https://bitcoinfees.github.io/
- Bitcoin Queue Project: http://www.bitcoinqueue.com/live.html
- P2SH Fee Estimation Roundup: http://p2sh.info/dashboard/db/fee-estimation
- Statoshi Fee Estimation: https://statoshi.info/dashboard/db/fee-estimates

