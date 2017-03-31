# Bitcoin Storage

It's said that Bitcoin allows someone to be their own bank. This means that when it comes to money Bitcoin users are only beholden to themselves: no third party can dictate to a Bitcoin user how they may spend their money. However this principle of self-determination also means that when it comes to security Bitcoin users have only themselves to rely upon.

There are a wide variety of ways to use Bitcoin, which means that securing Bitcoin is not a one-size-fits-all proposition. Generally though, there are two recommended configurations for using Bitcoins: hot and cold wallets. Hot wallets optimize for ease of spending and movement, cold wallets go the other way and optimize for difficulty of movement to prevent theft. 

## Hot Wallets

Hot wallets are where Bitcoin commerce happens, coins can flow in and out with the minimum of resistance needed to prevent theft. There are many use cases where a hot wallet is appropriate: receiving payments from third parties, making small daily purchases at points of sale, regular or bulk fund transfers to generic endpoints, and converting to fiat to send an outside currency.

### Receiving Payments

For receiving payments, it's recommended that the highest levels of validation be used. Even receiving funds from a trusted person may be suspect, the chain of trust is only as solid as its weakest link, if the trusted person re-sends coins from an untrusted third party, then the trusted person's funds cannot be trusted.

A strong user flow for this use-case is to use a strongly validating wallet as a proxy. Any funds that are known to have been validated by a strongly validating wallet are safe, even when transferred to a weakly validating wallet: the worst case scenario being that they do not transfer to the weakly validating wallet successfully.

Recommended strongly validating wallet:

- Bitcoin Core (Linux, OS X, Windows) - https://bitcoin.org/en/download

### Mobile Payments

For sending payments on the go or casual payments online, a mobile wallet is seen as a fairly secure option. Although it's unwise to store large amounts on a mobile wallet due to the risk of device loss or theft, a small amount of money on an iPhone or Android is seen as practical as long as those platforms' default security mechanisms have not been bypassed and well-vetted software is used.

Recommended well-vetted mobile wallets:

- Breadwallet (iPhone) - https://itunes.apple.com/app/breadwallet/id885251393
- CoPay (Android, iPhone, Windows Phone) - https://copay.io/
- GreenBits (Android) - https://play.google.com/store/apps/details?id=com.greenaddress.greenbits_android_wallet
- Mycelium (Android) - https://play.google.com/store/apps/details?id=com.mycelium.wallet

### Regular Spending

For transferring larger amounts of funds or making payments from small to large, it's useful to have a wallet that tempers extreme security with ease-of-use. The most effective way to achieve this utility is through the use of *MultiSig*, a feature of Bitcoin that allows multiple independent signatories to cryptographically sign off on outgoing fund transfers. This method is seen as highly secure: an attacker attempting to purloin funds must simultaneously compromise multiple independent devices in order to perform an unauthorized spend.

Other security methods are possible that separate and isolate potential attackers, such as crafting transactions on an offline or single purpose computer, but the inconvenience of those methods may lead to their disuse, whereas a multiple signature flow can be simple and closely follows the general security industry best practice of requiring multiple factors for authentication. Using a desktop wallet for regular spending is recommended, due to the standard desktop security model that places reduced trust in the platform vendor. 

Recommended MultiSig wallets

- Electrum (Linux, OS X, Windows) - https://electrum.org/
- CoPay (Linux, OS X, Windows) - https://copay.io/

### Fiat Spending

A Bitcoin user may stand apart from fiat and never touch it, but in practical reality no man is an island and the necessity or desire to interact with a fiat accepting merchant or a less enlightened individual may arise. To ease this process, custodial wallets and debit cards have been developed as compact convenient fiat exchanges. A user simply stores some Bitcoin with a service; when a fiat spend is requested the service automatically performs a market trade and completes the spend. Although generally speaking custodial wallets are not recommended, in the case of spending fiat they are a practical best solution.

Recommended Fiat Spending Solutions

- BitPay Visa: https://bitpay.com/visa/
- Circle: https://www.circle.com/
- Shift Card: https://www.shiftpayments.com/card
- Xapo Card: https://xapo.com/card/

## Cold Storage

Many users of Bitcoin have absolutely no need to access the majority of their funds on a day to day basis. To take advantage of this fact, these users can dramatically improve the security of their funds by placing them in a difficult to access cold storage wallet. Many solutions have been created for this use case, but generally speaking there are two broadly useful ways to accomplish cold storage: hardware wallets and HD backup seeds.

### Hardware Wallet

From a security perspective all software wallets are extremely problematic: they share a platform with other programs, any one of which may be malicious and abscond with user funds. Platform security features, dedicated computers, or software defensive programming can mitigate the problem but from a logical security perspective the surface area open to attack is much wider than absolutely necessary. A hardware wallet device addresses this problem by being designed specifically to be logically separate and single purpose, minimizing risk of unauthorized fund transfer.

Recommended hardware wallets:

- Digitalbitbox: https://digitalbitbox.com/
- KeepKey: https://www.keepkey.com/
- Ledger: https://www.ledgerwallet.com/
- Trezor: https://bitcointrezor.com/

### Backup Phrase

Every wallet stores a set of data called *private keys*, these keys are simply secret random numbers that are used to sign all fund transfers. If wallet files are deleted, and no backup is made, this can mean a loss of funds for the wallet owner: since he can no longer sign a transfer, he can no longer spend his funds.

To avoid this scenario, all that is needed is a backup of the private keys. Not only is this important for securing funds, it can be used as a method to secure funds in a cold way. By deliberately and securely erasing a hot wallet and keeping the backup out of the reach of any network or computer, the funds are logically separated it from the possibility of remote theft.

The best way to accomplish this is a durable and simple system called a Hierarchical Deterministic Seed, or *HD* seed, a system formalized in Pieter Wuille's Bitcoin Improvement Proposal [BIP 32](https://github.com/bitcoin/bips/blob/master/bip-0032.mediawiki). Essentially, this backup scheme specifies a single random number that is used as a starting seed to deterministically generate a lot of other random numbers, or private keys, to be used by a wallet instead of many individual isolated random numbers that must be collectively backed up.

The big advantage to this system is the extreme ease of backup and restoration: a seed can be encoded as a simple set of twelve words, which are easily written down. Users should keep at least three copies of their seed in separate, secure places, inclusive with a software or hardware wallet using the seed. Various mechanisms exist to improve the durability of stored seeds: laminated paper, safe deposit boxes, safes, etc. Writing down the seed is preferable to printing, as printers and the chain of printing may leak a copy along the way.

