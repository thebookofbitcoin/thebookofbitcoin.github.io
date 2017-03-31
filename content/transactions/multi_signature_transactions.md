# Bitcoin Multi-Signature Transactions

A common type of Bitcoin transaction, probably the most common type after a standard transaction is a **multi-signature transaction**, in which two or more signatures are used to secure Blockchain funds.

A number of Bitcoin clients support the formation and management of multi-signature locked funds. These wallets include Coinbin Bitcoin Wallet, CoPay from BitPay, BitGo, Electrum, and GreenAddress.

## Security Across Devices

The concept of multi-sig was initially pitched by many as an opportunity to improve upon the much lamented security issue of placing funds in the hands of potentially insecure computers.

The security of a multi-signature wallet works through the theory of redundancy, the chance of a failure of one security system is greatly mitigated when combined with one or more independent security systems that must also fail simultaneously. In an ideal scenario, a spending request is propagated between multiple independent signing devices, who each allow the user to sign off on the transaction.

A more specific and practical use of this system can be seen in providers of second factor authentication gateways, such as through Electrum or GreenAddress. Using those wallets, it is possible to enlist the services of a third party to confirm that a second factor auth check such as a Google Authentication token check is passed.

In those two of three signature wallets, a user retains his keys in a split configuration. He keeps two user keys on a paper backup, with one of his keys being stored on a computing platform to run the wallet and a third key given over to an authentication check service. In this configuration, even without the authentication check service cooperation the user may recover his funds from his paper backup. The authentication check service cannot unilaterally move the funds.

## Security Across People

There are many ancient and well developed mechanisms for sharing secrets across multiple people. Even before the Bitcoin network added support for multiple signature transactions, there was an existing method called Shamir's Secret Sharing that could be used to split a secret private key between independent people.

Multi-signature transactions make this process a lot simpler and easier. When using the system with people, a wallet can setup many different configurations for limiting the authority of an individual to unilaterally spend funds. Various user-friendly wallets support these types of transactions, a common example of a multi-signature wallet being the CoPay wallet which can be used to manage the social agreements to send funds.

In few-of-many multi-signature configurations, funds may be distributed into a setup akin to a petty cash drawer, or a spending pool amongst trusted peers. The multi-signature in this case acts to cryptographically prove the identity of the spending party or parties.

In all-of-many configurations, consensus arrangements may be setup between untrusted peers, where every participating member must assent to any movement of funds. One common method of using this arrangement is in payment channels, where the peers setup cooperative timeouts and then swap funds on a temporary balance sheet to improve transaction speed and granularity or to save on fees.

In most-of-many configurations, a pre-set majority of signatories must agree to move funds. This can be useful for representative organizations, to reflect a vote to authorize actions.

## Security With Untrusted Counter-parties

Multi-signature transactions may also be extremely useful when conducting business with unknown and untrusted third parties. Although a common method to alleviating that risk is custodial escrow, multi-signature arrangements offer all of the functionality of a custodial escrow service with the added protection against the custodian absconding with the funds. The [bitrated](https://www.bitrated.com/) web service provides this functionality for buyers and sellers. In theory, the escrow agent might not even need to know the details of a transaction, instead they might merely cryptographically attest to a statement of fact. That alone could be enough to determine the spending of funds, using *oracle* multi-signature transactions.

Another method of performing risk mitigating commerce using a multi-signature arrangement is to setup a trade in which a buyer locks but does not sign over funds for his purchase. The buyer is then somewhat protected against possible seller malfeasance; if he is not satisfied with his purchase he may refuse to sign over the purchase funds. This has the downside of offering a large risk to the merchant and not completely defraying the risk to the buyer; in practice it is not commonly used.

One problem multiple-signatures can help solve is the issue of transaction security speed being slow due to the time necessary to complete a proof of work. Generally speaking it is considered secure to wait for six confirmations, and most services wait for around three confirmations, with the rare low-risk service accepting one confirmation. Since a confirmation may take hours to arrive, a strategy using multi-signature funds is to use a trusted co-signer who publicly certifies that the funds will not be double spent: the security risk involved in trusting unconfirmed transactions.

This method allows a merchant or an exchange to instantly credit the sender with a funds transfer, even though the actual movement of funds will require a later settlement to the Blockchain. The services BitGo and GreenAddress both offer this functionality.

