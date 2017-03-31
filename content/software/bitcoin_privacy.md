# Bitcoin Privacy

## Mixers

A Bitcoin *mixer*, or *tumbler* offers users a centralized service that folds together funds from various sources to improve the privacy of users funds. 

Mixers are strongly not recommended because they make uncertain promises: there is no guarantee that they are not logging data, operated by a malicious party who may steal funds or fail to deliberately invade user privacy, or simply fail to provide their advertised services.

The recommended way to improve privacy of funds using a mixing method is called a CoinJoin, which is a method that addresses the problems of a mixer using Bitcoin *smart contracts*, specially crafted transactions to mix funds. CoinJoins can be constructed where there is no data to log, where stealing funds is impossible, and where service is guaranteed. There are various methods to facilitate a CoinJoin, the most popular being the [JoinMarket project](https://github.com/JoinMarket-Org/joinmarket).

