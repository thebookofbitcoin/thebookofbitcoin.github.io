# Deterministic Wallets

Bitcoin Wallets generate and store the private keys that control a user's funds. These keys are simply random numbers, chosen by the wallet from a range of numbers so vast that it is essentially impossible for there to be a collision with another wallet doing the same thing. **Deterministic wallets**, also known as **HD wallets** help to simplify backing up and restoring wallets by using a random seed number to deterministically generate all of a wallet's private keys.

## Private Key Backups

Whenever a Bitcoin user receives funds, they need a new private key. This means that the set of numbers that are important to store and back up is increasing indefinitely. In the original Bitcoin wallet, this required refreshing a back-up with a new one every time a user received funds.

Over time, Bitcoin grew more valuable and this burden of security grew more tiresome and costly. To address the issue Satoshi Nakamoto in October of 2010 released [Bitcoin version 0.3.14](https://bitcointalk.org/index.php?topic=1528.0) which contained a *key pool* feature. This feature automatically pre-generated a set of keys, to remain in abeyance for the user's next receipt of funds. This made backing up a much less frequent necessity, only being necessary after key pool exhaustion.

Over the following years, many other methods of improving key backups were tried. A popular concept of a *paper wallet* arose: printing a private key onto paper to store in a secure location. However this concept fell out of favor as being too complicated, vulnerable to printer information leaks, and encouraging address re-use.

## Type 1 Deterministic Wallets

In August of 2011 Mike Caldwell sought to simplify and streamline the process of managing a collection of private keys. [He created](https://bitcointalk.org/index.php?topic=34163.0;all) a Windows application called *Bitcoin Address Utility* that used a single random pass-phrase to deterministically create private keys from a single seed: essentially choosing one random number and then feeding it into a formula that would always produce more random numbers from the starting one.

This created a much easier way to backup private keys: simply secure the original random seed and restoring becomes a simple exercise of running the seed through the algorithm again.

## Type 2 Deterministic Wallets

Mike Caldwell's Type 1 deterministic wallet design was based on a simple scheme that had a significant limitation: to receive funds with a Type 1 wallet required also having access to the private keys that could spend them. In situations such as merchant scripts or exchange wallets, this represented a security issue.

Before Mike Caldwell published his Type 1 wallet, in [June of 2011 Greg Maxwell had already outlined](https://bitcointalk.org/index.php?topic=19137.msg239768#msg239768) a theoretical improvement to the Type 1 scheme, in which the public and private key generation might be separated to improve the security of stored funds. In Greg's outlined Type 2 scheme, a script could use what is called a *master public key* to generate new addresses, without ever being able to spend those funds.

In February of 2012, Pieter Wuille came up with a formalization and standardized version of this concept, [in BIP 32](https://github.com/bitcoin/bips/blob/master/bip-0032.mediawiki). A surge of wallet development activity followed the deterministic wallet concept. Since the master seed behind the wallet may be represented as a simple series of twelve words, it was widely considered to be the superior method for Bitcoin wallet private key generation.

Alan Reiner was the first to implement a Type 2 seed in Armory Wallet, and helped give feedback to the BIP 32 formalization. Since then, every major wallet has moved to support the feature.

## BIP 44 Deterministic Wallets

After BIP 32, development of Type 2 deterministic wallets progressed to a state where additional features and standardization was sought to be defined. In April of 2014 Marek Palatinus, also known as *Slush*, and Pavol Rusnak, Slush's employee at his company SatoshiLabs, sought to advance the state of deterministic wallets by adapting advancements in their own Type 2 hardware wallet Trezor into a standard they authored in [BIP 44](https://github.com/bitcoin/bips/blob/master/bip-0044.mediawiki).

Features promoted by the BIP 44 standard included a mechanism for internal pass-phrase protected accounts inside of a wallet seed, a standard for using the wallet seed across multiple chains, such as for Bitcoin Testnet, and an increased standardization of gap limits and change address separation.

## Deterministic Wallet Caveats

Despite the huge improvement in the state of Bitcoin technology that HD wallets represent, there are some outstanding issues and drawbacks or gotchas that may present difficulties.

Deterministic wallets generally present users with a dictionary derived random pass-phrase that actually represents a master seed number in a form that is easier for humans to deal with. But this ease-of-use has sometimes tempted developers into allowing users to set their own pass-phrase, a very bad idea. Users are extremely bad at choosing a properly random pass-phrase, and this behavior can lead to loss of funds. For this reason, all well-maintained wallets have ceased the practice of encouraging users to invent their own pass-phrases.

Another issue that sometimes confronts users in unexpected ways is that the seeds created by deterministic wallets should not be shared between wallets from different software projects. The reason for this is that the standard for deterministic wallets is generally not actually adopted by all wallets, or there are still areas left unspecified. Due to these small differences, seeds may superficially appear to be share-able between wallets, but in actuality leave some coins difficult to access from the non-originating wallet. To switch between deterministic wallets, the best practice recommendation is to initiate fund transfers on the Blockchain.

From a security and privacy perspective, under normal circumstances a deterministic wallet is just as good as a wallet in which random keys are individually generated. However use of the public master key can prove the exception to that rule. Although it is called a *public* master key, for privacy reasons it should not be shared publicly, as it can link all wallet addresses together. Another important reason it should not be shared is that if a single private key derived from the private seed is leaked and the public master key is also known, all the other private keys may be derived as well. This type of theft is quite uncommon, but for these reasons it is strongly recommended that the master public key still be treated as guarded information.

One practice that must differ between using an individually generated wallet and a deterministic wallet is the practice of creating addresses that are never used. HD wallets have a key implementation detail in the way that they calculate wallet balances: they go through their deterministic algorithm sequentially to determine if each private key has been used, stopping when no further activity is detected. This is a critical optimization, an HD wallet cannot scan endlessly or know automatically all of its balance information without individual queries. To provide a safety margin, HD wallets use something called a *gap limit*, which represents the number of keys checked that have no activity before the balance query will cease its sequential checking. This gap limit can means that creating many addresses that are never used is a bad practice and can lead to users mistakenly believing their funds have been lost, if more unused addresses are created beyond the gap limit safety margin.

A powerful feature of BIP 44 HD wallets is the internal pass phrase account system. This feature addresses a common security concern amongst people who worry about keeping their seed backups secure from theft: it adds an internal password to the stored seed. The feature also powers another use-case, a scenario in which the owner is confronted with the seed and forced to give access to it. As a precautionary measure, the owner may create a red-herring pass phrase and a real pass-phrase, pretending that the red-herring phrase contains the entirety of the funds when forced to open the wallet under duress. But with this power also comes risk deriving from any situation where users choose pass phrases to remember. Human generated pass phrases should generally be considered weak: a brute-force attack can most often bypass them. And memorized pass phrases can be easily forgotten, leading to an annoying situation where funds are temporarily inaccessible, or if a truly strong pass-phrase has been chosen, permanently lost.

