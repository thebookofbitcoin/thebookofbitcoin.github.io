# CoinJoin

One important problem to be solved in Bitcoin is creating a digital currency that is fungible. Fungibility means that every unit of Bitcoin should be equivalent to every other unit of Bitcoin. In practice, not all Bitcoin units are created equal. Some Bitcoins are linked to crimes, or to famous people, or to nothing, making them more or less valuable than others. To fix this, the **CoinJoin** concept proposes a way to create blind mixing of coins to make following the trail of ownership using Blockchain analysis much more difficult.

CoinJoining takes advantage of two important facts of how Bitcoin transactions work: 

1. Transactions may be formed cooperatively with funds being sent from multiple people and to multiple people
2. Within a transaction the source of transaction funds are not directly mapped to individual destinations of funds.

Using these facts, a CoinJoin simply sets up a transaction in which multiple people join together to send funds in a single joint transaction. Because the inputs and outputs in a single transaction are not linked discretely, privacy compromising information about whose funds are whose is destroyed.

## Advantages and Limitations

One issue with some similar mixing privacy methods is that they require signing funds over to a centralized service to perform the mixing of funds. With CoinJoin, mixing transactions are first formed and published to the group to mix with in an unsigned and not yet valid form. Every member of the transaction can independently evaluate the veracity of the mixing transaction, then cryptographically sign off on it: no alteration of the signed transaction can be made, meaning no trust in any server or other member of the group is necessary.

Another issue with any and all privacy methods is a simple attack in which coin values are used as a uniqueness indicator, allowing an observer to follow coin movement even across multiple unlinked transactions. For example: if a very specific amount of coins is seen to go into a mixing system and then a very similar specific value of coins is seen to exit, an observer has strong circumstantial evidence that those coins are linked, and has no need to follow the transactions in the middle.

This is a very difficult problem to solve, but CoinJoin mitigates the issue by splitting mixed coins into common denominations. All of the members of a mixing group determine common values to leave with, so that within a transaction the transaction destinations are masked behind that uniformity. The excess amounts are not obscured, but the mixed amounts now become much more difficult to relate back to their origins. The process may also be repeated many times with many participants to broaden the spectrum of possibilities and reduce the amount of un-mixed change left over.

## Practical Use

There are some practical challenges presented by the CoinJoin concept, challenges which account for the relative rarity of their use. The greatest challenge presented is coordinating a group of motivated people with whom to mix coins, and coordinating them in a privacy conscious, trust minimizing way.

To solve this, various concepts have been attempted, by far the most popular being the [JoinMarket](https://github.com/JoinMarket-Org/joinmarket/blob/master/README.md) which creates a market in which motivated mixers can pay others to to participate in a mix with them at a market defined rate.

Another important consideration is that CoinJoin must be used in conjunction with the most basic privacy improving mechanism: avoiding address re-use. Since CoinJoins separate coins into masked uniform outputs, the uniformity and separation of funds must be maintained or the coin value matching problem applies. Fortunately with the advent of HD wallets, common wallet practice has dramatically moved in the direction of avoiding address reuse by default. 

