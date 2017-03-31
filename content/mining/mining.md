# Bitcoin Mining

Every Bitcoin arrives into the world through a process called **bitcoin mining**. Bitcoin miners mint new Bitcoin on a transaction system called the Blockchain, which is a shared recording of transactions synced via the Bitcoin peer to peer network. In addition to minting coins, miners are also solely responsible for adding and subtracting transactions from the Blockchain shared transaction record, to facilitate normal payments and movements of funds.

In the early days of Bitcoin, every Bitcoin wallet could take part in mining. While coins minted in the early days of the project were valueless, as Bitcoin's popularity grew over time the minted coins would come to represent a highly prized reward. With this growth in reward valuation mining has shifted from the domain of desktop computers to a fierce competition between expensive and hard to obtain specialized single-purpose Bitcoin mining computers.

## The Blockchain

To mint coins, miners update a public transaction record, called the *Blockchain*, or the *block chain*. The Blockchain transaction system is an open fund transfer system, enabling the miners to introduce new currency for trade, and facilitate the trading of Bitcoin between Bitcoin users. Although anyone may submit a transaction to the miners, only miners may add or remove transactions through a series of updates called *blocks*. Each block encapsulates a number of transactions, including the miner's reward of newly minted Bitcoin. Each block refers back to the preceding block in a chain configuration, hence the name *Blockchain*.

There is one block that does not link back to a preceding block, and that is the original block called the *genesis block* that was first published to the Blockchain in January of 2009 by Satoshi Nakamoto. The coins mined in that block are not spendable. Since Satoshi started the Blockchain, others have come to take over the mantle of updating the transaction record and helping distribute the supply of Bitcoin to the world. Anyone may participate in building the blockchain, as long as they are able to expend energy in a provable way called *proof of work*.

Provable energy expenditure ensures that making changes to the transaction record is visibly expensive to accomplish, reducing the risk of alternative transaction records that could be used to mislead and steal by spending the same money in two conflicting transaction records. Making double spending expensive to accomplish and making the benefits of cooperation outweigh the possible returns of malfeasance gives participants in the Blockchain a way to evaluate their risk when receiving funds. Each block confirms that there was a provable amount of energy expended, establishing authority that there is not another series of conflicting transactions in which a visible payment did not happen.

## Block Rewards

The supply of Bitcoin is designed to be limited, but distributed over time using a system called the *block subsidy*. The limited supply of Bitcoin was modeled after gold coins, and miners of Bitcoin can be thought of as the digital equivalent of gold miners. 

Miners who mine blocks are allowed to print new coins for themselves with every block, with a time-diminishing reward. At the start of the Blockchain the subsidy amounted to fifty coins per block. The reward amount cuts in half every four years, as measured by every two hundred and ten thousand blocks. By 2035 the amount of new coins introduced per year should be under one percent of the total supply, and by 2140 there should be no more coin subsidy.

Miners may claim another type reward in the block, called *transaction fees*. These fees are essentially bids by Bitcoin users to have their transactions included in a block. A miner may only include transactions up to a limit, so it is expected that he will choose the set of transactions with the highest fees.

Fees are intended as a permanent reward for miners. Fees work by transactions inputting more funds than they output, which is allowable. Miners who include transactions in their block are allowed to take the excesses from inputs and add those funds to their own special reward transaction which is called the *coinbase* transaction. As long as a miner does not attempt to claim more Bitcoin in the coinbase transaction than was missing from outputs and is allowed by the block subsidy, he forms a valid block.

## Hashing

To produce blocks that update the Blockchain, miners must perform what is called a *Hashcash*, or a *Proof of Work*, in what is called *hashing*. A Hashcash challenge proves that the hasher did something that took significant energy to complete, in a way that is easily verifiable by any observer. In Bitcoin's implementation of Hashcash, this proof of work is to create a signature of their Blockchain update that matches a challenge pattern that is designed to be difficult to match. Bitcoin's signature method uses an algorithm called double SHA256, so the work of hashing is essentially computing large numbers of SHA256 hashes.

Sometimes hashing is described as a *difficult math problem*, but in actuality the problem is a *easily provably energy spending problem*. It is designed to prove that the miner spent real world resources to create updates, to give an assurance that there is not another set of updates somewhere else that conflicts. Hashers aren't intelligently solving any problem, they are simply finding the solution to an equation by brute force guessing.

To complete a Hashcash challenge, or *win a block*, the miner must search for a block with a hash value that matches a challenge pattern called a *target*. Miners constantly adjust their block, trying many times using random data called a *nonce* to make their block match the challenge pattern. The system is designed to dynamically adjust the challenge difficulty to achieve a ten minute block discovery time, or one hundred and forty four blocks per day. 

Every two weeks, as measured by two thousand and sixteen blocks, the challenge pattern difficulty is adjusted by the network. The adjustment targets a ten minute block discovery time using the previous two weeks' data. The adjustment can go up or down, but due to advances in hashing technology the challenge generally gets harder as time goes by.

## The Mining Game 

Mining has come a long way from the early beginnings of Bitcoin. It took almost a year after Satoshi Nakamoto published the first block for the difficulty to even adjust to a higher setting due to increased competition. The original configuration of desktop mining computers CPU power to find hashes, with all wallets participating in the mining, could not last in the face of Bitcoin's increasing popularity over time.

GPUs were found to be able to mine so much more efficiently than CPUs that they began to make CPU mining obsolete. As GPU mining rose in popularity, Satoshi asked people to avoid it for as long as possible to keep mining distributed, but eventually the tide of GPU miners overwhelmed any possible CPU competition and the mining option was removed from the Bitcoin desktop client visual interface.

An early innovation in mining was to create a pool of effort, or a *mining pool*. The first pool was created by the developer Slush, and he offered miners an opportunity to trade their hashing power in exchange for a share in his payouts. By increasing their chances of winning a block through collective effort, miners were able to minimize the undesirable reward variance inherent in the hashing process.

Mining pools took over the entire spectrum of mining, splitting into a few archetypes: farms to pool the mining effort of a company, decentralized pools like P2Pool or Eligius or Bitminer who seek to combine risk minimization with the distribution of individualized miner decision making, and standard pools like Slush's pool which essentially rent hashing power from contributing miners.

For a short time, there were some movements to upgrade from GPUs to an even more efficient form of mining called FPGA mining, but Bitcoin's value grew so quickly that the final configuration of mining was found in dedicated hashing devices called ASICs. ASIC miners, custom built chips that mine so much more efficiently and powerfully than anything else that they make any other option useless, quickly took over the entire hashing competition.

The first ASICs appeared in 2013, but multiple generations over the years have dramatically improved on the technology so that even older model ASICs are hopelessly obsolete. Unfortunately for Bitcoin's decentralization, the high expense of ASIC production has meant that mining manufacturing companies are also given a unique advantage by vertically integrating. Instead of selling their equipment to a distributed set of operators many ASIC manufacturers choose to mine on their own equipment. This means that mining as an individual became extremely difficult as ASICs completed their dominance of Bitcoin mining.

A common Ponzi scheme that pretends to offer a way for ordinary individuals to still take part in mining is called the *cloud mining* scheme. In this, an up-front deposit is taken to rent mining hardware with, with supposed future payouts from the hardware being given out over time. Instead, the scheme simply takes deposited funds and uses it to pay the payouts. Over time this scheme has fallen in popularity as victims have become burned and knowledge of the scam has spread.

