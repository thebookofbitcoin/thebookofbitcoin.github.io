# DoS Vulnerabilities

## CVE-2012-3789

In May of 2012, Sergio Lerner discovered and documented a pair of DoS vulnerabilities in Bitcoin Core - at that time called Bitcoin-Qt.

1. Abusing a mechanism that cached transactions not connected to a block or a previous transaction to force increased memory utilization of a connected node by up to ten gigabytes.
2. Abusing a mechanism that checked transaction history by crafting deliberately convoluted histories to require increased CPU utilization to a degree high enough to halt a node's operation.

Versions 0.5.3 through 0.6.2 were impacted by the vulnerability, which was fixed in 0.6.3, released in June of 2012.

## CVE-2012-4683, CVE-2012-4684

In August of 2012, Sergio Lerner discovered a DoS issue in full nodes that allowed abusing of the alert system to broadcast invalid alert messages that took enough time to validate that a node would cease to function. Another method of attacking the alert system was shown to abuse the incorrect way that the alert system packaged signatures, which allowed for fake alerts to fill connected node system memory endlessly.

Versions 0.3.21 through 0.6.3 were impacted by the vulnerability, and it was fixed in Version 0.7.0, in September of 2012.

## CVE-2013-2293

In January of 2013, Sergio Lerner discovered a DoS attack vector against Bitcoin full nodes that allowed an attacker crafting large numbers of double spend transactions to force a connected node to use hard drive resources at a rate higher than expected.

Versions 0.3.21 through 0.7.2 were impacted: the vulnerability was fixed in version 0.8.0. 

