# Block Timestamp

One of the inputs to the Bitcoin proof of work function is a unix epoch time style timestamp. The timestamp may be incorrect up to a limit: the network will reject timestamps that vary more than two hours from the Blockchain median over eleven previous blocks.

Nodes also coordinate a time value in what is called the *network-adjusted time*. To determine this time value, each node takes the median time of its connected nodes and then uses this time value as a canonical time. To resist abuse, this time value can only differ from the local time by a maximum of seventy minutes.

## Year 2106 Problem

The timestamp value is stored as a thirty two bit unsigned integer, which means that the range of times that Bitcoin supports extends to 2106. 

This type of problem is generally referred to as the year 2038 problem, however Bitcoin's timestamp representation can avoid this issue because it uses an unsigned value which doubles its range of time representations.

