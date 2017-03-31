# Off-Chain Transactions

The goal of Bitcoin is to serve as a world currency. Although Bitcoin is often associated with the Bitcoin Blockchain and the Bitcoin Peer to Peer network, Bitcoin is also an abstract concept of value that can be used without either of those things, merely to represent debts or credits on any arbitrary ledger. Using Bitcoin for its abstract value characteristics is called using Bitcoin as a *unit of account*. Transactions on ledgers other than the Blockchain ledger are called **off-chain transactions**.

Transactions outside of the Blockchain obviously lose all of the benefits of the Blockchain, but they are also not subject to any of the limitations of the Blockchain. The most commonly lamented limitations of the Blockchain are its limited speed, its inability to reverse fraudulent transfers, its limited capacity and consequent high expense, its limited privacy, its technical complexity, and its limited micropayment support. Since off-chain payments have none of the restrictions of the Blockchain, they have an opportunity to address those limitations.

## Custodial Transactions

The entire world's economy already runs on digital transactions. The world uses a wide variety of systems to accomplish this goal, but almost universally the systems used are abstracted from the core unit of value being transferred. A financial transfer system that moves U.S. dollars like PayPal is not very different from a financial transfer system that moves Chinese Yuan like AliPay. Using a Bitcoin unit in the place of a fiat currency unit in these existing systems would be easily possible, although the negative impacts of departing from the trust-minimizing and durable Blockchain are not to be discounted.

Even since the early days of Bitcoin, transactions using custodial proxy systems have comprised a great majority of the exchanges between Bitcoin users. There is then ample evidence of the perils and promises of such systems. A common example is the Mt. Gox exchange, which offered an innovative rapid fund transfer system for exchanging Bitcoin, at the cost of requiring counter-party trust in the system. As is well known, the counter-party trust in the system would come to be misplaced, but the general innovation held: after Mt. Gox, the vast majority of Bitcoin exchanging and most likely trading of any kind came to take place through proxied off-chain ledgers.

To improve upon the problematic Mt. Gox model in which complete trust was a near absolute requirement, two solutions have been devised. The first is a layered security approach in which redundant trust systems are used. This is represented through multi-signature control of funds, which requires two independent parties to sign-off on fund transfers, to prevent unauthorized movements of funds. Exchanges and companies have sprung up to use this model, as it reduces the risk to all parties, a risk made all too apparent by the dramatic failure of Mt. Gox.

The second security solution is to use a combined signature scheme to prove to users that their funds are still present. The exchange simply cryptographically signs a public statement that user funds exist, by signing a known state of the overall system based on a collective signature of every users' funds. The exchange then allows users to spot check their own funds and compare notes to prove that the exchange cannot be playing games with the numbers by showing the same funds to multiple people.

## Blockchain Proximate Transactions

The spiritual ideological foundations of Bitcoin are those of the crypto-anarchist movement, which promote the value of encryption and efficient information transfer and attempt to avoid trusted systems. From this perspective, even strong trust mitigating tactics may be seen as imperfect or insufficient if a small number of trusted custodians are necessary.

With the goal of avoiding trusted custodians in mind, off-chain applications are still possible through two potential methods. The first method would create new similar structures to the Blockchain ledger, with a set of distributed judges who would determine the state of the network. These judges might be in an open competition for fees, as they are in Bitcoin, or a large set of trusted individuals or companies, or even the Bitcoin miners themselves.

These ledgers would then synchronize with the main ledger using a series of swaps, which would lock coins on one side and free coins on the other side, giving a one to one exchange rate. This idea is known as a *pegged sidechain*, and it would allow for a completely different rule set on the other ledger, while maintaining the value peg to Bitcoin in a trust-minimizing way. A major issue with this proposal is that the sidechain judges would still have to have trust invested in them to not end their cooperation and attempt to unlock funds from the sidechain using a forged history.

The second more secure proposal for trading Bitcoin off-chain is through the use of signed but not published Bitcoin transactions. This concept uses transaction multiple signature fund locking and timeout features to create funds that are invested in a relationship between two users, who may then update the state of their relationship out of band with the Blockchain.

If there is a cooperation failure, neither side may claim funds on the Blockchain that are not theirs because they are missing the appropriate signature and they are also protected by a resetting timeout function that restores funds after a period in which the relationship is proved to be non cooperative. This proposal is called *payment channels* and exists in the form of libraries such as 21 computer and BitcoinJ, and in the form of services such as 21 market services and the streamium.io video streaming service. This is also the foundational concept used by the Lightning Network proposal, which is essentially a network of payment channels.

## Bitcoin Backed Currency

As Bitcoin was modeled upon gold, it may be used just as gold and silver were used to back currency in a model that served the world economy for much of human history and is still a highly regarded option in many circles. In this model, existing currencies would simply switch the meaning of their existing notes to peg their currency to a Bitcoin amount. 

This peg could be accomplished by the governments in question purchasing large sums of Bitcoin to hold in reserves, allowing for exchange at a fixed and published rate. This could be done even in part, with a country holding a basket of assets that would install confidence in a currency not being adjustable at the whims of a voting public or a ruling sovereign.

In this system, every exchange of paper notes or bank transfers could be thought of as an off-chain exchange of Bitcoin. A crisis in confidence in the note would be immediately obvious in non-official market prices. As an improvement over gold and silver backed currencies whose assets are frequently called into question, Bitcoin could allow for mathematical certainty as to asset accounting accuracy.

