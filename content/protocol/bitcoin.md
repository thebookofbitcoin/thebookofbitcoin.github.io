# Bitcoin

**Bitcoin** is a currency designed to be universally usable, require no trust and not be reliant on any single party for its operation. To promote the idea of bitcoins being valuable, the design limits the production of coins and utilizes them as a prioritization and rate limiting mechanism when sending transactions. Satoshi Nakamoto [first proposed Bitcoin via a white paper](https://www.mail-archive.com/cryptography%40metzdowd.com/msg09959.html), in November of 2008, and then published a client that began the network on January 3rd, 2009.

## Limited Issuance

Bitcoin miners are allowed to reward themselves with a subsidy when they publish new blocks, this serves to distribute the currency. To promote the idea of bitcoins being scarce, this subsidy is designed to reduce exponentially over time: every four years the subsidy is reduced by half. At the start of Bitcoin, a miner could reward themselves with up to fifty bitcoins per block, after four years this subsidy was reduced to twenty-five bitcoins. The sum of these subsidies over the entire lifetime of Bitcoin is designed to total twenty-one million bitcoins.

## Previous Electronic Currencies

- 1982: David Chaum's [ecash, or "Untraceable Electronic Cash"](http://blog.koehntopp.de/uploads/chaum_fiat_naor_ecash.pdf)
- 1998: Wei Dai's [b-money](http://www.weidai.com/bmoney.txt)
- 1998: Nick Szabo's [bit gold](http://spectrum.ieee.org/computing/software/bitcoin-the-cryptoanarchists-answer-to-cash/0)
- 2004: Hal Finney's bit gold variant [Reusable Proofs of Work](http://cryptome.org/rpow.htm)

## Trust and Decentralization

The fundamental design goals for the Bitcoin currency are to minimize the trust required to use the system and to maximize the durability of the system through decentralization. Through these goals, a lasting, reliable currency to store and transmit value can be achieved.

To achieve a system in which no trust is required, users can run a fully validating wallet called a "full node", which fully validates incoming transactions. The design of a full node is such that it analyzes every single transaction ever made to independently confirm all information that was supplied by a third party.

The key innovation that Bitcoin makes to reduce trust in accepting transactions is the "mining" concept. A key problem faced by any distributed system is determining the ordering of operations across multiple independent systems. In a digital currency this problem manifests itself as a possibility in which a modifier of the transaction history may modify the history in such a way that they first appear to send funds to someone else, but then alter the history so that the funds are sent to themselves, nullifying the initial send.

To solve this, mining requires that the parties who alter the shared transaction history must provably expend energy when they modify the transaction ledger. Through this mechanism, when receiving a transaction the receiver can determine that if the party sending the funds will modify the history to take their funds back, they will also have to expend energy and therefore money to create a new history. This allows receivers to manage their risk, and wait a commensurate amount of time before accepting a transaction from a third party.

To prevent node centralization, the design of the network is such that full nodes have a low operating cost, they are designed to be accessible to a wide range of users. To prevent mining centralization, the proof of work problem that miners have to solve is designed to be very generic and the process for publishing solved proof of work is also designed to be accessible to a wide range of users.

