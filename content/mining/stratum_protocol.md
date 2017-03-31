# Stratum Protocol

The **Stratum** protocol is an open source standard protocol for a server and client relationship between a full node and a light client to synchronize Blockchain data. The protocol, which originated in Electrum, to service Electrum clients from Electrum servers was built upon by Slush in [December of 2011](https://bitcointalk.org/?topic=55842) to coordinate mining for his mining pool. Although the protocol is in quite common use, it is not a BIP standard, its development was done out of band with the common Bitcoin effort.

Slush popularized and [documented the protocol](https://slushpool.com/help/#!/manual/stratum-protocol) in 2012, as a full replacement for the dated *getwork* method. Unlike the less popular *getblocktemplate* and *P2Pool* pooled mining solutions, Stratum avoids the use of a validating full node, lightening resource requirements but also harming decentralization.

