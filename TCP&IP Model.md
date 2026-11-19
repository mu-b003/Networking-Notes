
# TCP/IP Model

## **1. Application Layer**

These deal with protocols that handle data directly, such as HTTP (browsing protocol), FTP (file transfer protocol), SMTP (email protocol), and many others.


The Application Layer is the closest layer to the user. It provides the network services that applications need to communicate with other devices over a network.

When you open a web browser, send an email, transfer a file, or access a website, the Application Layer provides the protocols that allow these activities to happen.

Each protocol has a specific responsibility:

- **HTTP (Hypertext Transfer Protocol):** Used to transfer web pages and other web resources between a web browser and a web server.
    
- **HTTPS (Hypertext Transfer Protocol Secure):** A secure version of HTTP that uses encryption to protect communication.
    
- **FTP (File Transfer Protocol):** Used to transfer files between computers over a network.
    
- **SMTP (Simple Mail Transfer Protocol):** Used to send emails between email clients and mail servers.
    
- **DNS (Domain Name System):** Translates domain names, such as google.com, into IP addresses.
    
- **SSH (Secure Shell):** Allows users to securely access and manage remote computers.
    

**How does it work?**

For example, when you type `www.google.com` into your browser:

1. Your browser initiates a request to access the website.
    
2. DNS helps resolve the domain name into an IP address.
    
3. HTTP or HTTPS defines how the browser communicates with the web server.
    
4. The application data is passed down to the Transport Layer.
    

**Important point:** The Application Layer does not mean the applications themselves. It means the network protocols and services that applications use to communicate.

## **2. Transport Layer**

It is the layer responsible for data flow and ensuring its correct delivery, and the two most common protocols are TCP and UDP.



The Transport Layer is responsible for communication between processes running on different devices.

It takes the data coming from the Application Layer and divides it into smaller pieces called segments when using TCP, or datagrams when using UDP.

It also uses port numbers to identify which application or service should receive the data.

For example:

- HTTP commonly uses port 80.
    
- HTTPS commonly uses port 443.
    
- FTP commonly uses ports 20 and 21.
    
- SSH commonly uses port 22.
    
- DNS commonly uses port 53.
    

The Transport Layer has several important responsibilities:

1. **Segmentation:** Dividing large amounts of data into smaller units.
    
2. **Reassembly:** Reconstructing the original data at the receiving device.
    
3. **Port Addressing:** Identifying the correct application or service.
    
4. **Flow Control:** Controlling the transmission rate to avoid overwhelming the receiver (TCP).
    
5. **Error Recovery:** Detecting missing or damaged data and arranging retransmission (TCP).
    
6. **Multiplexing:** Allowing multiple applications to communicate over the network simultaneously.
    

There are two main transport protocols:

### **TCP (Transmission Control Protocol)**

It is a connection-oriented transmission, which is highly precise in data delivery; for instance, it sends a specific segment to the receiver, waits for the receiver to confirm that the segment arrived intact, and only after receiving that confirmation does it send the next segment.

TCP establishes a connection between the sender and receiver before transmitting application data. This process is called the Three-Way Handshake.

![TCP 3-Way Handshake](https://images.openai.com/static-rsc-4/6gwA6gBGeNzuFPpuXdmiAs-vlhGCbPmLWBgI_4xJCZxasydLAwYwM8FCbvaLpPhutfzcMhfoVnohyupfP_Nzx5KP3BexROJjP8T2Ai6setOQ53pzUai8U3spaoDWIONhaiEVa9wLnsHUh8d2wIsoUNo_L2cSoErWphUHRcaQFPA?purpose=inline)

The Three-Way Handshake consists of three steps:

1. **SYN:** The sender requests to establish a connection.
    
2. **SYN-ACK:** The receiver acknowledges the request and responds.
    
3. **ACK:** The sender confirms the response, and the connection is established.
    

After establishing the connection, TCP provides several mechanisms:

- **Acknowledgment (ACK):** The receiver confirms received data.
    
- **Retransmission:** Lost data can be sent again.
    
- **Sequence Numbers:** Each segment has a sequence number to help organize data correctly.
    
- **Flow Control:** Prevents the sender from transmitting data faster than the receiver can handle.
    
- **Error Detection:** Uses a checksum to detect corrupted data.
    

For example, if a segment is lost during transmission, TCP can detect that it has not been received correctly and retransmit it.

For example, if you want to send an important email, speed is not the priority; rather, the accurate and intact delivery of the data is what matters—which is why we use the TCP protocol.

**Where is TCP commonly used?**

- Web browsing (HTTP/HTTPS).
    
- Sending and receiving emails.
    
- File transfers.
    
- Remote server access through SSH.
    

### **UDP (User Datagram Protocol)**

Connectionless transmission: This protocol is not highly precise in its data delivery, but it is extremely fast. It simply identifies that a device needs to receive data and proceeds to send it.


Unlike TCP, UDP does not establish a connection before sending data. It sends datagrams directly to the destination without waiting for an acknowledgment for every datagram.

UDP does not provide built-in retransmission, sequencing, or flow control like TCP.

Its main characteristics include:

- **Connectionless:** No connection establishment is required.
    
- **Low Latency:** It introduces very little communication delay.
    
- **No Guaranteed Delivery:** Datagrams may be lost.
    
- **No Guaranteed Ordering:** Datagrams may arrive in a different order.
    
- **Low Overhead:** It has a smaller header than TCP, which makes it efficient.
    

![UDP vs TCP: Complete Guide to Network Protocols in 2026 | Pinggy Blog](https://images.openai.com/static-rsc-4/LSZKyagzqtEMlm9PzSn1t3MeVT-jP4Ki9h-4jt1Yobdodp_nVL-wIevfWKaYKQjQwFu_ikWjAN-ScBWqYtT_-Jx7m9TKWv4RNgG2sg5aWgBaMkpchommkDvOnZr9qOMGy-RB8mE4xOLaEOqVBJfluNrWNHIBzniY4dBxK52fXt0?purpose=inline)

For example, when we are on a live stream (like Zoom Live), we need the data to arrive in real time, but high precision is not essential; in this case, we use the UDP protocol.

**Where is UDP commonly used?**

- Live audio and video communication.
    
- Online gaming.
    
- Voice over IP (VoIP).
    
- DNS queries.
    
- Real-time streaming applications.
    

**Important comparison between TCP and UDP:**

|Feature|TCP|UDP|
|---|---|---|
|Connection|Connection-oriented|Connectionless|
|Reliability|Reliable delivery|No delivery guarantee|
|Speed|More overhead|Lower overhead|
|Acknowledgment|Yes|No built-in ACK|
|Retransmission|Yes|No built-in retransmission|
|Data order|Maintains ordered delivery|No ordering guarantee|
|Header size|20 bytes minimum|8 bytes|

## **3. Internet Layer**

At the internet layer, the sender's and receiver's IP addresses will be added.

The Internet Layer is responsible for logical addressing and moving packets between different networks.

Its main responsibility is to make sure that data can travel from the source device to the destination device, even when both devices are connected to different networks.

The most important protocol in this layer is IP (Internet Protocol).

There are two main versions:

- **IPv4:** Uses 32-bit addresses, such as `192.168.1.10`.
    
- **IPv6:** Uses 128-bit addresses, such as `2001:db8::1`.
    

![Complete Protocols Master Part 3: Network Layer & IP - Wasil Zafar](https://images.openai.com/static-rsc-4/C6138ZWJBGO4KQ636jKeB4FeAxVSqiXc59QPDXyvn6cJKMNmOFHfcJfe8xmlkXKxDDHAE6wJyQcuKKmwoooHVPLbDqpFWzsxL7C6hakA32PXTl3JQTN758Jr1X5UqbBJXPn3-7JLtJdUz26JtRyTlqlWFAIuf8HBD9h-btX4LGs?purpose=inline)

When data reaches this layer:

1. The Transport Layer passes down its segments or datagrams.
    
2. The Internet Layer adds an IP header.
    
3. The header contains the source IP address and destination IP address.
    
4. The resulting unit is called an IP packet.
    
5. The packet is passed to the Network Access Layer for transmission.
    

**Other important protocols in this layer:**

- **IP:** Responsible for logical addressing and packet delivery between networks.
    
- **ICMP:** Used for network diagnostic and error-reporting messages. For example, the `ping` command uses ICMP.
    
- **IPsec:** Provides security features such as authentication and encryption at the IP layer.
    

**Example:**

Imagine that your computer has this IP address:

`192.168.1.10`

And you want to communicate with a server that has this IP address:

`142.250.190.14`

The Internet Layer adds these addresses to the IP header so that the network can identify the source and destination of the packet.

**Important point:** IP provides addressing and best-effort packet delivery. It does not guarantee that packets will arrive, arrive in order, or arrive without errors. TCP handles reliability when required.

## **4. Network Access Layer (Network Layer)**

This is the layer responsible for routing and determining the path of data. The routing process and IP address take place in this layer.

**Technical clarification:** In the standard TCP/IP model, routing and IP addressing belong to the Internet Layer, not the Network Access Layer. The Network Access Layer is responsible for transmitting data over the local network.

The Network Access Layer is the lowest layer in the TCP/IP model. It is responsible for how data is physically transmitted through the network.

It combines the functions associated with the Data Link and Physical Layers of the OSI model.

Its responsibilities include:

1. **Framing:** Encapsulating IP packets into frames for transmission over a local network.
    
2. **MAC Addressing:** Using MAC addresses to identify devices on a local network.
    
3. **Physical Transmission:** Transmitting data through Ethernet cables, fiber optics, or wireless signals.
    
4. **Media Access Control:** Managing how devices access and transmit data over a shared communication medium.
    
5. **Error Detection:** Using mechanisms such as Ethernet Frame Check Sequence (FCS) to detect transmission errors.
    

![Ada Computer Science](https://images.openai.com/static-rsc-4/SaH4ItKXwwLMRauZpQV-dxWkejH-qJUt2N8-lJPYVc1-mZgGs1pi6T8R4iuqAKfAszvoAwX6Es83oD8KPXxkdBYf2kz3hQmsWoct-_JX5ExfZHGMArcDFHsUvXZ-vavD9BXf-fjcZAektzigUkdgM3ar1l9RhhXrHKPd_t3jhXE?purpose=inline)

**What is a MAC Address?**

A MAC address (Media Access Control Address) is a hardware-level address associated with a network interface.

For example:

`00:1A:2B:3C:4D:5E`

Unlike an IP address, which provides logical addressing, a MAC address is used for communication on a local network.

**How does it work?**

Imagine that your computer wants to send data to another device on the same local network:

1. The Internet Layer creates an IP packet containing the source and destination IP addresses.
    
2. The Network Access Layer encapsulates the IP packet inside an Ethernet frame.
    
3. The frame contains the source MAC address and destination MAC address.
    
4. The network interface transmits the frame through an Ethernet cable or Wi-Fi.
    
5. The receiving device processes the frame and passes the IP packet to the Internet Layer.
    

**What happens when the destination is outside your local network?**

Your computer does not normally send the Ethernet frame directly to the remote server's MAC address.

Instead, it sends the frame to the MAC address of its default gateway (usually a router).

The router receives the frame, examines the destination IP address, and forwards the packet toward its destination through other networks.

**Important protocols and technologies associated with this layer:**

- **Ethernet:** Used for wired local network communication.
    
- **Wi-Fi (IEEE 802.11):** Used for wireless local network communication.
    
- **ARP:** Resolves an IPv4 address into a MAC address on a local network.
    
- **PPP:** Used for point-to-point communication links.
    

# **Understanding How All Four Layers Work Together**

Let's use one practical example: You open your browser and visit Google.

![What are the 4 layers of the TCP/IP model?](https://images.openai.com/static-rsc-4/--lIZqb365a6_fH8iuCbGyiILvFUVBt5PiDO1ki-8r-SQ5FZB0u3NFoIS-u_Y4RX7YUGqgJ3xtIlAt5wnvm27r-fbiycdCiywhgBhXvrRPj1LDP2ClRBQgy_yB2dZv_tD3HPsckBxSxqw3Iyy1XtQhobaQXEhw-dgQHgmTdhWbI?purpose=inline)

|Layer|What happens?|
|---|---|
|Application|HTTP/HTTPS prepares the web request.|
|Transport|TCP or UDP carries the application data using port numbers.|
|Internet|IP adds source and destination IP addresses.|
|Network Access|The packet is placed inside a frame with MAC addressing and transmitted.|

**Encapsulation:**

When data travels from your computer to another device, each layer adds its own information (headers) to the data.

The process is:

**Application Data**

**TCP Segment / UDP Datagram**

**IP Packet**

**Network Frame**

**Bits transmitted over the network**

**Decapsulation:**

When the data reaches the receiving device, the reverse process happens. Each layer removes and processes its corresponding information until the original application data reaches the correct application.
