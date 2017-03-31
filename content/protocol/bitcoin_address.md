# Bitcoin Address

An **address** in Bitcoin is a term that refers to an identifier that a Bitcoin user gives to another wallet in order to receive a payment. Although technically this identifier may be reused for successive payments, this goes against recommended best practices for privacy and security reasons. In best practice use, the identifier is treated as a one time use token.

Addresses are composed of 26-34 letters and numbers, with some similar looking letters and numbers removed and a validity checksum included to avoid transcription mistakes.

Addresses are derived deterministically from *private keys*, random numbers that are used to control Bitcoins. This means they can be generated offline without any communication with the Bitcoin network, and they can also be derived through the use of a *hierarchical deterministic*, or HD algorithm that derives many keys from a starting master seed.

## Address Types

The convention for address types is to indicate their type by the leading alphanumeric character.

- Leading character: "1" - PSPKH address. 
- Leading character: "3" - P2SH address.

## Address Reuse

The practice of address reuse is highly discouraged for various reasons. This standard guideline applies both to the situation in which funds are received in multiple transactions without spending, and to the situation in which the wallet spends funds received at an address and then continues to re-use a previously used address.

### Address Reuse Privacy Issues

When a user re-uses an address, it makes Blockchain network analysis much easier to determine both the owner of the address and everyone associated with the owner. Given that all network transactions are connected to each other, this means everyone on the Blockchain suffers when anyone reuses an address. 

A simple example of how privacy is harmed for the re-using user is through Blockchain indexing. For example when a merchant gives out a singular address to multiple customers, the customers can query the Blockchain to see the sum of funds sent to that address, a number the merchant may not wish to reveal. Another customer may also not appreciate being linked so obviously to the merchant, that may be information they wish obscured from public view.

### Address Reuse Security Issues

When a transaction is published to the network, the published transaction reveals a signature authorizing the movement of funds controlled by the private key. There is no known problem with this: the signature uses an algorithm considered completely secure and unforgeable.

However the mere presence of the signature represents additional information that is previously obscured to the network: secret information only the wallet's owner is privy to. If there ever is found a vulnerability that exploits this signature data, if the assumption of signing algorithm security is wrong in some way, private keys without public signature data revealed via signature re-use would be infinitely more secure than private keys where signature data was known. 

### Attempts to Abuse Address Reuse

Even with the known privacy and security issues, there have been attempts made by developers to encourage address reuse, both for usability reasons and to build features on top of the concept. Ignoring the issues with address re-use does not make them go away however, so these attempts have slowly been filtered out of common practice.

One concept to encourage address re-use was the *Firstbits* registration scheme. This rewarded the first use of an address on the network by allowing it to be used as a short name. Beyond the problems of encouraging address re-use, this concept was internally problematic and was only implemented on an eponomyous website firstbits-dot-net and on the much maligned service blockchain-dot-info.

Another concept was the *Green Address* system, named based on a common misunderstanding that transactions include a from address, which is not the case. In this concept, adopted by the now defunct Instawallet and the MTGox exchange services, Blockchain analysis was used to attempt to determine the source of funds from transactions.

One slightly more lasting concept has been the idea of *vanity addresses*, or addresses that are imbued with some desirable pattern or word. To obtain these addresses, thousands or millions of private key combinations are created and discarded to attempt to find a matching pattern. These addresses can carry a small risk that they lull user into a false sense of security, multiple visually similar matches may be easily found by anyone, so a vanity address should still be used cautiously. For some uses of Bitcoin addresses, the alternatives to address reuse are simply not practical, or underdeveloped, and this is where vanity addresses have found their most success.

