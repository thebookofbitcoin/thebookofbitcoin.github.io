# GBT

The getblocktemplate protocol, or **GBT**, is a decentralized mining protocol that was developed in 2012 by Luke-Jr as a modern successor to the dated getwork protocol. The design of GBT gives contributing pool hashers more individual control over the blocks they are contributing towards. This is seen as desirable because it distributes the network mining authority more widely, instead of simply amongst a small set of mining pool operators.

Not many pools support the protocol, but there are two pools where it can be used: Bitminer and Eligius.

The protocol uses a series of JSON requests to work through the mining process. First the hasher gets the basic block template to start work against. Then, unlike in a centralized mining pool configuration, the hasher individually goes through all the transactions they have verified to include in the block, building the transactions' merkle root signature to use for their block hash. The hash of all the transactions is then combined with the block template to create the block header to hash against. While hashing, a hasher can request that new transaction data be signaled to him so that he can recalculate the transaction merkle root.

The origin of this protocol was in improvements forrrestv made so that P2Pool could use getmemorypool over JSON-RPC to allow decentralized miners to add transactions to their blocks. Luke-Jr expanded on that work to provide a solution for his Eligius pool, and created a solution that served as a simple compromise between centralized pools and a new system like P2Pool. Luke over time has tried to promote the broad use of GTB by standardizing the concept in [BIP 22](https://github.com/bitcoin/bips/blob/master/bip-0022.mediawiki) and [BIP 23](https://github.com/bitcoin/bips/blob/master/bip-0023.mediawiki), and by creating open source software to make its use easier.

