Lab Assignment: Inter-Subnet Routing with 4 Hosts across 2 Subnets
Question 1: IP Addressing Table
Device	IP Address	Subnet	Default Gateway
Host A1	192.168.10.10/24	Subnet A	192.168.10.1
Host A2	192.168.10.11/24	Subnet A	192.168.10.1
Host B1	192.168.20.10/24	Subnet B	192.168.20.1
Host B2	192.168.20.11/24	Subnet B	192.168.20.1
Router eth1	192.168.10.1/24	Subnet A	Not applicable
Router eth2	192.168.20.1/24	Subnet B	Not applicable

Question 2: How do devices communicate within the same subnet and between different subnets?
Devices in the same subnet communicate directly using their IP addresses and MAC addresses. They do not need a router.

Devices in different subnets communicate through a router. The sending device forwards the packet to its default gateway. The router then sends the packet to the correct subnet.
Question 3: What is the purpose of a default gateway?
A default gateway is the router address that a device uses to communicate with other networks.

If the default gateway is missing or incorrect, devices may still communicate inside their own subnet, but they cannot properly reach other subnets.
Question 4: What router interfaces are required?
The router needs two network interfaces:
- eth1: 192.168.10.1/24 for Subnet A.
- eth2: 192.168.20.1/24 for Subnet B.
Both interfaces must be enabled and configured with the correct IP addresses.
Question 5: Why must IP forwarding be enabled?
IP forwarding allows the router to receive packets on one interface and forward them through another interface.
