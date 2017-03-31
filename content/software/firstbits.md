# Firstbits

Although it is considered extremely bad practice to re-use a Bitcoin address for privacy and security reasons, people have not always heeded this recommendation, and so various developers created features on top of address reuse. One such feature was the concept of **Firstbits**, essentially a truncated version of an address that could be used to refer to the first address matching the pattern found on the blockchain.

A now defunct website was created to help identify the matching addresses, and the blockchain.info block explorer also for a time supported the ill-conceived scheme that encouraged users to create many useless transactions for the purposes of registering their Firstbits, abusing the network for a non currency purpose.

Firstbits used a case insensitive search, so the first address to match any case insensitive predict search would be considered the match. The wide flexibility in search caused issues where typos could be squatted to try and take advantage of a mistaken send.

Firstbits was pitched as an easier way to deal with addresses, but that pitch also revealed an issue: only nodes with an expensive index could use Firstbits in a secure and no trust manner. Normal nodes and light clients would have to outsource their queries in an insecure way. This security and privacy problem made using first bits as a universal system basically untenable. 

