# Bitcoin Core Block Exchange Protocol

Bitcoin nodes sync blocks with each other using the **block exchange protocol**.

The protocol is based on a series of steps. When first connecting to another node, a node will send its version and receive a version message in response. The node will then send the first node that it completes this exchange with some hashes of blocks that it knows about and ask to be caught up on recent blocks via the request *getblocks*. The hashes of blocks that it sends are spaced out, and there is always a common block to be caught up from: the starting block of the Blockchain, also known as the genesis block.

Nodes catch up out of date nodes by sending them a range of block hashes, through the *inv* message that lists a menu of missing block hashes that it can provide. The out of date node then sends a *getdata* message that pulls down the actual block data. To avoid abuse, nodes reject repeated *getdata* calls for the same block.

Out of date nodes are pulled up to date through a batched sending process. This process sends all the blocks to the out of date node, in pages, with the out of date node interactively asking for more pages as it processes the records. Interruptions in the process reset the sync until the next new block is received via broadcast.

