# Script Codes

## OP_RETURN

The **OP_RETURN** script opcode is used to indicate that a transaction output cannot be spent, which is generally used as a method to store user data in the Blockchain with lower impact than other methods. The network permits up to [eighty bytes](https://github.com/bitcoin/bitcoin/blob/master/src/script/standard.h#L30) of data to be sent this way, although the limit is not consensus critical.

The limit of eighty bytes is an arbitrary limit designed to discourage but not prevent the use of the feature, due to its cost burden on the network for out of scope goals, but also its lower cost characteristics than other methods. Other methods of storing arbitrary data in the Blockchain generally leave spendable outputs, which cannot be easily archived and thus consume additional system memory which is a scarcer resource. In archive resource constricted situations, OP_RETURN marked outputs may even be safely discarded as they can have no impact on future transactions.

