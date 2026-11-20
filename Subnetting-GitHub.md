This means dividing a large network into smaller networks called subnets. In simpler terms:
Imagine you have a company with 100 computers, and you want to divide the computers into groups:

1- Accounting Department
2- Human Resources Department
3- Information Technology Department
4- Administration Department

Instead of putting all the computers on one network, you can divide the network into smaller networks. Each group will have its own subnet.
![Subnetting network topology](images/subnetting-network-topology.png)

-Why do we use subnetting?
1-Network Organization: Organizing and grouping devices.
2-Security: Helping to isolate networks and control communication between them.
3-Performance: Reducing the broadcast range within each network.
4-IP Address Management: Using IP addresses in a more organized and efficient manner.

-Before we understand Subnetting what is an IP Address?
Every device connected to an IP network needs an IP address to communicate with other devices.
Example: 192.168.1.10

-This is an IPv4 address. IPv4 consists of 32 bits divided into four parts called octets. Each octet consists of 8 bits.
192       .168       .1         .10
 8 Bits    8 Bits    8 Bits     8 Bits
Total = 32 Bits 

-In this example:
192.168.1 represents the network segment.
10 represents part of the device.
![Binary notation of IP address and subnet mask](images/ip-address-subnet-mask-binary.png)

-What is CIDR?
CIDR stands for Classless Inter-Domain Routing. It is a method for writing the length of a network segment using a slash (/) followed by a number after the IP address. Example: 192.168.1.10/24 The number 24 means that the first 24 bits are allocated to the network, and the remaining 8 bits are for devices.