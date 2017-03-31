# Smart Contracts

Bitcoins on the Blockchain are moved through *transactions*, which are simply files that contain cryptographically signed statements about the movements of coins. The entire Blockchain history is basically just a giant set of these signed statements, Blockchain balances are always determined by following the chains of ownership declared by the transactions.

The signed statements in transactions can actually be thought of as a signed contract: a buyer signs an agreement to send an amount of Bitcoin to a seller. The language of a transaction is a flexible language, like a computer scripting language. It can express a wide variety of statements beyond the simple statement of "send funds to address". Because there is this variety of expression, Bitcoin transactions are sometimes also referred to as **smart contracts**.

## History of Smart Contracts

In the original envisioning of Bitcoin, many types of transactions were envisioned: [Satoshi Nakamoto carefully thought out](https://bitcointalk.org/index.php?topic=195.msg1611#msg1611) a set of language primitives that would allow the expression of a wide variety of smart contracts. Due to the complexity of crafting easy-to-use tools to form these contracts, the Bitcoin client left their construction as an exercise to the future developer.

Satoshi's decision to design a system that allowed complex contract formations was quite controversial. [Gavin Andresen](https://bitcointalk.org/index.php?topic=2162.msg28549#msg28549) and Jeff Garzik lobbied strenuously for a simplified system, with Jeff Garzik going so far as [to demand](https://bitcointalk.org/index.php?topic=2129.msg27884#msg27884) [repeatedly](https://bitcointalk.org/index.php?topic=2129.msg27961#msg27961) that all smart contracts be removed from the system. Luke-Jr, Greg Maxwell, [Theymos](https://bitcointalk.org/index.php?topic=2162.msg28317#msg28317) and others argued against this restriction, looking towards the future promise of smart contracts to power advanced Bitcoin applications.

When Satoshi [published Bitcoin version 0.3.18](https://bitcointalk.org/index.php?topic=2162.0), he created a rough compromise, based on Gavin's suggestion: create a standardized rubric for what transactions look like and refuse to allow unknown constructions to be shown to users or relayed on the network, in an opt-in whitelisting system known as *standard transactions*. 

Over time as Jeff Garzik and Gavin Andresen's influence waned and their fears were proven unfounded, the limitations of the whitelist were reduced, however the basic concept of whitelisting was never removed, and it serves as a simply safety net to avoid confusion about the nature of transactions.

## Smart Contracts By Example

Beyond the most common smart contract: sending coins to make a payment or to transfer funds, there exists a constellation of smart contract possibilities, with many complex transaction types even found in common use.

The most commonly used or promising potential uses for smart contracts are: multi-signature wallets, signature based escrow, coin mixing, group payments, payment channels, and time locked payments.

Generally speaking there are a simple set of primitives and logical rules that may be applied to form these contracts. Funds are controlled by private key values, which have a public key representation that is used as a public identifier. Fund values are represented by unspent funds from previous inward transactions, called *unspent outputs*. When forming a transaction, the unspent outputs are used to form the inputs of the new transaction. Alongside the fund transfer information is a statement regarding the preconditions of the transfer: limits on timing, signature strictness and composition are allowed to place intelligent limits on the fund transfer. The finalization of transactions involves two steps: cryptographically signing transactions with private keys to authorize the movement of funds, and publishing transactions to the miners to confirm transactions into blocks in the Blockchain.

### CoinJoin Transactions

The concept of a CoinJoin transaction is to obscure the ownership of funds through a transaction in which many parties pool their funds in a single transaction, and then withdraw their funds from the pool in a proportional way, obscuring the Blockchain's chain of custody of funds: the Blockchain only cares about the balance of of funds going into and out of a transaction, within a transaction no linking information regarding the linking of funds in to funds out is necessary.

The way this leverages the scripting primitives is by taking advantage of the separation in the transaction formation step and the transaction signing step. The pooling transaction is passed around for all parties in the pool to inspect for its validity. After each party has signed, it is published to the network. Trust is not a variable in the equation because the signature each person applies can only be used in the transaction that they saw, alterations that would steal funds are prevented through the signature's cryptography.

These type of transactions are rare, but they can be found in the wild, most notably on the [JoinMarket](https://github.com/JoinMarket-Org/joinmarket).

### Arbiter Escrowed Transactions

In an arbiter based transaction, a trade is made in which two parties do not trust each other, but they trust the decision of a neutral arbiter to decide in the case of a dispute. This arbiter can be a person who evaluates the details of a trade, or even just a service or function that returns a signed statement that can be fed into a transaction. This kind of a transaction acts like traditional escrow, but with the advantage that the arbiter has no way to unilaterally take the funds for himself.

This type of transaction takes advantage of a transaction primitive called *multi-signature verification*. This statement can be setup to declare that some number of signatures are required to spend the unspent funds. In the prototypical arbitrated escrow situation, funds are given over to three people, with two signatures required to spend the transaction. This gives both the buyer and the seller an opportunity to refrain from signing until they are satisfied with their transaction, and in the case of a dispute gives the arbitrator the deciding vote to either refund or complete a transaction.

Escrowed exchanges are extremely common in Bitcoin, especially in instances like intra-platform trades on custodial wallets like ChangeTip, Coinbase, LocalBitcoins, Bitstamp. However these trades do not use arbiter escrow systems, due to the complexity cost of implementation.

Still, arbiter multi-signature transactions have some real world use. One example is enabling rapid fund transfers with [BitGo's Instant service](https://www.bitgo.com/instant). Another service that is more classically in line with the arbitration model is [Bitrated](https://bitrated.com), which is something of a directory and marketplace for arbitrators.

Signed statement services and even standalone signing functions have been theorized as possible additional useful tools to use as arbiters, however in practice these have not found much uptake due to complexity, narrow scope, and lack of obvious necessity for their use.

### Cooperative Multi-signature Contracts

One very simple scenario in which a multisig contract can assist in a trade is one in which a buyer does not trust a merchant to deliver and the merchant does not trust the buyer to pay. In this case a contract may be formed that states that both the merchant and the buyer must cooperate to finalize a payment over to the merchant. Once the buyer is satisfied, he signs the payment over to the merchant. 

If something goes wrong, the buyer's funds are locked: not signed over to the merchant but not returned either. This gives the two parties motivation to come to an agreement to unlock the funds.

Although this type of multi-signature contract is quite simple, in practice it's rarely used. The properties of the failure scenarios when compared with adding an arbiter mean that arbiters are seen as a much more attractive option.

### Security Multi-signature Contracts

The initial driving force behind multiple signature contracts was to improve the security of funds. A separation of signing authority is a security industry standard practice: simultaneously compromising multiple isolated systems is much more difficult. This security can power a scheme in which multiple independent personal devices are needed to sign off on a transaction, such as in the [digitalbitbox](http://digitalbitbox.com/) hardware wallet's cooperation with a mobile phone app. Or it can create a voting mechanism between trustees, funds can be stored in a corporate wallet, with ten signatories but a mandatory signature limit of six signatures to send funds. 

In practice, cooperative multi-sig is used quite frequently as a security precaution. Multiple signatures can make wallets such as [Electrum](https://electrum.org/) and [CoPay](https://copay.io/), or even Bitcoin exchange wallets like [Bitfinex](https://www.bitfinex.com/security_policy), much more secure by preventing single points of security failure. 

### Grouped Payment Contracts

One method of crafting a transaction can be to setup an aspirational send, a send in which there are not enough signed funds, but there is a known destination for funds. For example: several people together wish to egg each other on to participate in a bet. They can construct a transaction that has a known and unalterable output and transfer amount, but an undefined set of funding parties. These people can then allocate signed funds to the bet transaction, with confidence that the target of the funds cannot be altered and if the aspirational amount is not reached, the transaction will never complete. 

In practice, situations in which this type of contract is apropos are few and far between. Due to the complexity of forming these transactions, few tools exist to make this workflow accessible for the average user and these transactions are very rarely seen in the real world.

### Payment Channels

One promising Blockchain innovation powered by smart contracts is the concept of a *payment channel*. At a simple level, a payment channel allows instantly secure transactions at minimal cost by creating a secure channel to route transactions through. A transaction settled over a payment channel can be settled a million times faster and be a million times cheaper than a transaction settled on the Blockchain. Payment channels are only appropriate for repeated transactions between long running partners, however in theory a network of partners may be formed to allow sends between non-directly linked pairs.

Payment channels involve a series of smart contracts: a fund locking contract to lock in an amount of funds to trade, a time-locked refunding contract to avoid a cooperation deadlock between the payer and the payee, and then a series of balance update transactions that represent the rapid and secure trading of funds.

In detail payment channels are established through a careful protocol. First, the channel creator forms and signs a *fund locking transaction* that sends Bitcoin to an address controlled by both parties, but he does not share this transaction with the other party. Next, the creator creates a *refund transaction* that re-spends the Bitcoin from the fund locking transaction. The creator gets the other party to sign it, but the creator does not sign it himself so that only he can execute the refund. It's important to note that the refund transaction has a time restriction: it cannot be spent immediately, only after a period of time specified in the contract.

Finally, to create the channel, he shares the initial fund locking transaction with the other party, who can then sign and broadcast it to lock in the funds to the shared address. Because the creator has the refund transaction, he is safe from the other party not cooperating to return his funds, and because the refund transaction has a timeout, the other party has an assurance that the refund cannot be executed unexpectedly.

Now that the channel is established, the channel creator can start creating a new type of transaction, a *payment channel* transaction, which is like the refund transaction in that it re-spends the funds to refund the money, but updated with some funds now going to the other party instead of fully refunding himself. Each of these refund/payment channel transactions conflicts with the others, so double spending is impossible: when the other party wants to get paid, or the creator wants to end the channel arrangement, they simply take the last transaction and broadcast it to the Blockchain to settle the temporary balance of funds.

Channels need to be periodically closed and re-opened based on the expiration date of the time-lock. The time-lock ensures to the other party that the creator cannot back out of the contract unexpectedly or with an obsolete refund transaction. At the same time, the time lock guarantees that if the other party stops cooperating, the funds may be returned without their intervention after a period of time.

Although this protocol is promising for the rapid and economical advantages it brings, it is not yet in widespread use. The complexity involved in the protocol, complications from bugs and deficiencies with the Blockchain smart contract system, and the limitation presented locking funds to a single other party create large barriers to its use. That is not to say efforts have not been made. Developers have created libraries to abstract away the complexity of the protocol, such as in [bitcoinj](https://bitcoinj.github.io/working-with-micropayments). Bitcoin Core has been progressively addressing the bugs and deficiencies that cause problems for effective channel use. And many efforts have been made to expand the protocol from single party payments to a network of connected parties.

Some examples of payment channels in the wild are the [21 Marketplace](https://21.co/mkt/) which provides a series of APIs that are paid over payment channels. Another commonly cited example is the [Streamium](https://streamium.io/) streaming video service, which offers pay per second viewing of premium video content.

