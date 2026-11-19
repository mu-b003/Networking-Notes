
## Introduction to the OSI Model

The OSI model (Open Systems Interconnection) is a seven-layer framework that stipulates that any device wishing to communicate over a network must pass through these seven layers. The transmitting device must go through seven stages, and the receiving device must also go through the same seven stages, but in reverse.

The OSI model was developed by the International Organization for Standardization (ISO) to standardize network communication and make it easier to understand how different devices communicate with each other.

Each layer has a specific responsibility, and each layer provides services to the layer above it while receiving services from the layer below it.
![[Pasted image 20261119140540.png]]
**The seven layers of the OSI model are:**

1. Physical Layer
    
2. Data Link Layer
    
3. Network Layer
    
4. Transport Layer
    
5. Session Layer
    
6. Presentation Layer
    
7. Application Layer
    

---

## 7 – Application Layer

The application layer determines the appropriate protocol for the action you are performing and provides that protocol. For example, when you open your browser and enter a URL—such as "google.com"—the "https" protocol is automatically added; this is the protocol used for web browsing.

And when you want to download a file, it uses the FTP protocol, which stands for File Transfer Protocol.

The same applies if you want to send an email; this uses the SMTP (Simple Mail Transfer Protocol) protocol. There are also many other protocols that operate at the application layer.

The application layer is the closest layer to the end user. It provides network services that applications use to communicate over a network.

It does not mean that this layer is the application itself. Instead, it provides the network protocols and services that applications need to exchange information.

**Important application-layer protocols:**

- **HTTP (Hypertext Transfer Protocol):** Used to transfer web pages and other web resources.
    
- **HTTPS (Hypertext Transfer Protocol Secure):** The secure version of HTTP, which uses TLS encryption to protect communication.
    
- **FTP (File Transfer Protocol):** Used to transfer files between computers.
    
- **SMTP (Simple Mail Transfer Protocol):** Used to send emails.
    
- **POP3 (Post Office Protocol 3):** Used by email clients to retrieve emails from a mail server.
    
- **IMAP (Internet Message Access Protocol):** Used to access and synchronize emails stored on a mail server.
    
- **DNS (Domain Name System):** Translates domain names, such as google.com, into IP addresses.
    
- **DHCP (Dynamic Host Configuration Protocol):** Automatically assigns network configuration information, such as IP addresses, to devices.
    

### Practical Example

When you open a browser and type:

`https://www.google.com`

Several things happen:

1. The browser uses HTTP over TLS (HTTPS) to communicate securely with the website.
    
2. DNS helps translate the domain name into an IP address.
    
3. The browser sends a request to the web server.
    
4. The server responds with the requested web content.
    

**Main Responsibility:** Providing network services and communication protocols for applications.

---

## 6 – Presentation Layer

The presentation layer takes data arriving from the application layer—in the form of characters and numbers—and converts it into binary (zeros and ones) so that the device can understand and process it; this process is called translation. Subsequently, it reduces the number of these binary digits—a process known as data compression—which facilitates the transmission process.

This is what we observe when we upload an image to Facebook or WhatsApp: its file size decreases due to what is known as data compression.

The presentation layer also encrypts data before transmission; upon receipt, the receiving device decrypts it using the SSL (Secure Sockets Layer) protocol.


The presentation layer is responsible for ensuring that data is represented in a format that the receiving device can understand.

Different computer systems and applications may use different data formats. The presentation layer helps make sure that information can be correctly interpreted by the receiving system.

It performs three main functions:

**A – Data Translation**

Translation means converting data from one representation or format into another.

Computers ultimately process information as binary data (0s and 1s). However, applications work with different data formats, including text, images, audio, and video.

Examples:

- ASCII and Unicode are character-encoding standards used to represent text.
    
- JPEG and PNG are formats used to represent images.
    
- JSON and XML are formats used to represent structured data.
    

**B – Data Compression**

Data compression reduces the size of information before transmission or storage.

There are two main types:

- **Lossless Compression:** Reduces file size without losing the original information. Examples include ZIP and PNG.
    
- **Lossy Compression:** Reduces file size by removing some information that may be less noticeable. Examples include JPEG and some audio and video compression formats.
    

For example, when you upload an image to WhatsApp, the application may compress the image to reduce its file size and make transmission faster.

**C – Data Encryption**

Encryption converts readable information (Plaintext) into an unreadable format (Ciphertext) to protect it from unauthorized access.

The receiving device uses the appropriate decryption key to convert the encrypted information back into readable data.

For example, when you visit a website using HTTPS, TLS provides encryption to protect the communication between your browser and the web server.

**Important Note:** SSL (Secure Sockets Layer) is an older security protocol that has been replaced by TLS (Transport Layer Security). Modern HTTPS connections use TLS.

The OSI presentation layer is a conceptual way of describing data formatting, compression, and encryption. In real-world networking, these functions are often performed by application formats and protocols rather than by a separate physical layer in the network stack.

**Main Responsibility:** Data translation, compression, and encryption.

---

## 5 – Session Layer

The session layer performs four functions.

### A – Transmission Mode

Here the transmission mode is specified whether it is:

- Simplex Mode
    
- Half Duplex
    
- Full Duplex
    

These modes describe the direction in which data can travel between two communicating devices.

1. **Simplex Mode:** Communication takes place in only one direction. One device sends information, and the other receives it.
    
    Example: Traditional television broadcasting.
    
2. **Half-Duplex Mode:** Both devices can transmit and receive data, but they cannot do so at the same time.
    
    Example: Walkie-talkies.
    
3. **Full-Duplex Mode:** Both devices can transmit and receive data simultaneously.
    
    Example: A telephone conversation.
    

### B – Authentication

When we want to access any server, the server typically asks for information—such as a username and password—to identify who you are.


Authentication is the process of verifying the identity of a user or device.

In other words, it answers the question:

**Who are you?**

Authentication can be performed using:

- Something you know: Password or PIN.
    
- Something you have: Security token or authentication application.
    
- Something you are: Fingerprint or facial recognition.
    

For example, when you log in to a website using your username and password, the website verifies your identity before allowing you to proceed.

### C – Authorization

After entering your username and password and accessing the server, the authorization process takes place. This is the process by which the server determines whether or not you have permission to access a specific file—in other words, it defines your access rights on the server.


Authorization determines what an authenticated user is allowed to do.

It answers the question:

**What are you allowed to access or perform?**

For example:

- An administrator can create, modify, and delete files.
    
- A normal user may only view certain files.
    
- A guest may have limited access to the server.
    

Authentication and authorization are different:

- Authentication verifies identity.
    
- Authorization determines permissions.
    

### D – Session Management

One of the key functions of the session layer is session management. For instance, when you access Facebook while offline, you can still see the images and posts that were present during your last online session. This is because the session layer captures the data that was temporarily displayed on the site and stores it; when you access Facebook again, it retrieves this stored data, allowing you to view it even without an internet connection.


Session management involves establishing, maintaining, synchronizing, and terminating communication sessions between two devices or applications.

A session represents a period of communication between two parties.

Its main activities include:

1. **Session Establishment:** Starting a communication session.
    
2. **Session Maintenance:** Keeping the communication session active.
    
3. **Session Synchronization:** Using checkpoints to help communication resume from a known point if an interruption occurs.
    
4. **Session Termination:** Properly ending the communication session.
    

**What are checkpoints?**

Checkpoints are synchronization points that can help two communicating systems recover after an interruption without necessarily restarting the entire operation.

For example, during a long data transfer, checkpoints can identify how much information has already been processed.

**Important Technical Clarification:**

The Facebook offline example is a useful way to understand stored information, but technically, offline posts and images are generally retrieved from application or browser cache and local storage, not directly by the OSI session layer.

Similarly, authentication and authorization are commonly implemented by application-layer protocols and security systems. They are useful concepts when studying session management, but they are not exclusive responsibilities of the OSI session layer.

**Main Responsibility:** Establishing, maintaining, synchronizing, and terminating communication sessions.

---

## 4 – Transport Layer

This layer is responsible for:

### A – Data Transmission

It performs a crucial function known as "segmentation": it takes data from the session layer and breaks it down into smaller units called "segments" to facilitate the transmission process.

We can observe this in practice when a file download encounters an issue; if we restart the download, it does not begin from scratch—instead, it resumes from the specific segment where the corruption occurred.

Each of these segments contains a port number to identify the application it belongs to, as well as a sequence number to maintain the correct order of the segments, ensuring they arrive in the proper sequence at the receiving device after the reassembly process (de-segmentation).


Segmentation is the process of dividing large amounts of data into smaller units so they can be transmitted efficiently across a network.

At the receiving device, the transport layer performs reassembly when the transport protocol supports it.

There are two important concepts here:

**1. Port Numbers**

A port number identifies the application or service associated with network communication.

An IP address identifies a device or network interface, while a port number helps identify the particular application or service receiving the data.

Examples of common port numbers:

- HTTP: Port 80.
    
- HTTPS: Port 443.
    
- FTP: Ports 20 and 21.
    
- SSH: Port 22.
    
- DNS: Port 53.
    
- SMTP: Port 25.
    

For example, when your computer communicates with a web server using HTTPS, the server commonly listens on port 443.

**2. Sequence Numbers**

TCP uses sequence numbers to identify the position of data in a byte stream.

They help the receiving device:

- Identify the correct order of data.
    
- Detect missing data.
    
- Reassemble the received information.
    
- Support retransmission when necessary.
    

**Important Technical Clarification:**

Resuming a failed file download from a previous point is generally handled by application-layer protocols, such as HTTP Range Requests or FTP restart functionality. It is not automatically performed by the transport layer's segmentation process.

### B – Flow Control

It means that it controls the amount of data being transferred; for example, if you want to send data from a computer to a mobile phone, the computer might send 100 megabytes per second, while the mobile phone can only receive 10 megabytes per second.

For example, if we transmit data at a rate of 100 MB—which exceeds the rate the mobile device can handle—the device will send feedback to the computer to reduce the speed to 10 MB, thereby preventing data loss. Conversely, if the computer is transmitting at 5 MB, the mobile device will send feedback to the computer to increase the rate to 10 MB, ensuring optimal performance.


Flow control prevents a fast sender from overwhelming a slower receiver.

In TCP, flow control is primarily implemented through a mechanism called the **TCP Receive Window**.

The receiving device informs the sender how much additional data it can accept.

For example:

- A sender is transmitting data to a receiver.
    
- The receiver has limited available buffer space.
    
- The receiver advertises a smaller receive window.
    
- The sender adjusts the amount of unacknowledged data it sends.
    
- When the receiver has more available buffer space, it can advertise a larger receive window.
    

This helps prevent the receiver's buffer from becoming overwhelmed.

**Important Difference: Flow Control vs Congestion Control**

These two concepts are related but different:

- **Flow Control:** Protects the receiving device from receiving more data than it can handle.
    
- **Congestion Control:** Prevents too much data from being injected into the network, which could overload network devices and links.
    

TCP uses both mechanisms.

### C – Determine Protocol

Here, we specify the type of protocol to be used for data transmission; there are two types of protocols, which are:

#### 1. TCP (Transmission Control Protocol)

It is a connection-oriented transmission, which is highly precise in data delivery; for instance, it sends a specific segment to the receiver, waits for the receiver to confirm that the segment arrived intact, and only after receiving that confirmation does it send the next segment.

For example, if you want to send an important email, speed is not the priority; rather, the accurate and intact delivery of the data is what matters—which is why we use the TCP protocol.



TCP is a reliable, connection-oriented transport protocol.

Before exchanging data, TCP establishes a connection between the sender and receiver using a process called the **Three-Way Handshake**.

The three steps are:

1. **SYN:** The client sends a synchronization request to the server.
    
2. **SYN-ACK:** The server acknowledges the request and responds.
    
3. **ACK:** The client acknowledges the server's response.
    

After this process, the TCP connection is established.

TCP provides several important features:

- Reliable data delivery.
    
- Error detection.
    
- Acknowledgments (ACKs).
    
- Retransmission of lost data.
    
- Correct ordering of data.
    
- Flow control.
    
- Congestion control.
    

**Important Clarification:**

TCP does not necessarily wait for each individual segment to be acknowledged before sending the next one. It can send multiple segments before receiving acknowledgments, depending on the available window and network conditions.

TCP is commonly used for:

- Web browsing (HTTP/HTTPS).
    
- Email communication.
    
- File transfers.
    
- SSH connections.
    

#### 2. UDP (User Datagram Protocol)

Connectionless transmission: This protocol is not highly precise in its data delivery, but it is extremely fast. It simply identifies that a device needs to receive data and proceeds to send it.

For example, when we are on a live stream (like Zoom Live), we need the data to arrive in real time, but high precision is not essential; in this case, we use the UDP protocol.


UDP is a connectionless transport protocol.

Unlike TCP, UDP does not establish a connection using a three-way handshake before sending data.

It sends independent units of data called **Datagrams**.

UDP does not provide built-in guarantees for:

- Successful delivery.
    
- Correct packet ordering.
    
- Retransmission of lost datagrams.
    
- Flow control.
    

However, UDP has a smaller protocol overhead and is useful for applications where low latency is important.

UDP is commonly used for:

- Live video and audio communication.
    
- Online gaming.
    
- DNS queries.
    
- Voice over IP (VoIP).
    
- Real-time communication.
    

**TCP vs UDP**

|Feature|TCP|UDP|
|---|---|---|
|Connection|Connection-oriented|Connectionless|
|Reliability|Reliable delivery|No delivery guarantee|
|Ordering|Maintains data order|No ordering guarantee|
|Acknowledgment|Yes|No built-in acknowledgment|
|Retransmission|Yes|No built-in retransmission|
|Speed and overhead|More overhead|Less overhead|
|Common uses|Web, email, file transfers|Gaming, streaming, DNS|

**Main Responsibility:** End-to-end communication, segmentation, reassembly, port addressing, reliability, and flow control.

---

## 3 – Network Layer

The network layer does two things:

### A – Logical Addressing

Every device on a network has a unique IP address, which can be used to communicate with it. For example, when you send something by mail, you need to know the recipient's address to ensure that what you send reaches the correct destination.

The network layer receives data segments from the transport layer, adds the sender's and receiver's IP addresses to them, and forms a packet called data unit for the network layer.

Thus, the packet consists of the sender's IP address, the receiver's IP address, and the data segment.


Logical addressing uses IP addresses to identify the source and destination of network communication.

An IP address allows devices to communicate across different networks.

There are two main versions of IP addresses:

**1. IPv4 (Internet Protocol Version 4)**

IPv4 uses a 32-bit address.

Example:

`192.168.1.10`

It is usually written as four decimal numbers separated by dots.

Each number represents 8 bits, so the total length is 32 bits.

**2. IPv6 (Internet Protocol Version 6)**

IPv6 uses a 128-bit address.

Example:

`2001:db8:85a3::8a2e:370:7334`

IPv6 was introduced to provide a much larger address space than IPv4.

**Important Note:**

Not every IP address is globally unique or publicly reachable. Private IP addresses can be reused in different local networks, while public IP addresses are used for communication across the internet.

### B – Routing

The second function performed by the network layer is routing; in short, routing is the process of selecting the best path for data to travel from the sender to the receiver.


Routing is the process of determining the path that packets should follow to reach their destination.

Routers are the main networking devices responsible for forwarding packets between different networks.

A router examines the destination IP address in a packet and uses its routing table to determine where to forward it.

**What is a Routing Table?**

A routing table is a collection of information used by a router to determine the next destination for incoming packets.

It can contain:

- Destination network.
    
- Subnet mask or prefix length.
    
- Next-hop address.
    
- Outgoing interface.
    
- Route metric.
    

**Practical Example:**

Imagine you are using your home Wi-Fi to access a website hosted in another country.

1. Your computer creates a packet containing the destination IP address.
    
2. The packet is sent to your home router.
    
3. Your router checks its routing information.
    
4. The packet is forwarded toward the next network.
    
5. Other routers continue forwarding the packet.
    
6. Eventually, the packet reaches the destination network.
    

The packet may travel through several routers before reaching its destination.

**What is the Difference Between Routing and Switching?**

- **Routing:** Transfers packets between different networks using IP addresses.
    
- **Switching:** Transfers frames within a local network using MAC addresses.
    

**Main Responsibility:** Logical addressing and routing packets between networks.

---

## 2 – Data Link Layer

We have a second type of addressing, known as physical addressing, which takes place at the data link layer using MAC (Media Access Control) addresses.

The data link layer receives data packets from the network layer and adds the MAC addresses of the sender and the receiver to form a "frame"—the unit of data at the data link layer. This process, performed by the device sending the data, is called "frame encapsulation." Once the receiving device gets the frame and reads the MAC addresses, it performs "frame decapsulation."

### MAC Address

A MAC address is a physical address assigned to a network interface card by its manufacturer. It consists of hexadecimal digits (numbers and letters) for example, 11-S0-G0-78-M8-88 where each digit represents four bits, making a MAC address 48 bits long in total.


The data link layer is responsible for transferring data between devices on the same local network or directly connected network link.

It organizes information into units called **Frames**.

It also helps identify devices on a local network through MAC addresses.

The data link layer has two main sublayers:

**1. LLC (Logical Link Control)**

The Logical Link Control sublayer helps identify and manage communication with the network layer.

**2. MAC (Media Access Control)**

The Media Access Control sublayer is responsible for controlling access to the transmission medium and handling MAC addressing.

### A – MAC Address Structure

A standard MAC address is typically 48 bits long (6 bytes).

Each hexadecimal digit represents 4 bits.

Therefore:

- 1 hexadecimal digit = 4 bits.
    
- 2 hexadecimal digits = 8 bits (1 byte).
    
- 6 bytes = 48 bits.
    
- 12 hexadecimal digits = 48 bits.
    

A valid example of a MAC address is:

`00:1A:2B:3C:4D:5E`

MAC addresses are commonly written using hexadecimal digits from 0–9 and A–F.

**Technical Note:** The example `11-S0-G0-78-M8-88` in the original explanation is not a valid hexadecimal MAC address because characters such as S, G, and M are not hexadecimal digits. A valid example is provided above.

### B – Frame Structure

A typical Ethernet frame contains:

1. Destination MAC Address.
    
2. Source MAC Address.
    
3. Type/Length Field.
    
4. Data (Payload).
    
5. Frame Check Sequence (FCS).
    

**What is FCS?**

Frame Check Sequence is used for error detection.

The receiving device calculates and checks the frame's CRC (Cyclic Redundancy Check) value to determine whether the frame was corrupted during transmission.

If an Ethernet frame fails the integrity check, it is normally discarded.

### C – Encapsulation and Decapsulation

**Frame Encapsulation:**

When the sending device receives a packet from the network layer, the data link layer adds a header and trailer to create a frame.

The header contains information such as source and destination MAC addresses.

The trailer contains error-detection information.

**Frame Decapsulation:**

When the receiving device gets the frame, the data link layer examines its header and trailer, checks the frame, and extracts the packet to pass to the network layer.

### D – Switches and MAC Address Tables

A network switch mainly operates at the data link layer.

It learns the source MAC addresses of incoming frames and associates them with the ports on which they were received.

This information is stored in a MAC address table.

When a frame arrives, the switch checks the destination MAC address and determines which port should receive the frame.

For example:

- Computer A sends a frame to Computer B.
    
- The switch reads the source MAC address.
    
- It learns which port Computer A is connected to.
    
- It checks the destination MAC address.
    
- It forwards the frame to the appropriate port if the destination is known.
    

**Main Responsibility:** Physical addressing, framing, local network communication, and error detection.

---

## 1 – Physical Layer

Data is broken down into segments at the transport layer. It then reaches the network layer, where the source and destination IP addresses are added, forming what is known as a packet. Next, at the data link layer, the source and destination MAC addresses are added, creating a frame—a collection of bits (zeros and ones). As data passes through all these layers, it eventually reaches the physical layer in the form of bits. At this stage, the physical layer converts these bits into signals so they can be handled by the transmission medium, as no transmission medium can directly interpret the zeros and ones understood by the device.

These signals can be converted into electrical signals—in the case of copper cables, such as an Ethernet connection—or into optical signals when using fiber-optic cables, or even into radio signals in the case of wireless media.


The physical layer is the lowest layer of the OSI model.

It is responsible for transmitting raw bits (0s and 1s) through a physical transmission medium.

Unlike the higher layers, the physical layer does not understand IP addresses, MAC addresses, or port numbers. Its main responsibility is to transmit and receive signals.

### A – Types of Transmission Media

There are three main types of transmission media:

**1. Copper Cables (Electrical Signals)**

Copper cables transmit data using electrical signals.

Examples:

- Ethernet UTP cables.
    
- STP cables.
    
- Coaxial cables.
    

Ethernet cables are commonly used to connect computers, routers, and switches in local networks.

**2. Fiber-Optic Cables (Optical Signals)**

Fiber-optic cables transmit information using light signals.

They are made of very thin strands of glass or plastic.

Advantages:

- Very high transmission speeds.
    
- Suitable for long distances.
    
- Resistant to electromagnetic interference.
    
- High bandwidth capacity.
    

**3. Wireless Media (Radio Signals)**

Wireless communication transmits data through electromagnetic waves without requiring a physical cable.

Examples:

- Wi-Fi.
    
- Bluetooth.
    
- Cellular networks.
    

### B – Physical Layer Devices

Some devices and equipment operate primarily at the physical layer.

Examples:

- Hubs.
    
- Repeaters.
    
- Physical network cables.
    
- Connectors.
    
- Transceivers.
    

A hub receives signals from one port and repeats them to other ports without examining MAC addresses.

A repeater regenerates or reshapes signals to help extend transmission distance.

### C – Data Transmission Characteristics

The physical layer also defines several important characteristics:

- **Bit Rate:** The number of bits transmitted per second.
    
- **Transmission Mode:** How information is transmitted through the medium.
    
- **Connectors:** The physical interfaces used to connect devices.
    
- **Signal Encoding:** How bits are represented through signals.
    
- **Physical Topology:** How devices and cables are physically arranged.
    

### D – What Happens When Data Reaches the Physical Layer?

Consider the following process:

1. The transport layer divides the data into segments.
    
2. The network layer adds source and destination IP addresses, creating packets.
    
3. The data link layer adds source and destination MAC addresses, creating frames.
    
4. The physical layer converts the frames into a stream of bits.
    
5. The bits are transmitted through electrical, optical, or radio signals.
    

At the receiving device, the physical layer receives the signals and converts them back into bits.

The data then moves upward through the OSI layers until it reaches the receiving application.

**Main Responsibility:** Transmitting and receiving raw bits through the physical transmission medium.

---

# Complete OSI Data Encapsulation and Decapsulation

Now that we understand the seven layers individually, we need to understand how they work together when two devices communicate.

This process is known as **Encapsulation and Decapsulation**.

## 1. Encapsulation (Sending Device)

Encapsulation occurs when data moves from the application layer down to the physical layer.

Each layer adds its own information to the data before passing it to the next layer.

The process is:

1. Application Layer: Creates the data.
    
2. Presentation Layer: Formats, compresses, or encrypts the data.
    
3. Session Layer: Manages the communication session.
    
4. Transport Layer: Divides the data into segments (TCP) or datagrams (UDP).
    
5. Network Layer: Adds source and destination IP addresses, creating packets.
    
6. Data Link Layer: Adds MAC addresses and other frame information, creating frames.
    
7. Physical Layer: Converts the frames into bits and transmits them as signals.
    

## 2. Decapsulation (Receiving Device)

Decapsulation is the reverse process.

When the receiving device receives the signals, the information moves upward through the seven layers.

The process is:

1. Physical Layer: Receives signals and converts them into bits.
    
2. Data Link Layer: Examines the frame and extracts the packet.
    
3. Network Layer: Examines the IP information and extracts the transport-layer data.
    
4. Transport Layer: Processes the TCP segments or UDP datagrams and delivers data to the appropriate application.
    
5. Session Layer: Manages the communication session.
    
6. Presentation Layer: Handles the appropriate data representation, decompression, and decryption where applicable.
    
7. Application Layer: Delivers the information to the receiving application.
    
![[Pasted image 20261119140632.png]]
---

# Protocol Data Units (PDU)

Each OSI layer uses a specific name for the data it processes. These names are known as Protocol Data Units (PDUs).

|OSI Layer|PDU|
|---|---|
|Application Layer|Data|
|Presentation Layer|Data|
|Session Layer|Data|
|Transport Layer|Segment (TCP) / Datagram (UDP)|
|Network Layer|Packet|
|Data Link Layer|Frame|
|Physical Layer|Bits|

**Remember these terms:**

- Data: Information being communicated.
    
- Segment: Transport-layer data unit for TCP.
    
- Datagram: Transport-layer data unit for UDP.
    
- Packet: Network-layer data unit.
    
- Frame: Data link-layer data unit.
    
- Bits: Binary values (0s and 1s).
    

---

# Important Differences Between OSI Layers

|Layer|Main Addressing / Function|Data Unit|
|---|---|---|
|Application|Network services and protocols|Data|
|Presentation|Translation, compression, encryption|Data|
|Session|Session management|Data|
|Transport|Port numbers and end-to-end delivery|Segment / Datagram|
|Network|IP addressing and routing|Packet|
|Data Link|MAC addressing and framing|Frame|
|Physical|Signals and physical transmission|Bits|

## OSI Model Mnemonic

A useful way to remember the seven layers in order from Layer 7 to Layer 1:

**All People Seem To Need Data Processing**

- All = Application
    
- People = Presentation
    
- Seem = Session
    
- To = Transport
    
- Need = Network
    
- Data = Data Link
    
- Processing = Physical
    

---

# Final Summary

The OSI model explains how data travels from one device to another through seven different layers.

Each layer has a specific responsibility:

- **Layer 7 – Application:** Provides network services and protocols to applications.
    
- **Layer 6 – Presentation:** Handles data translation, compression, and encryption.
    
- **Layer 5 – Session:** Establishes, manages, and terminates communication sessions.
    
- **Layer 4 – Transport:** Provides end-to-end communication, segmentation, port addressing, and transport reliability.
    
- **Layer 3 – Network:** Handles IP addressing and routing between networks.
    
- **Layer 2 – Data Link:** Handles MAC addressing, framing, and communication over a local network link.
    
- **Layer 1 – Physical:** Transmits raw bits through electrical, optical, or radio signals.
    

**The most important concept to understand is that the seven layers work together. No single layer performs the entire communication process. Each layer contributes a specific function to ensure that data can travel from the sender to the receiver.**
