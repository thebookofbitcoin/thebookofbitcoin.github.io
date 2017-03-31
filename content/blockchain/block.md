# Block

A Bitcoin **block** is an individual encapsulation of transactions on the Bitcoin Blockchain. Blocks serve as a timekeeping mechanism for the Bitcoin network, and collectively provide for what is essentially a canonical transaction history of the network. Each block, save for the first or *genesis* block, points backwards to a previous block, forming a chain of blocks called the Blockchain. Since the process of publishing blocks is open, there can be multiple valid chains of blocks. To determine a working version of history Bitcoin full nodes are programmed to use the longest chain of valid blocks, with ties going to the first seen.

Blocks are intended to serve as a permanent transaction record, with a proof of work cost serving as a prevention mechanism for future block displacement. As blocks link to each other in a chain, the cost to alter the chain of blocks grows in proportion to the length of the blocks: the signature method in each block and in each link means that changing a single block also requires changing all the blocks linking to it. The network nodes that append to the block record are called *miners* and they are selected via an open process of random, proof of work weighted, selection called *winning a block* that is designed to be repeated every ten minutes on average.

## Proof of Work

The design of the Bitcoin network presents an open process for anyone to participate in confirming transactions in blocks, but works to limit the number of blocks per hour to a maximum of six. To *win* a block and place it in the chain of blocks, a miner must solve a challenge also known as the *Proof of Work* or *hashing*. In the proof of work, guesses are made towards a random number, in a probabilistic way where a guesser makes no progress towards a solution.

The particular mathematics behind the number selection give the ability for anyone to very quickly verify the correctness of the number. Every two weeks measured by two thousand and sixteen blocks, the network adjusts the *difficulty* of the guessing game, based on statistical analysis of recent guess results. This adjustment serves as a rate limiting function on the entrance of blocks into the chain.

Block times are quite variable, with some blocks requiring hours to be found. This is by design, to avoid a race condition where multiple blocks are found at similar times. The race avoidance also assists in the decentralization of mining, the importance of being first in a race to send blocks to the other miners is lessened when the chance of simultaneous blocks is minimized.

## Block Incentives

The network design grants the winners of the Proof of Work challenge a reward, incentivizing the mining process. The rewards consist of a lump sum of coins or *block reward*, and a variable amount of fees paid by network users.

The block reward serves as a strong encouragement to mine in the bootstrapping phase of the network, and to distribute the coins over a long period of time, with the hope of promoting a more diverse ownership set. After the network's bootstrapping phase, the block reward disappears, using an exponentially decreasing step function. At the start of the Blockchain, every block includes a fifty bitcoin reward, this reward halves every four years, or more specifically: every two hundred and ten thousand blocks.

The transaction fees serve as a signaling and braking mechanism to prevent a network denial of service: in the event of an excess of transaction activity, nodes may choose to cull the low fee transactions as a defensive mechanism, raising the overall expense of an attack and allowing for high value transactions to enter the Blockchain without issue. 

## Transactions

Blocks encapsulate transactions, data chunks representing movements of bitcoin through the system. Users of Bitcoin broadcast their transactions to a peer to peer network formed by people running full node Bitcoin Core software or compatible full node clients. Each node relays the transactions as it receives them, assuming they pass a set of validation rules and fit within priority limits governed by each transaction's fee per byte. Given that blocks appear only once every ten minutes or so, transactions arrive in the network's holding areas or *mempool* in an unconfirmed state: received by the network, but not *confirmed* into a block.

Miners include transaction data into their blocks, up to a system defined limit of one megabyte. From the pool of unconfirmed transactions, miners generally select a mix of transactions that results in the highest possible amount of fees. Miners also often avoid including transactions that have little to no fees, making the judgement call that these transactions represent little importance to the network and in the final analysis bear a cost to the network that is greater than their benefit.

## Empty Blocks

It's quite unusual for the network to ever fully clear out all of the network transactions that are waiting for a place in a block. However it is not unusual for a miner to produce what is called an *empty block*, a block with only a single reward transaction, also known as the coinbase transaction.

The reasoning behind this behavior is that miners do not run the standard Bitcoin Core mining software, they run a customized version that is designed to cut corners, to maximize profit. In a rare situation in which a block is found very quickly after the previous block there is no time to validate previous transactions, existing transactions and assemble transactions in a new block, so the validation is skipped and the new block is sent to the network with no transactions. This maximizes profit for the miner, minimizes risk of propagating invalid transactions, and happens rarely enough that it does not serious impact the network in a negative way.

## Discarded Blocks

It's possible through accident or deliberate purpose that crafted valid blocks will not make it into the permanent Blockchain record. Generally this situation is known as *orphaning*, and the situation only occurs for a single block. A lot of design and work goes into preventing this situation, because it is confusing and wasteful for the Blockchain to have blocks that are discarded.

In the situation where there are two valid blocks published around the same time and one becomes non authoritative as being part of a shorter chain, this is called a *stale block*. Clients will simply ignore these stale blocks, and miners attempt to avoid this situation by quickly propagating their blocks to avoid losing their block prizes.

If miners continue to build on a stale block, they add *orphan blocks*, so called because they have no known parent in the longest valid chain.

