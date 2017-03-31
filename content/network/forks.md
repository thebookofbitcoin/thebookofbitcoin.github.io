# Forks

## Hard Fork

Any change to the Bitcoin protocol that means the existing nodes would reject blocks and transactions as invalid is called a *hard forking* change.

Since the Bitcoin protocol is strict about setting limits in a wide variety of areas, most notably the coin limit and block size limit, there are a wide number of changes that may appear to be simple, but from from a protocol perspective are equivalent to completely changing the entire system.

Not all clients of the Bitcoin protocol work the same way. It's possible to change the limits, and so for some types of clients, a hard fork would not be a hard fork at all. Because this is confusing, generally only the broad consensus of the Bitcoin rules is considered when referring to a hard fork.

### Proposed Hard Forks

It's generally understood that should there be an obvious issue or critical problem with the Blockchain, any issue including a deliberate attack on the network, this problem can be solved with a rapid, dynamically chosen or custom developed hard fork.

Satoshi Nakamoto once proposed that in the future a possible hard fork to increase the block size limit be implemented by using a far future *flag day*, a day after which the old ruleset is no longer used and a new ruleset is switched to.

One Bitcoin protocol change that has been long discussed is the reversal of how Bitcoin transactions are confirmed. In the existing protocol, miners sweep unconfirmed transactions into their blocks. In a theorized change, miners would win a temporary period of time in which they could simply directly add transactions to the Blockchain. 

Every Bitcoin can be subdivided into one hundred million Satoshis, however this may not always be enough. A hard fork could increase the divisibility without increasing the coin limit, should the value of a Satoshi grow by enough to justify the change.

## Accidental Hard Forks

Sometimes a hard fork happens in an unplanned way, where miners simply make invalid blocks for accidental reasons.

In July of 2015, this happened on two separate occasions. The first fork produced a series of six invalid blocks, starting with an invalid block from the small mining pool *BTC Nuggets*, and then followed by a series of five blocks produced by the Chinese mining pools *AntPool* and *F2Pool*. The next day, a similar fork occurred, initiated by a block created by the miner *MegaBigPower*. The block was followed by two invalid blocks created by unknown miners.

The reason for this fork is that from the point of view of the network, some miners attempted to reverse the rules set up in the [BIP 66](https://github.com/bitcoin/bips/blob/master/bip-0066.mediawiki) soft fork upgrade. This split the network into two: Bitcoin nodes that used the consensus rule set defined in Bitcoin version 0.9.4 and Bitcoin nodes that used the consensus rule set defined in Bitcoin version 0.9.5.

## Soft Fork

Any change to the Bitcoin protocol's consensus rules that is more restrictive than the existing set of rules is called a *soft fork*. Generally soft forks are considered backwards-compatible because nodes on both sides of the consensus fork may remain interoperable. The standard rollout of a soft fork involves a majority of mining hashing power updating node software to only mine transactions that comply with soft fork rules, and deliberately avoid building on blocks who do not do the same.

Reversing a soft fork would be changing the limits to something that existing nodes would reject, and is thus a hard fork. The hard fork would be from the point of view of the updated nodes only, older nodes would not notice the reversal. This means that even a majority of miners enforcing a soft fork at one point in time do not provide an assurance that the soft fork will remain or be constantly enforced. The assurance derives from the rest of the network's acceptance of the soft fork code, which provides the hard fork cost to the miner of rolling back the soft fork.

Soft fork rollbacks may be accidental, shepherding the miners and the network to a new set of consensus rules can be a perilous process and has led to multiple historical accidents. To safeguard against this, steps have been taken to encourage miners to accurately signal their soft fork consensus rules in BIP 9, and the common process for miners coming to agreement on a soft fork is to signal for three to four weeks that the soft fork has at least ninety-five percent consensus and will be enforced permanently. A soft fork increases the risk to an out of date node that they will no longer be following consensus, so they are encouraged to either update their node to the soft fork or reduce their payment receipt risk by waiting for more confirmations.

### Adding Features

The primary method of adding major features to the Bitcoin protocol is to use a soft fork to enforce new rules about a transaction. For example: adding a new transaction type that appeared to spend funds that anyone might be able to spend but also included a script that others would validate as only being spendable under arbitrary conditions. This transaction would pass muster both to nodes that could not validate the new unknown conditions and to nodes that could validate the script's additional requirements. In this way, miners introduce new spending types by enforcing new rules on apparently less-restricted transactions.

In the case of the P2SH soft fork which enabled new transaction types such as multi signature transactions, the signature requirement to spend funds locked in a P2SH address simply changed to be more restrictive. Before P2SH, anyone could spend funds sent to an output script that matched the pattern *OP_HASH160 $value OP_EQUAL* as long as they provided an input that matched the hash value. After P2SH only the value that matched a working script could be used to spend funds.

Many transaction operation codes or *opcodes* have been with Bitcoin since the early days of the protocol. This set of codes also includes codes that do nothing and always validate, so that in the future they may be used to include new features as they are conceived and agreed upon, without the need to hard fork.

### Fixing Issues

Sometimes a soft fork is necessary to correct a bug. This deployment strategy leaves the bug present in older versions, but takes advantage of the majority miners to censor transactions that exhibit a bug from the Blockchain.

In [August of 2010](https://bitcointalk.org/index.php?topic=822.0), a block was mined with a spurious transaction that created a chain with a transaction sending over a hundred billion bitcoins, an amount that had no source but was rather the result of a coding error called a *value overflow*, where values were not properly checked for numbers that could not be accurately stored.

The severity of the issue was somewhat muted, at that time the project was yet to find popularity and the value of the entire market hovered around hundreds of thousands of dollars. Nevertheless, the obviousness of the problem dictated that a solution be found, and Satoshi Nakamoto [published a comprehensive fix](https://bitcointalk.org/index.php?topic=823.msg9548#msg9548) within four hours of the problem's discovery. The fix had quick uptake that reorganized the chain around the offending transaction within an hour, striking it from the Blockchain history, and preventing any future similar inclusion by miners.

