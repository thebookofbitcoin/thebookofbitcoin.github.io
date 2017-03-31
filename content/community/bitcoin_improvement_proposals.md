# Bitcoin Improvement Proposals

The **Bitcoin Improvement Proposals** or BIPS system is a design framework for submitting, reviewing and introducing changes to Bitcoin in a decentralized way. The framework was modeled off of BitTorrent's improvement system, and it was first proposed by Amir Taaki in August of 2011.

BIPs introduce changes in three ways:

1. Informational BIPs describe guidelines or formalize design ideas
2. Process BIPs describe changes in methodology around the development process. 
3. Standards Track BIPs describe network protocol changes, consensus rule changes, or any other impactful protocol changes.

BIPs follow a life-cycle where they are drafted, accepted, and finalized. Drafted BIPs that are not accepted can be withdrawn or redrafted. To update a finalized BIP, a replacement can be submitted to replace it.

## BIP 0001 - BIP Purpose and Guidelines

Amir Taaki proposed the first BIP that defined the BIPs system in August of 2011. Originally modeled after the BitTorrent Enhancement Proposals and named Bitcoin Enhancement Proposals, the name was changed to Bitcoin Improvement Proposals to avoid an abbreviation conflict. 

https://github.com/bitcoin/bips/blob/master/bip-0001.mediawiki

## BIP 0011 - M-of-N Standard Transactions

Gavin Andresen was the first to create a standard type BIP, which outlined a proposal to add a multisig transaction type

https://github.com/bitcoin/bips/blob/master/bip-0011.mediawiki

## BIP 0013 - Address Format for pay-to-script-hash

Gavin Andresen proposed a new address type for P2SH transactions, marked with a leading "3"

https://github.com/bitcoin/bips/blob/master/bip-0013.mediawiki

## BIP 0014 - Protocol Version and User Agent

Amir Taaki and Patrick Strateman proposed a Bitcoin User-Agent standard.

https://github.com/bitcoin/bips/blob/master/bip-0014.mediawiki

## BIP 0016 - Pay to Script Hash

Gavin Andresen proposed a method for creating addresses that supported script based redemption in order to empower multi-sig and other complex transaction types.

https://github.com/bitcoin/bips/blob/master/bip-0016.mediawiki

## BIP 0021 - URI Scheme

Matt Corallo and Nils Schneider adapted Luke-Jr's earlier BIP to formalize a Bitcoin URI standard to make the process of making payments via links and QR more user friendly.

https://github.com/bitcoin/bips/blob/master/bip-0021.mediawiki

## BIP 0022 - getblocktemplate

Luke-Jr formalized a system for sending block structures to hashers instead of just headers, in order to promote decentralization. The system was extended to cover pooled mining in BIP 0023

https://github.com/bitcoin/bips/blob/master/bip-0022.mediawiki 
https://github.com/bitcoin/bips/blob/master/bip-0023.mediawiki 

## BIP 0032 - Hierarchical Deterministic Wallets

Pieter Wuille created a concept for wallets to build out a supply of private keys deterministically from a starting seed value, to make backing up and restoring a wallet a simpler process.

https://github.com/bitcoin/bips/blob/master/bip-0032.mediawiki

## BIP 0034 - Block v2, Height in Coinbase

Gavin Andresen proposed a versioning process for blocks and a block version increase to v2.

https://github.com/bitcoin/bips/blob/master/bip-0034.mediawiki

## BIP 0044 - Multi-Account Hierarchy for Deterministic Wallets

Marek Palatinus and Pavol Rusnak proposed an increased formalization of the deterministic wallet system for standardization reasons.

https://github.com/bitcoin/bips/blob/master/bip-0044.mediawiki 

## BIP 0050 - March 2013 Chain Fork Post-Mortem

Gavin Andresen wrote a description of a problem that led to a disastrous accidental Bitcoin hard fork that led to hundreds of Bitcoins being double spent.

https://github.com/bitcoin/bips/blob/master/bip-0050.mediawiki

## BIP 0065 - OP_CHECKLOCKTIMEVERIFY

Also known as OP_HODL, Peter Todd proposed a new operation code to indicate that a transaction's funds may not be spent until a specified future date.

https://github.com/bitcoin/bips/blob/master/bip-0065.mediawiki

## BIP 0070 - Payment Protocol

Gavin Andresen and Mike Hearn proposed a protocol standard for coordinating the details of a Bitcoin payment, oriented towards the merchant and customer use-case.

https://github.com/bitcoin/bips/blob/master/bip-0070.mediawiki

## BIP 0112 - CHECKSEQUENCEVERIFY

BtcDrak, Mark Friedenbach, and Eric Lombrozo proposed an upgrade to the Bitcoin script to enable transaction scripts based on relative time values. Using this opcode, escrow transactions may include timeouts to avoid a scenario in which funds are stuck through a cooperation failure.

https://github.com/bitcoin/bips/blob/master/bip-0112.mediawiki

## BIP 0141 - Segregated Witness

Johnson Lau, Eric Lombrozo, and Pieter Wuille proposed a large improvement to Bitcoin transactions that clearly split transactions so that all of the data related to the scripting and signing of the transaction was separated into its own demarcated section. Splitting this data out fixes various issues, chief among them a problem called transaction malleability in which duplicate versions of the same transaction could exist on the network.

https://github.com/bitcoin/bips/blob/master/bip-0141.mediawiki

