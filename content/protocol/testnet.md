# Testnet

The Bitcoin **testnet** is an alternative block chain, created for the purpose of testing upcoming alterations to or new software for the Bitcoin Blockchain. The entire Testnet network is cleanly isolated from the Bitcoin Blockchain, using port *18333* instead of *8333*, dedicated address formats to prevent accidental overlap, and other network rules to prevent any interaction between the two networks.

Standard Bitcoin Core releases support testnet, enabled througha command line switch *testnet=1* to swap out of the main network. Various other wallets provide an interface to testnet, including light wallets such as CoPay. Testnet is strongly recommended as the appropriate place to conduct research and testing, and there is no standard transaction whitelist checking for relaying on testnet, so even advanced future type transactions may be attempted in the sandbox environment.

## Origins

The original Bitcoin client included no test network, coins were valueless and the network constraints limited, implying no pressing need for a separate test environment. As Bitcoin grew in popularity, the forward stability of the network became a more critical consideration and the cost of testing on the main network grew, so in October of 2010 Bitcoin Core version 0.3.14 added support for the test network. 

Testnet met with acclaim, but a pandora's box opened: the concept of a second Blockchain invited a secondary market for coins. As Bitcoin's value grew, some sought to grab an early start on a new market by investing in testnet coins. The difficulty of the network began to rise, making life difficult for testers, and the rising cost of test coins began to make testing expensive.

To combat this, Bitcoin Core abandoned the original testnet and created Testnet2, with the stern warning that testnet's coins were ephemeral and not intended to hold value. Attempting to build a new sustained currency on top of the test network would not be supported, and to preempt any future attempts, developers promised to keep creating new testnets until the futility of attempting to store value in the test coins was made sufficiently obvious.

Testnet2 accomplished its goals of destroying the value of the coins, however a wide disparity in mining hardware started to become apparent to the test network. When incredibly powerful miners would test on the network, they could abruptly leave, putting it in a state where the difficulty could not adjust quickly, impeding testing. In Bitcoin Core's 0.7.0 release in September of 2012, the test network was again reset to create Testnet3 with test-network specific rules to prevent difficulty difficulties by simply resetting difficulty after certain timeouts.

Testnet3 functioned for years without incident, however with the development of the Segregated Witness or *SegWit* feature developed in 2015, a great divergence from the standard consensus logic was seen to present an issue with an overlap on the main testing network. To facilitate isolated development on SegWit, a temporary separate testing network was created in December of 2015, called *SegNet*. SegNet saw multiple iterations as the feature ran through the final stages of testing and development, but eventually the feature was deemed stable enough in May of 2016 to merge into Testnet and shut down the separate testing network.

