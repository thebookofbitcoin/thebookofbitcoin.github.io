# Bitcoin Release History

Bitcoin Core Versions

## 0.12.1 - April 15, 2016

- Added BIP 9 system for allowing miners to signal multiple soft forks simultaneously
- Added BIP 68 soft fork for allowing transactions to include a relative lock time that locks funds for a time relative to its confirmation time. This is called *CHECKSEQUENCEVERIFY* or *CSV*.
- Disabled the alert system

# 0.12.0 - February 23, 2016 - 94 Contributors

- Upgraded signature validation from OpenSSL to libsecp256k1, making signature validation speed seven times faster, [dramatically increasing overall sync speed](http://altoidnerd.com/2016/01/23/how-long-does-it-take-a-new-bitcoin-full-node-to-sync-to-the-blockchain-does-libsecp256k1-speed-up-the-sync/).
- Added maxuploadtarget option to allow nodes to limit their upload bandwidth utilization
- Made pruned nodes able to relay blocks
- Added maxmempool option to allow notes to limit their memory usage
- Adjusted nSequence usage in transactions to allow for transactions to be marked as replaceable, allowing fee and target adjustment, also called *Opt-in RBF*
- Disabled by default the priority system of favoring some lower fee transactions to be selected for block inclusion
- Started automatically detecting and using Tor if locally present
- Added support for ZMQ announcement of transactions and blocks
- Added historical block data pruning support to the GUI client
- Added discrete signaling of Bloom filter support to nodes
- Added support to the JSON RPC API for passing monetary values as Strings

## 0.11.2 - November 13, 2015

- Added support for BIP 65 feature OP_CHECKLOCKTIMEVERIFY or *CLTV*, which makes funds un-spendable until a future date.

## 0.11.1 - October 15, 2015

- Fixed buffer overflow vulnerability in UPNP, back-ported to 0.10.3
- Reduced transaction malleability problems by strengthening signature standard checking for relaying, back-ported to 0.10.3
- Increased the minimum relay fee to 0.00005 BTC, back-ported to 0.10.3

# 0.11.0 - July 12, 2015 - 77 Contributors

- Added support for pruning to bitcoind, which allows eliminating the large hard drive space usage of bitcoind for users who don't wish to store unnecessary historical data.
- Improved Tor integration by connecting to peers individually through Tor, hardening against a Tor exit node attack

## 0.10.3 - October 14, 2015

- Fixed buffer overflow vulnerability in UPNP
- Reduced transaction malleability problems by strengthening signature standard checking for relaying
- Increased the minimum relay fee to 0.00005 BTC

# 0.10.0 - February 16, 2014 - 100 Contributors

- Improved initial sync time using *headers-first sync*, making sync go as quickly as local hardware can process transaction data, given high bandwidth.
- Started automatically determining fees for transactions based on historical fee data.
- Added REST HTTP interface
- Added libsecp256k1 library to replace OpenSSL for signature creation, which improves signature speed and eliminates variation in signature outputs.
- Began separation of consensus rule code into a packaged library called *libconsensus*
- Removed restrictions on relaying P2SH transactions

## 0.9.2 - June 16, 2014

- Reduced warning threshold for transactions not including a fee to 0.01 BTC from 0.25 BTC
- Added Deterministically built OSX version using gitian
- Added "weeks" label to sync catchup time indicator

# 0.9.0 - March 19, 2014 - 88 Contributors

- Rebranded to Bitcoin Core to clarify distinction between the Bitcoin network and the Bitcoin Core project
- Switched transaction formation to only use low S values to reduce transaction malleability
- Reduced tolerance in transaction formation to reduce transaction malleability
- Added command line option -zapwallettxes to reload wallet transaction data
- Increased block size soft limit to 750k
- Reduced relay fee to 0.00001 BTC.
- Added checkpoint block at 279,000
- Added BIP 70 payment request support and redesign payment request form
- Started showing transaction fees in send confirmations
- Added network traffic graph
- Added support for native OSX notifications, high resolution display on OSX

## 0.8.6 - December 9, 2013

- Increased default block soft limit
- Fixed issues that caused frequent LevelDB block data database corruption issues on OSX

## 0.8.4 - September 3, 2013

- Fixed a DoS vulnerability that could exploit Bloom filter functionality added in 0.8 to crash remote nodes.
- Improved LevelDB on OSX to correct frequent database corruptions suffered on the OSX LevelDB

## 0.8.2 - May 29, 2013

- Changed default fees from 0.0005 BTC to 0.0001 BTC
- Prevented relaying of transactions with outputs lower than 0.00005430 BTC, based on half of the minimum relay fee
- Removed IRC from network bootstrapping

## 0.8.1 - March 18, 2013

- Fixed validation issue deriving from accidental LevelDb block size hard fork with a planned consensus change on May 15, 2013
- Added block checkpoint at 225,430 to force locking to the correct chain in the March 2013 accidental hard fork that continued for eleven blocks

# 0.8.0 - February 19, 2013 - 29 Contributors

- Switched to LevelDB from Berkeley DB for transactions and block data. 
- Parallelized signature checking to improve performance
- Added Bloom filter querying to assist lightweight non-validating clients.
- Fixed privacy issue where change outputs were not random

# 0.7.0 - September 17, 2012

- Implemented BIP 22 / getblocktemplate to improve mining decentralization
- Improved CPU efficiency by avoiding re-validating signatures through caching
- Started prioritizing block space by fees
- Added block checkpoint at 193,000
- Added IPv6 support
- Added Tor support

## 0.6.3 - June 25, 2012

- Fixed a DoS vulnerability documented in CVE-2012-3789
- Added a block checkpoint at 185,333

# 0.6.0 - March 30, 2012 - 26 Contributors

- Added preliminary support for Multisig via P2SH transactions

## 0.5.4

- Started initial support for P2SH

## 0.5.3 - March 14, 2012

- Fixed a DoS vulnerability vector that abused orphan transactions and back-ported the fix to 0.4.4
- Added a checkpoint at block 168,000 to prevent network miner attack and back-ported the change to 0.4.4

## 0.5.2 - January 9, 2012

- Corrected the minimum transaction fee to be 0.0005 BTC and back-ported the fix to 0.4.3
- Added Luke-Jr and Peter Wuille's DNS seeds to network bootstrapping and back-ported the change to 0.4.3

## 0.5.0 - November 21, 2011

- Added an icon to the GUI to reveal network connectivity, a progress bar for blockchain sync status, and a loading screen with a progress indicator for wallet startup.
- Fixed a bug in the 0.4.0 wallet encryption found by Alan Reiner, which was also back-ported to 0.4.1

## 0.4.4

- Fixed a potential DoS vulnerability that could exploit a flood of orphan transactions, or invalid transactions.
- Added a checkpoint at block 168,000 to prevent network miner attack.

## 0.4.3

- Added Luke-Jr and Peter Wuille's DNS seeds to network bootstrapping
- Corrected an error where the minimum transaction fee was supposed to be 0.0005 BTC but it was accidentally set to 0.0001 BTC.

## 0.4.1

- Fixed a bug in the 0.4.0 encryption found by Alan Reiner that meant that the new encryption scheme introduced was not completely secure.

## 0.4.0 - September 23, 2011

- Added wallet encryption and a password confirmation step to send bitcoins.

## 0.3.24 - July 8, 2011

- Made the DNS method of network discovery the default
- Made the UPNP method to bypass firewalls the default

## 0.3.23 - June 14, 2011

- Reduced the transaction fee to 0.0005 BTC
- Reduced the relay fee to 0.0001 BTC

## 0.3.22 - June 5, 2011

- Changed the relay fee to 0.0005 BTC
- Removed the mining option from the GUI

## 0.3.21 - April 27, 2011

- Added UPNP support to enable peer to peer connectivity behind firewalls.
- Added support for sending Bitcoin amounts below 0.01 in the GUI, but also added a mandatory 0.01 fee for sending amounts lower than 0.01.
- Added a new bootstrapping connectivity system using DNS
- First release from Gavin Andresen

## 0.3.19 - December 12, 2010

- Removed safe mode triggering from alerts, which was a temporary measure

Last release from Satoshi Nakamoto

## 0.3.18 - December 8, 2010

- Changed nodes to have a whitelist model for verifying transactions

## 0.3.17 - November 25, 2010

- Re-enabled transaction fee setting (he disabled it in 0.1.5)
- Added limits to free transactions

## 0.3.15 - November 13, 2010

- Switched transaction fees to be based on size

## 0.3.14 - October 21, 2010

- Changed the key generation mechanism to create a pool of keys, to reduce the necessary frequency of backups
- Added support for testnet, a testing mode with its own network

## 0.3.13 - October 1, 2010

- Disabled by default IP address transaction functionality
- Added an option to allow remote JSON-RPC connections

## 0.3.12 - September 7, 2010

- Improved error reporting in the JSON-RPC API


