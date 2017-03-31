# The Alert System

The Bitcoin **alert system** was introduced by Satoshi to the Bitcoin p2p network in Bitcoin v0.3.10 to create a system in which important system information could be quickly relayed to all listening clients. Alert messages were cryptographically signed with a private key to prevent abuse. Each message contained an expiration date, a unique id, a target listing of other messages to eliminate, a version targeting message, a priority value and the content text of the message to display.

In addition to the message displayed, alerts triggered an automatic downgrade to "safe mode", which was intended to prevent accidental automated usage of a Bitcoin node in an unforeseen and potentially problematic circumstance. In version 0.3.20 this automatic change mechanism was removed. 

In v0.12.1 the alert system was removed from the client, with the reasoning that it was redundant to other out of band signaling mechanisms and the alert key had become known to too large of an audience.

## Links

- **Historical Alerts**: https://bitcoin.org/en/alerts

