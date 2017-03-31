# Replace By Fee

Every transaction published to the Bitcoin network enters a state known as *unconfirmed* or *0 confirmations*, meaning that the transaction broadcast succeeded and now the transaction awaits confirmation by a miner. During this waiting period, the publisher of the transaction might wish to alter the transaction, but under normal circumstances the network ignores transaction alterations within a lengthy timeout period of two or three days. Using **replace by fee** a transaction may bypass this transaction alteration prevention mechanism by publishing a transaction replacement with a fee higher than the previous submission.

## Origin of the Sequence

Since the start of Bitcoin, until the present, a feature known as a *sequence number* has been present in every transaction. The purpose of the sequence number was to allow in-flight updates to transactions, by replacing them with a later sequence number. In the original Bitcoin software published by Satoshi Nakamoto, this was possible, but Satoshi [disabled sequence numbers](https://github.com/bitcoin/bitcoin/commit/05454818dc7ed92f577a1a1ef6798049f17a52e7#diff-118fcbaaba162ba17933c7893247df3aR522) in version 0.3.12. Satoshi wrote "Disable replacement feature for now", indicating the feature posed a problem to the network that required a temporary disabling.

Transaction replacement was in fact a potential denial of service vulnerability in the Bitcoin peer to peer network; an attacker could flood the network with replacements without cost, creating an outsize burden on the relaying infrastructure. The standard flood prevention design used by relaying nodes is to make sure that every network action has a well-defined cost, and that service may be quickly cut off to low priority traffic when the network is under high load.

## Fees with Sequences

Over time, the network came to rely on the temporary disabling Satoshi enacted in version 0.3.12. Transaction replacement grew to be viewed as undesirable, with claims that the design of the overall network to promote immutability clashed with the design of mutable transactions. But others countered that the only immutability guarantee not simply a matter of happenstance was the immutability of spent energy in the proof of work, that the pattern and topology of the peer to peer network could change at any time and should not figure into a protocol design equation and not be depended on by anyone.

An idea was borne to solve the replacement denial of service issue: treat each replacement sequence increase as a new transaction, with a commensurate new fee. This concept, *replace by fee*, or *RBF* solved the denial of service issue, and as Bitcoin design thinking leapt forward to a time in which transactions might be increasingly stuck due to extremely low priority fees, or when sudden spikes in demand for the Blockchain might leave some transactors in the lurch with their priority transactions. Proposals were formalized for RBF: sequence increases might be performed up to one hundred times, and must always pay a fee increase larger than the minimum relay fee amount.

Finding network traction for this idea proved difficult, despite the solution to the denial of service problem. The possibility for abusive use to mislead merchants into expecting a payment that would later be removed loomed large. For a time the proposal languished, unable to make headway against the fear of abuse.

## Backwards Compatible Sequence Replacement

The Bitcoin Core developer Peter Todd had been championing the cause of RBF since early in 2013. He and other prominent Bitcoin developers long argued that transaction replacement was always possible through deliberate action and merchants were either incorrect in relying upon unspecified and unpredictable transaction behavior, or not in fact relying upon it in the first place. Over the years Peter published software to bring back transaction replacement, in two variants: *First-Seen-Safe RBF* or *FSS-RBF*, and *Full RBF*.

FSS-RBF was an attempt to ameliorate concerns that RBF would be used to defraud, by requiring the replacing transactions to still pay the same destination addresses. This proposal did serve to appease the worriers, however as a long term solution it was widely criticized as privacy abusing and therefore fungibility threatening. Bitcoin destinations are designed to be opaque, to avoid the chain of payments being meaningful and to protect the financial privacy of users. Adding new transaction destinations would help defeat privacy protections by pointing to the destinations as linked to the author of the transactions.

A final compromise was found after seemingly endless debate: a new, non-standard transaction type that explicitly signaled its status as replaceable. This compromise was called *Opt-in RBF*, and it simply reenabled the original replaceability Satoshi temporarily disabled, with the protections against DoS, but in a simple form that wallets must be deliberately coded to show in unconfirmed state. Wallets could then easily show these transactions in a level below unconfirmed: unconfirmed and easily replaceable.

In February of 2016, Bitcoin Core version 0.12.0 included support for this signaled replaceability, although only for relaying and mining purposes, no user interface support was included.

