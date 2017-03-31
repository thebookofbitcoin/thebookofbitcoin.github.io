# Bitcoin Transactions Best Practices

The Bitcoin peer to peer network is a shared resource that costs significant resources to keep in operation. To reduce this cost and harden the network against potential attack or downtime, certain usage is discouraged. Discouraging transactions takes many forms, but principally fees are used to create a cost to abuse, and secondarily community effort is taken to discourage harmful use.

Arbitrary data storage has long been considered as a potential abuse of the system that must be discouraged. Satoshi Nakamoto [highlighted this in a discussion](https://bitcointalk.org/index.php?topic=195.msg1617#msg1617) of storing music videos on the Blockchain.

> That's a cool feature until it gets popular and somebody decides it would be fun to flood the payment network with millions of transactions to transfer the latest Lady Gaga video to all their friends...
> That's one of the reasons for transaction fees. There are other things we can do if necessary.

Arbitrary data causes multiple problems in the network, just as a simple networking, computing and storage burden, but also even more abusive forms leave spendable coins in their wake, increasing the memory burden for all validating clients who must save spendable coins in a priority cache.

Basic efficiency steps can also help reduce the network burden, like folding transactions together which saves space. Taking the network for granted can mean services abuse transactions as messages or pings, or simply send transactions for no purpose at all. Some parties deliberately congest the network to show stress test data, or to increase the cost of using the Blockchain, anti-social actions which are difficult to stop.

