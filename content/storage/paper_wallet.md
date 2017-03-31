# Paper Wallet

Although computers are needed to work with Bitcoin, they also represent a security and durability threat. Computing devices can be hacked, have errors, get broken, whereas many forms of traditional currency such as gold coins and cash are immune from these particular foibles. **Paper wallets** combine the durability and security of physical currency forms with the digital advantages of Bitcoin, such as redundant storage.

Bitcoin wallets hold Bitcoin funds through *private keys*, simply very large random numbers that are used to represent the identity of a fund's authorized spender. To transfer funds, fund transfer statements are cryptographically signed with the stored random numbers to authenticate the transfer.

When not signing fund transfers, Bitcoin wallets do nothing with their stored private keys, they simply sit in storage, waiting for a transfer. In a paper wallet, the storage of a Bitcoin wallet is serialized to an analog paper form. When the owner of the paper wallet is ready to send the stored coins, the data on the paper is digitized and then used to authorize a transfer.

## Uses

The primary and recommended use for a paper wallet is to backup a digital key, to safeguard against computer or device failure. To make this process easy, a wallet format called *Hierarchical Deterministic* or *HD* has been devised and broadly rolled out to condense all the private keys in a wallet into a single, easily written set of twelve words. This works based on a principle of deterministic number generation, saving a pointer to the start of a mathematical series of numbers that may not be reversed.

Another common use for paper wallets is in the presentation of gifts. To present coins in a traditional physical gift, they may be serialized onto a piece of paper and then opened as a normal gift, with enclosed instructions advising sweep-based importing of the enclosed funds. In this situation, a single standard private key would be the most appropriate option: revealing individual HD private keys is not advisable due to the possibility of compromising the other HD keys, and the security risk of simply sharing a private key with someone else. The gift-giver should also retain a backup copy of the gift, to confirm that the gift-receiver has successfully claimed their gift by sweeping the private key.

To extend the physical metaphor of Bitcoin between trusted individuals, paper pseudo-currency may be constructed using tamper resistant stickers placed on top of private keys with common denominations. The stickers prevent casual theft, the paper tokens represent theoretically claimable Bitcoin. Although this system may work well between trusted acquaintances, the security of the Blockchain design does not extend to this use-case and thus this type of denominated paper wallet scheme should not be extended to non-trusted third parties.

## Formats

The early standard format for paper wallets was a simple standard based off of a serialization of the private key raw number, called *WIF* encoding. In this serialization method, the Bitcoin Address system of limiting characters to avoid look-alike characters is used, as well as the Bitcoin Address system of avoiding typos through a checksum addition. A small indicator to the private key purpose is also added. The checksum and limited character-set means it is very feasible to write out the private key by hand.

Although the early standard of paper wallets proved popular, the later simplification of wallet paper backups that came from HD seeds created a more dependable alternative. HD seeds provide for a more sustainable paper backup, and with BIP44 extensions may even provide for multiple interior pass phrases and multi-chain usage. Outside of a few exceptions, HD seeds are strongly recommended over serialized private keys for paper wallet uses.

## Best Practices

There are a lot of best practices that should be followed with paper wallets, although HD wallets have been designed to reduce the burden of following best practices guidance.

Private key paper wallets should always be swept and never imported. In the case of an HD wallet, importing a private key invites loss, as the HD seed cannot cover arbitrary imported keys. In the case of a standard paper wallet designed to provide logical security from digital based methods of loss, that is compromised by importing.

Private keys are also not meant to be used in isolation, because funds they control may only be sent as a complete unit, and so spending the funds controlled by a private key most often requires a new private key to send the change from the first private key, which complicates life. Since an HD seed represents many private keys, it does not suffer from this issue.

Although paper wallets may be used to secure funds from digital theft, analog theft remains a threat. Proper use of paper wallets involves secure storage, avoidance of recording devices, and key splitting when appropriate. HD wallets suffer from this issue, but due to their compactness are generally simpler to secure.

To address the physical theft issue, a proposal was put forward to encrypt private keys behind a pass phrase. Although this proposal is commonly known as *BIP38*, it is not in fact a standard BIP, the title is a self-styled. HD wallets using the BIP44 standard offer a similar process, taking it a step further to offer multiple pass phrases within a single paper wallet to secure multiple isolated wallets for multiple accounts and plausible deniability. Both of these security measures come with a strong word of warning that they do not offer strong security, and that pass phrases should be kept simple or recorded separately. Pass phrases created by humans are notorious for being either too complex to remember, leading to coin loss, or being too simple to present a challenge to a serious attacker, also leading to coin loss.

When crafting paper wallets, HD or standard keys, critical care must be taken to the environment in which they are created. One method that precludes leaking of the keys is to physically disconnect the key generation method from any communication channel before generating the random key. This logically separates the key from any possibility of remote digital access.

Logical separation from communication channels does not guarantee security. The random generation of a wallet seed or a private key requires that the generating code be true to its purpose. Tainted key generation software has no need for leaking keys, they are essentially pre-leaked to an attacker. To avoid this, a secure software environment as possible is recommended for key generation: avoiding shared platforms such as browsers, or even general purpose computing devices if a hardware wallet is available. Invalid random code may even occur by accident, so well vetted key generation is quite critical to paper wallet security.

Printing paper wallets is a popular option, particularly for single private keys, due to the complexity of characters in a standard private key serialization. However printers should be avoided or treated with caution, as many models cache data, or may be hacked to leak data, leading to a potential loss of funds. HD wallet seeds address this issue by being more user friendly: writing down a set of twelve simple words is a task in which a printer is easily avoided.

