# Bitcoin Wallets

## Electrum

The **Electrum** wallet is a project started in [November of 2011](http://bitcointalk.org/index.php?topic=50936.0) to provide a powerful open source light client wallet. The Electrum project also includes a dedicated server that is used to provide service to Electrum light clients, Electrum clients do not connect to random full nodes as some other light wallets do.

Electrum has proven itself to be a well maintained wallet that follows most best practices, wallets are encrypted, wallet data and private keys are only stored locally and never shared with third parties, keys are deterministically generated following the BIP 32 standard, servers are open source and can be self-run, updates are cryptographically signed and no updates or executable code is ever sent to clients.

### Links:

- **Documentation**: http://docs.electrum.org/ (warning: HTTP)
- **Repository**: https://github.com/spesmilo/electrum/
- **Website**: https://electrum.org/

## GreenAddress

The **GreenAddress** wallet is a multi-sig accounts based wallet that offers a cross-platform and mobile solution for storing and spending Bitcoins. GreenAddress follows Bitcoin wallet best practices and modern standards: it is open source, multi-sig and supports BIP 32 HD key generation.

### Advanced Multi-Sig

GreenAddress gets its name through its rethinking of a concept in which trusted entries might be specifically green-lit when sending funds to allow them to make faster off-chain transactions that eventually are trusted to settle on the Blockchain. To achieve this speed improvement, GreenAddress creates multi-signature wallets for users that are time locked into a two of two signature arrangement.

Users cannot spend their money without GreenAddress co-signing, and GreenAddress works to create a reputation for themselves as refusing to co-sign any double spending attempts. If a merchant trusts GreenAddress, they can also trust that any transaction co-signed by them is not a double spend and allow an instant purchase. GreenAddress cannot spend funds without the cooperation of the user, and the user can use the time-lock feature of the wallet to exit with their funds in the case that GreenAddress stops cooperating. The multiple signature setup also serves as a security measure: coins cannot be spent without authenticating separately to GreenAddress.

GreenAddress also offers a more traditional two of three multi-signature arrangement where no time-lock is needed so funds are always fully accessible to the user, but no trusted transactions are possible.

For multi-signature authentication GreenAddress offers a variety of options: phone call confirmation, email, text message, and RFC 6238 time codes.

### GreenAddress Links

- **GreenAddress for Android on Google Play**: https://play.google.com/store/apps/details?id=it.greenaddress.cordova
- **GreenAddress for Android on F-Droid**: https://f-droid.org/repository/browse/?fdfilter=greenaddress&fdid=it.greenaddress.cordova
- **GreenAddress for Chrome on the Chrome Store**: https://chrome.google.com/webstore/detail/greenaddressit/dgbimgjoijjemhdamicmljbncacfndmp
- **GreenAddress for Chrome for side loading on Github**: https://github.com/greenaddress/WalletCrx/archive/master.zip
- **GreenAddress for iOS on the App Store**: https://itunes.apple.com/us/app/greenaddress/id889740745
- **Repository**: https://github.com/greenaddress/
- **Website**: https://greenaddress.it/

## Mycelium

The **Mycelium** wallet, previously known as *BitSpinner*, is a project [first published](https://bitcointalk.org/index.php?topic=293472.0) in September of 2013 to create a mobile wallet with a wide array of features. The Android App is a free download on Google Play.

Mycelium is developed by the European company *Megion R&D* and the client software has been published under a non OSI approved open source license, making it essentially a proprietary wallet product.

The server components of the wallet are completely proprietary and no source is visible. Mycelium's server integrations add a multitude of other features: fiat value hinting in over one hundred and fifty currencies, Cashila support for integrated fiat exchanging with the European SEPA transfer system, and a local trading market for exchanging Bitcoin in person.

Mycelium uses reduced security validation to provide a light client experience, and private keys are generated deterministically using a BIP 32 HD wallet scheme. Tor is supported through a proxy setting, and there is support for spending funds saved in a Shamir's Secret Sharing configuration. A PIN code can be used to secure the wallet, and Mycelium supports various features for cold wallets, including watch-only mode and support for so-called BIP38 encrypted private keys.

- **Repository**: https://github.com/mycelium-com/wallet
- **Website**: https://mycelium.com

