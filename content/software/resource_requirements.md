# Blockchain Resource Requirements

A Bitcoin Core node following the standard Bitcoin peer to peer protocol of syncing and verifying transactions is subject to resource limitations imposed by the number and quality of transactions. 

These limitations present a barrier to the Blockchain being used as a universal world wide payment network, existing networks providing tens of thousands or hundreds of thousands of transactions more per second of capacity than is capable for the most powerful servers in the world running full nodes, let alone a widely distributed configuration that is considered to be the most durable for providing the reliability that Bitcoin seeks to offer.

The biggest resource burden on a full node is the verification of transactions; specifically CPU usage is required to calculate transaction signatures and to a lesser degree evaluate smart contract logic. Validation also requires heavy local storage access to find referenced previous funds and confirm the chain of spending.

A standard desktop computer in 2016, using fully optimized signature code would be expected to be able to verify around a maximum of ten thousand signatures per second. There is no way to explicitly state a perfect estimate of verification capability due to the wide array in signature calculation requirements from transaction to transaction. This limitation would assume a perfectly in sync node keeping up with the bare minimum of traffic. Due to catchup situations and spikes in unconfirmed transactions it would make sense to reduce the maximum by around a factor of ten.

A single transaction might present signatures that require a desktop minutes to calculate. Improvements in signature composition and code, transaction standards rules and miner cooperation would likely make minutes a high upper bound for a transaction and only a useful metric for atypical transaction denial of service prevention and safety margin planning.

Another resource limitation for a node for many computers is the pure networking requirements of syncing transactions. A broadband connection capable of syncing one megabyte per second should be able to keep up with about two thousand transactions per second. This assumes a fully duplex connection capable of sending and receiving and a fully caught up node, and perfectly even traffic and no thrown out transactions. 

Unspent transaction outputs are another great consumer of resources. These must be kept in memory, to avoid slow transaction syncing that requires excessive slow disk reads. SSDs may mitigate this issue, but when only memory is available, unspent transactions add one megabyte of permanent resource consumption for every two thousand transactions.

