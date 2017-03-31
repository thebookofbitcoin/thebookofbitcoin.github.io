# Bitcoin Peer to Peer Network Protocol

The Bitcoin network is designed to operate in a peer to peer configuration, in a reflection of the overall decentralized design of the system. The network goal is to sync the Blockchain, the transaction record and payment settlement system through which Bitcoins are minted and exchanged with Bitcoin users. A high level view of the network is that of a wide array of individual peers, each helping to broadcast updated Blockchain information across the entire group.

The broadcast sync of the Blockchain and the network setup and operational action are accomplished through a narrow network protocol, consisting of a small set of messages. Most messages are designed with pushing data in mind, to continue to propagate waves of updated Blockchain and peer data to local peers and across the greater network.

## Connecting

All Bitcoin network communication occurs using TCP, the standard Internet protocol for reliable networking. Bitcoin has supported the IPv6 standard since September of 2012, and can be used over a user selected port, with the default being 8333.

When a Bitcoin node is instantiated for the first time, it needs to find a way to connect to the greater network. At the start of the project, new nodes would automatically connect to a hard-coded IRC server, with IRC channels being used to publish and discover IP addresses of network nodes. This bootstrapping process was created in 2011, complementing the IRC system it would ultimately wholly replace. In this system hard-coded DNS address based seeds are resolved to the IP addresses of seed nodes to direct a new node onto the network. Since 2012 Bitcoin Core developers Luke-Jr and Pieter Wuille have operated seed nodes, along with various others over the years.

When connecting to a node IP, a Bitcoin node will send its version as the initial message, in a handshaking process where information about its makeup including its current clock value is published to the remote node. The specific messages used are *version*, which sends the node information, and *verack*, which acknowledges the receipt of the version information. This handshake helps a node define a normalized network clock value: time calculations a node makes are based not off of its own clock, but rather the median time from all successfully connected peers.

After the initial bootstrapped connection onto the network, previously connected-to peers as well as relayed known local active peer information is cached. Nodes are designed to recall other nodes in an archival list. This list of node IPs is cached in order to bypass the node seed stage on subsequent starts. On each network join, a node will consult its cache of nodes, semi-randomly selecting nodes to attempt to connect to, with a prioritization of most recently active.

## Syncing

Once nodes have successfully joined the network, they are then faced with their primary task of syncing the Blockchain. The workhorse message that helps a node accomplish this task is the *inventory* or more precisely *inv* message, which a node uses to push listings of blocks and transactions to connected peers. Inventory messages are simply concise high level identification information, they do not carry any information beyond a listing of blocks and transactions. These messages are published constantly, as novel blocks and transactions are validated and then pushed to other peers to relay the new information.

Specific inventory messages may be requested directly from a connected peer using the *getblocks* message that queries about a specific set of blocks. This message is used to sync nodes that are out of date, such as nodes that are new to the network and must sync the entire blockchain through a long series of *getblocks* requests.

When an inventory message is received, listed inventory of blocks and transactions may be requested through the *getdata* request. This is generally performed when a node receives an inventory message containing novel block or transaction information. In response to the *getdata* response the node returns with a *block* or *tx* message, sending blocks and transactions respectively.

## Syncing to Light Clients

Full nodes may also service the syncing needs of light clients, which some call *SPV* clients after a general proposal made by Satoshi in the original Bitcoin whitepaper. These clients avoid validating the blockchain to provide a more practical user experience at the cost of incurring counter-party risk of an abusive miner or set of miners.

*Filter* message features so that full node could service requests for light clients were added through [BIP 37](https://github.com/bitcoin/bips/blob/master/bip-0037.mediawiki). Light clients uses the *getheaders* message to request that full nodes return Blockchain headers information which are sent using the *headers* message. The chain of Blockchain headers are used to piece together the chain with the greatest proof of work. This is used to verify transactions as being on the longest chain of blocks, with the important caveat that it may be an invalid chain.

Light clients also use bloom messages to request transactions that they care about, they do not ask directly for transactions in an effort to add some slight privacy to the client's financial status, however these efforts have only a small impact and are not comprehensive.

## Peer Announcements

In addition to syncing the Blockchain, the Bitcoin network syncs information about the IP addresses that comprise the network, to provide for sustainable connectivity. Nodes publish to other nodes the set of active peers they know about using the *addr* message, which can contain a list of up to a thousand known active nodes. Nodes can also ask other nodes for an *addr* message using a *getaddr* message. Every twenty four hours every node will broadcast a heartbeat *addr* message, which is passed along to two connected nodes.

General network connectivity may also be tested by a node using the *ping* message, which does nothing other than attempt a connection to verify connectivity.

## Obsolete Messages

In the original Bitcoin protocol, support was present for an IP based sending system. The concept allowed connecting to a node directly to make a transaction. To accomplish that task nodes used messages that were later deprecated and removed. IP based sending was eliminated very early on due to security, privacy, and practicality issues.

Although the Bitcoin network was designed as a group of headless automatons, early in its life various critical defects were found that required aggressive central action to remedy. As a practical solution to facilitate the rapid deployment of requisite fixes, Satoshi Nakamoto devised an alerting system for sending version update messages across the node network.

This system used a protocol message called *alert* to directly broadcast a signed message from Satoshi, to be shown to users to inform them of critical information. To avoid a singular dependency Satoshi shared the signing key with others, which over time became an unnecessary risk to the network. In April of 2016 the release of Bitcoin Core version 0.12.1 eliminated the alert system.

