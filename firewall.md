Firewall

A firewall is a security system used to monitor and control network traffic entering and leaving a network based on a set of security rules.
In simpler terms: A firewall works like a guard at the entrance of a building, allowing authorized individuals to enterand preventing unauthorized individuals from entering. Similarly, a firewall inspects network traffic and decides whether to allow or block it.

-How does a firewall work?
There are two main outcomes:
1. Allow: Allows data traffic to pass.
2. Block/Deny: Prevents data traffic from passing.

Let's say you have a network within a company, and you want to allow employees to use the internet, but you don't want to allow unauthorized connections to their devices. A firewall enforces rules that define which connections are allowed and which are blocked.

-Why use a firewall?

1-There are several reasons for using a firewall:
2-Network Security: Protects the network from unauthorized connections.
3-Traffic Filtering: Filters incoming and outgoing data traffic.
4-Access Control: Controls which devices and services can connect to the network.
5-Threat Prevention: Helps prevent malicious connections.
6-Network Monitoring: Monitors data traffic and logs events according to the firewall's capabilities.

-Firewall types
There are several types of firewalls:

1. Packet Filtering Firewall 
   It inspects data packets based on information such as:
- Source IP Address
- Destination IP Address
- Source Port
- Destination Port
- Protocol
  Then it decides whether to allow or block the package according to the rules.


2. Stateful Inspection Firewall
   It monitors connection state, not just scans each packet individually. For example, it remembers established connections and allows packets from authorized connections to pass.


3. Proxy Firewall
   It acts as an intermediary between the user and the internet. Instead of a direct connection to the server, the connection goes through a proxy firewall, which can inspect requests and enforce security policies.


4. Next-Generation Firewall (NGFW)
   It is an advanced firewall that combines traditional firewall functions with additional security features, such as:
- Deep Packet Inspection (DPI)
- Intrusion Prevention System (IPS)
- Application Awareness
- Advanced Threat Protection


-Firewall types according to usage method
1-Hardware Firewall: A physical device that protects the network.
2-Software Firewall is a program that runs on a computer or server.
3-Cloud Firewall is a firewall service that operates over a cloud infrastructure.


-Windows Defender Firewall: A firewall built into Windows.
-AWS Network Firewall: A firewall service for cloud networks in AWS.

             INTERNET
                 |
                 |
          Incoming Traffic
                 |
                 v
        +-------------------+
        |                   |
        |     FIREWALL      |
        |                   |
        |   Security Rules  |
        |                   |
        +---------+---------+
                  |
           +------+------+
           |             |
           v             v
        ALLOW          BLOCK
           |             |
           v             X
      +----------+    Connection
      | Internal |
      |  Network |
      |          |
      |  PC 1    |
      |  PC 2    |
      |  Server  |
      +----------+
