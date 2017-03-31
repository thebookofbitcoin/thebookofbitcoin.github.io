# Bitcoin Core

**Bitcoin Core** (also known as Bitcoin-Qt) is the cross-platform MIT licensed wallet application of the Bitcoin Core project, which is seen as the reference implementation of Bitcoin and also acts as an all-in-one peer to peer node.

Satoshi Nakamoto originally coded a graphical wallet application for Bitcoin using the wxWidgets interface library in the wallet known as *WxBitcoin*. Over time the Qt library was recognized as a better option, and Wladimir J. van der Laan created *Bitcoin-Qt*. Bitcoin-Qt was later renamed to Bitcoin Core in [March of 2014](https://bitcoin.org/en/release/v0.9.0) as part of an overall brand clarification.

Since April of 2014, Wladimir J. van der Laan has acted as the project maintainer for Bitcoin Core.

## Data Directory

Bitcoin Core stores the blockchain data and wallet data in a placed called the **data directory**. 

Directory Locations:

- **Linux**: ~/.bitcoin/
- **OSX**: ~/Library/Application Support/Bitcoin/
- **Windows XP**: C:\Documents and Settings\$YOUR_USER_NAME\Application data\Bitcoin (Windows XP)
 - **Windows Visa, Windows 7+**: C:\Users\$YOUR_USER_NAME\Appdata\Roaming\Bitcoin (Windows Vista and 7)

Directory files and folders:

- .lock : locking file for BerkeleyDb
- bitcoin.conf - optional configuration file for command line options
- blocks/ - contains the raw block data, a LevelDb indexing database
- database/ - contains the Berkeley Db journaling files
- debug.log - tail of Bitcoin Core's log
- fee_estimates.dat - cache of fee analysis data
- peers.dat - cache of network peers
- wallet.dat - data file for private keys, user wallet data. **Back this up!**

Copying the blocks and chainstate directories to improve sync times on a machine that has not yet synced, however no third-party database files should be used, only files from another trusted machine. When performing this copy, both installations of Bitcoin Core should be off.

## Backups

It's a very good idea to back up the wallet.dat file that is found in the Data Directory. This wallet file includes all the private keys that are required to restore the wallet funds in the case of hardware failure or loss.

Originally it was required that the wallet file backup be refreshed with ever new receipt of funds, later Satoshi Nakamoto added a *key pool* feature that pre-generated many private keys so that funds would be securely backed up within the key pool window.

By default the key pool is set to pre-generate one hundred keys, this may be increased using the command line option *keypool* or adding a line with keypool=# to the bitcoin.conf file, however creating large numbers of keys may be a slow operation, so the limit defaults to one hundred.

## Fixing Stuck Transactions

It is possible that through manually overriding the recommended fee settings, or using an out of date version of Bitcoin Core, that a transaction may become *stuck*. A stuck transaction means that no miner is interested in adding the transaction to their block due to a fee that is out of line with their fee policies.

To remedy this situation, there is a function accessible in the Bitcoin Core debug console called abandontransaction that can command Bitcoin Core to forget about a stuck transaction. This will allow the user to reuse the funds they were trying to send with the stuck transaction in a new transaction with more attractive fees.

The function only works on transactions that are not currently in the mempool, so it may be a good idea to temporarily add maxmempool=5 to the bitcoin.conf file or use that argument on the command line when starting Bitcoin Core to make sure that the transaction is absent.

Another method to resolving stuck transactions is to use the zapwallettxes configuration option, either in the bitcoin.conf file or as a command line option when starting Bitcoin Core.

## Links

- **Repository**: https://github.com/bitcoin/bitcoin
- **Website**: https://bitcoincore.org/

