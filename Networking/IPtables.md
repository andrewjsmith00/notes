# IPTables
## Filter table
Has 3 built-in changes: Input, Output, Forward. Packets being passed through moves through one of these depending on the source/destination of the packet.

Packets from outside the firewall and heading inside will move through input, packets from inside heading outside go through output. Routed packets move through forward.

`iptables` let you add/remove rules from the kernel level firewall.

In creating an `iptables` script, the order of commands matters./