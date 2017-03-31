# Bitcoin Proof of Work

In adding to the transaction history of the Bitcoin Blockchain, also known as mining, a **Proof of Work** is the determiner for the individual mining node that is selected to append a block to the Blockchain. The specific proof of work Bitcoin was designed to use is called *hashcash*, which is a proof of work concept that was originally envisioned to limit email spam by imposing a rate limiting cost to send an email.

The Bitcoin hashcash proof is basically a function that takes input data and returns an output signature.

The input data supplied to the hashcash function includes:

- A piece of data to hash against called a nonce
- A pointer back to the previous block in the chain
- The current version
- A timestamp
- A counter
- A signature derived from all of the transactions in the block
- The consensus defined difficulty rating.

The function uses a mathematical hashing formula called SHA256 to create a one-way signature of the input data. The formula is run twice: first on the input data, and then on the signature itself.

