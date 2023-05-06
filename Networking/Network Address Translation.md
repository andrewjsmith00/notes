# Network Address Translation
You can either have small packets, or lots of IP addresses. So 32 bit IP addresses were chosen. Thats only 4.2 billion IP addresses.

Your router is assigned the internet accessible IP address. Home devices are assigned a private IP address by the home router which is not accessible from the internet.

There is a NAT forwarding table that will decode the private IP from the public IP. NAT is transparent as the router will do all the work.