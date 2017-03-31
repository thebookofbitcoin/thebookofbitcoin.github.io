# Blockchain Info Wallet

The **Blockchain** wallet, also known as [blockchain.info](https://blockchain.info/) wallet, is a Javascript based web wallet with an extremely checkered privacy and security history that accompanies a popular Blockchain explorer on the 
 [blockchain.info website](https://blockchain.info/). The service began in August of 2011, with [Android](http://bitcointalk.org/index.php?topic=74191.0) and [iOS](http://bitcointalk.org/index.php?topic=75673.0) wallets wrapping the Javascript core in March of 2012 and April of 2012 respectively. Blockchain management describes their wallet as open source, however the complete software is not actually offered under an open source license, only the client source is published under an open source license and only intermittently.

## Security Issues

Blockchain has been plagued with many minor and major security issues, from man-in-the-middle attack vulnerabilities to invalid key generation code. These security oversights have resulted in frequent theft of user funds.

In a 2015 security issue with Blockchain's Android wallet, it was discovered that the App was using unencrypted HTTP connections to the third party web site random.org in order to generate the private keys for the wallet. This exposed funds in the wallet to a variety of attacks: man in the middle attacks where private keys could be stolen by network attackers, third party attacks where the operators of random.org could have stolen funds from the wallet, and service change issues where the random.org could stop returning dependably random numbers. The issue was discovered when [funds were in fact lost](http://arstechnica.com/security/2015/05/crypto-flaws-in-blockchain-android-app-sent-bitcoins-to-the-wrong-address/), through an unexpected change in the response data from random.org that led to private keys being guessable and therefore funds being left open to theft by third parties.

In a 2014 security issue with Blockchain's web wallet, it was discovered that random number generation was flawed due to bad code commit. White hat hacker Johoe was able to successfully obtain [hundreds of Blockchain users' bitcoins](https://bitcointalk.org/index.php?topic=581411.msg9774894#msg9774894) by exploiting this vulnerability.

Up until the [end of 2014](https://github.com/blockchain/My-Wallet/commit/98d48a0b5765c6cb42f10c3d07f8b33bef6c5404), the web wallet had a major security issue with the way that it dealt with failures to connect to its real time data service. When the connection failed, it would retry, but the retry would not be encrypted, allowing man in the middle attacks on the private wallet data: an attacker could push invalid data to the web client causing loss of funds. 

## Privacy Issues

In 2012, investor in Blockchain and Bitcoin personality Roger Ver was allowed to have access to the admin panel, which [he abused](https://bitcointalk.org/index.php?topic=131574.0) to publicly reveal private information about someone whom he accidentally sent Bitcoins to in order to motivate them to return the funds. Through this incident, it was also revealed that Blockchain was recording and indexing user information against Blockchain queries, in a way that helped to make compromising user privacy much easier.

The Blockchain wallet offered a service called *SharedCoin* to ostensibly improve the privacy of Bitcoins sent through a special sending mechanism. Sending through SharedCoin promised to match multiple users to share a transaction where funds in the transaction were split up and sent to multiple destinations, obscuring the chain of ownership. However this service's privacy protection was proved to be trivial to defeat, as outlined by Kristov Atlas in his report [Weak Privacy Guarantees for SharedCoin Mixing Service](http://www.coinjoinsudoku.com/advisory/)

The CEO of Blockchain Peter Smith revealed in a blog post in 2016 that his company is monitoring and [compiling statistics about the nature and destination of transactions](https://medium.com/@OneMorePeter/bitcoin-scaling-and-choices-bed96a76e637#.1vnwacxdb) made by wallet users, indicating that users should not have an expectation of financial privacy in using the service.

## Rich Client Security Model

The concept behind the Blockchain wallet is one in which the web client is heavily responsible for the functionality of the wallet, as opposed to the traditional custodial model of web wallets where a server holds the user's account credit information on file and spends and holds from an aggregated set of funds.

The theoretical advantage behind this model is an improvement of security, portability and service legal exposure. 

From a security perspective, custodial wallets often suffer from unauthorized movement of funds, due to the inherent complexities of securing large amounts of funds that also must be available to move quickly at a clients' request. Through fire-walling each wallet's funds off from each other by storing the funds in encrypted files, it is theorized that security breaches should be more limited in scope. Unfortunately, for ease of use reasons, the wallet does not encourage or require a very high level of entropy in encrypted wallet funds, meaning the benefits of this security model are somewhat muted and in some cases, actually could be seen to be at a lower level of security than a custodial alternative.

Originally, Blockchain did not mitigate much against the weak encryption scheme, with wallets being protected against arbitrary attacker download through the use of what they called a "wallet identifier", or a uniquely generated id that served as a kind of password. This identifier suffered from a spate of security issues: users forgot their identifier and requested standard usernames, or users didn't keep their identifier secret. Since the knowledge of the identifier or username allowed an attacker to download the wallet, wallets with weak passwords suffered attacks where users lost funds. The scheme was later improved through rate limiting and multiple factor authentication, which mitigated the issue to a large degree.

From a portability perspective, lack of standardization in wallet files and wallet backups has presented problems for the wallet. In recent iterations this issue was improved, but users of previous versions of the wallet were left to the wind regarding their backup files: backup data present, but stored in a format not straightforward to access.

Legally, the concept of a rich client web wallet has yet to be tested, however that may point towards a vindication of this model. The author of the web service can argue: they are separate and apart from any money transmission, funds transferred are authored and executed by other parties, they are merely the neutral software mechanism.

