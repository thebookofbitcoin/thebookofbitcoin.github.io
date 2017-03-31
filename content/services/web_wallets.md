# Web wallets

The **web wallet** concept is a wallet which is served as a web application. This concept can be split into multiple separate concepts: custodial wallets that function like banks, signatory wallets that function like notaries, and javascript wallets that function like software wallets in miniature.

There are some similar security and privacy concerns with all web wallets, because the Web's trust model of clients trusting servers is not compatible with Bitcoin's open source software trust model of using well vetted independent software to provide security and privacy. Web pages are also so ubiquitous and amorphous that they are particularly vulnerable to social hacking and phishing attacks, where users are tricked into revealing their credentials and therefore access to their Bitcoins by being presented with a web page that appears similar to the one that they trust, but is in fact run by a malicious operator. 

## Custodial Wallets

A very common practice for web wallets is to treat client funds as deposits into a large fund, and then trade the funds for account credits in a private database, offering the advantages to the service operator that centralized software can bring via the efficiency and simplicity of only changing local records.

In this method, the wallet operator takes custody of the funds, so it is widely considered to be a large degradation in the trust model of Bitcoin and something to be avoided. Custodial wallets open up a large attack target for theft: coins spread out in a diverse landscape of security systems can present a harder target than coins concentrated behind a single known security wall. A user might not even realize that their funds are missing, if the service does not practice [proof of reserves](https://iwilcox.me.uk/2014/proving-bitcoin-reserves).

Another reason that custodial wallets are not recommended is their total lack of privacy: any transaction that is made on the system is done by proxy, therefore the service operator has full and complete knowledge of every single transaction made by every single user.

In some circumstances, people may want to willingly forsake the security and privacy benefits of cryptographically secure wallets. They may not trust themselves with their own security, or they may be willing to make the trade-off for other benefits of a trusted third party, at least for some limited amount of funds. The most common example of this is depositing funds into a Bitcoin exchange, where a centralized system is extremely beneficial to rapid trading in an order-book marketplace. 

Custodial wallets have the ability to operate more quickly and efficiently than the Blockchain, because they do not have to make the same costly decentralization guarantees. When using a custodial wallet, one should always use a multiple factor authentication mechanism to authenticate due to weaknesses in standard web authentication systems.

## Signatory Wallets

It's well understood that custodial wallets represent a threat to the agency of funds, but it's also understood that individuals may have difficulties being responsible for the safety of their own funds. Fund transfers at the start of Bitcoin were a simple affair of sending from one person to another, but Bitcoin's fundamental design was intended to power more advanced use cases, one manifestation of which is the multiple signature or *multisig* wallet. In normal Bitcoin transactions only one signature is necessary, in a multi signature wallet, a combination of multiple signatures is necessary.

Using a system of multiple entities in shared control of funds using multisig transactions, some web wallets simply act as a trusted signatory to funds that are ultimately controlled by standard software or hardware wallets. For example, a user can create a two of three multi-signature wallet, where a web site has one key, a hardware device has another key, and a third key is written down only in a secure location on paper. In this setup, the web site cannot move funds without the cooperation of the hardware device or the paper key, drastically reducing the trust required in the web service. Typically the web wallet then serves as a check on the power of the standard wallet: even if that wallet is compromised, the web site must also be simultaneously be compromised for there to be a loss of funds.

Unfortunately, this separation of signatures is not always a simple situation to coordinate. Even though the separation improves security significantly, it is not a panacea. Signatory wallets often setup the keys in suspect ways, don't keep a clear separation between the methods, and the scheme is weakened to various degrees. For example, if a web wallet generates all the signatures itself and just guarantees it does not keep them, or it keeps two signatures but one encrypted with a user's pass phrase and does not compel a user to use a strong pass phrase, or commits one of a multitude of other various other slip-ups, the process can still be attacked and funds can be lost. 

From the privacy perspective, users still are forced to share financial information with the signatory, so the web service operator must be one who can be trusted to keep and not abuse the privacy of the user's privileged information.

## Javascript Wallets

A Javascript Wallet is designed as a standard software wallet, but delivered in a web page package. This gives the advantage of reducing lock-in to the web service provider, reducing exposure to custodial service security breaches, and increases the self-determination of security through encrypting private data on the client and not sharing it with a trusted server. However these wallets come with a lot of disadvantages and are generally seen as unsafe due to their drawbacks. 

One of the most serious drawbacks to any software delivered via a standard Web method is that the server can quite easily make arbitrary alterations to the software that are not secure or not expected and the user has very little recourse against this. Some web wallets have attempted to promote the use of browser extensions to protect against this vulnerability, however this is not something browsers are designed to do and the security of this methodology has been shown to be generally fairly weak. 

Another unfortunate drawback to Javascript wallets is that the standard set of APIs available to web developers is seriously lacking in the cryptographic API set of functions. Sensitive information not being easy for the developer to secure or handle means that there is a greater likelihood of security error. Weak Web cryptography APIs also include weak randomization APIs, a critical security element in using Bitcoin security, since Bitcoins are controlled by a secret random number: if the number is not sufficiently random, the Bitcoins may be stolen.

From a privacy perspective, Javascript web wallets are quite similar to the other web wallets: they tend to leak financial details of users to the web service operator. Even worse, Javascript wallets tend not to validate the data sent back from the web service, making them particularly vulnerable to man in the middle attacks that could put users at risk of loss of funds.

Although browsers are generally considered to be a secure environment, it's often the case that there are still periodic security problems, due to the fact that a browser is also a highly shared environment and a high value target for finding vulnerabilities. Cross site scripting attacks, privacy leaks, and other similar problems are common in web applications, particularly Javascript ones. Using a software or hardware wallet implies a logical firewall of separation from third parties that is not present in a Javascript web wallet.

