# Dnsmasq
Dnsmasq provides network infrastructure for small networks: DNS, DHCP, router advertisement and netowrk boot.

It is designed to be lightweight and have a small footprint and be suitable for resource constrained routers and firewalls. It is included in most [[Linux]] distros and the ports systems of FreeBSD, OpenBDS and NetBSD and has full IPv6 support.

The DNS subsystem provides a local DNS server for the network with forwarding of all query types to upstream recursive DNS servers and caching of common record types.
- Local DNS names can be defined in /etc/hosts by importing names from the DHCP subsystem or configuration of a range of useful record types
- Upstream servers can be configured in a variety of convenient ways, including dynamic configuration
- Authorative DNS mode allows local DNS names to be exported to zone in global DNS. Dnsmasq acts as authoritative server for this zone.
- DNSSEC validation may be performed on DNS replies from upstream nameservers to provide security against spoofing and cache poisoning
- Specified sub-domains can be directed to their own upstream DNS servers

The DHCP system supports DHCPv4, DHCPv6, BOOTP and PXE
- Both static and dynamic DHCP leases are supported
- There is a read only TFTP server.

Unused features can be omitted at compile time