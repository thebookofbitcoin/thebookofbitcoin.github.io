# P2Pool

Most mining pools essentially rent hash power from hashers and steal hasher's agency of choice in crafting blocks in the process. This works to reduce the durability of Bitcoin by adding weak central points that can be more easily pushed into participating in network harming acts. Not all pools work this way, *getblocktemplate* supporting pools such as BitMinter and Eligius allow hashers to sign off on transactions, but this is the exception and not the rule.

The **P2Pool** project seeks to redress the pool centralization deficiency by allowing miners to mine in a pool of hash power without sacrificing their individual decision making powers. P2Pool was [first announced](https://forum.bitcoin.org/index.php?topic=18313.0) by creator Forrest Voight in June of 2011 and began operating the next month.

P2Pool uses a novel method of mining, called *share chain* mining. Share chain mining is similar to Blockchain mining, with the exception that share blocks have a lower difficulty that is more accessible to an average miner. A miner is twenty times more likely to get a share block than a Blockchain block. The share chain achieves this by operating on a lower difficulty targeting system than the Blockchain, targeting a thirty second block.

Share chain blocks are still valid Blockchain blocks, except that they have an incorrect difficulty target, the share chain network is more accepting of blocks. Each share would otherwise be a valid Blockchain block, the restriction on difficulty is simply looser. When share chain blocks happen to align in difficulty with the Blockchain difficulty, they are sent to the Blockchain to claim Bitcoin rewards for the pool

Each share chain block contains rewards pointing back at previous share chain block winners. This is so that when a valid Blockchain block is found, the valid block splits its reward out to the less fortunate miners. The winning block does include a half a percent bonus amount to reward the actual miner who mined it. Donations may be made to the P2Pool in a hashing proportional way by giving funds directly to share block winners.

To avoid the share chain getting out of hand due to its increased block frequency, only a few days of share blocks are kept. This works because share blocks lock a timestamp with the Blockchain, preventing a hidden share chain from being constructed by requiring future unknowable Blockchain information.

- **Website**: http://p2pool.in/

