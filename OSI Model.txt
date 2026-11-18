The OSI model(Open Systems Interconnection) is a seven-layer framework that stipulates that any device wishing to communicate over a network must pass through these seven layers. The transmitting device must go through seven stages, and the receiving device must also go through the same seven stages, but in reverse.
![[osi-model-layers-explanation.webp]]
7-Application Layer
The application layer determines the appropriate protocol for the action you are performing and provides that protocol. For example, when you open your browser and enter a URL—such as "google.com"—the "https" protocol is automatically added; this is the protocol used for web browsing.

And when you want to download a file, it uses the FTP protocol, which stands for File Transfer Protocol.

The same applies if you want to send an email; this uses the SMTP (Simple Mail Transfer Protocol) protocol. There are also many other protocols that operate at the application layer.

6-Presentation layer
The presentation layer takes data arriving from the application layer—in the form of characters and numbers—and converts it into binary (zeros and ones) so that the device can understand and process it; this process is called translation. Subsequently, it reduces the number of these binary digits—a process known as data compression—which facilitates the transmission process.

This is what we observe when we upload an image to Facebook or WhatsApp: its file size decreases due to what is known as data compression.

The presentation layer also encrypts data before transmission; upon receipt, the receiving device decrypts it using the SSL(Secure Sockets Layer) protocol. 

5-Session layer
The session layer performs four functions

A-Transmission mode
Here the transmission mode is specified whether it is :
-simplex Mode
-half duplex 
-full-duplex

B-Authentication
When we want to access any server, the server typically asks for information—such as an username and password—to identify who you are.

C-Authorization
After entering your username and password and accessing the server, the authorization process takes place. This is the process by which the server determines whether or not you have permission to access a specific file—in other words, it defines your access rights on the server.

D-Session Management
One of the key functions of the session layer is session management. For instance, when you access Facebook while offline, you can still see the images and posts that were present during your last online session. This is because the session layer captures the data that was temporarily displayed on the site and stores it; when you access Facebook again, it retrieves this stored data, allowing you to view it even without an internet connection.

4-Transport Layer
This layer is responsible for 

A-data transmission. It performs a crucial function known as "segmentation": it takes data from the session layer and breaks it down into smaller units called "segments" to facilitate the transmission process. We can observe this in practice when a file download encounters an issue; if we restart the download, it does not begin from scratch—instead, it resumes from the specific segment where the corruption occurred.

Each of these segments contains a port number to identify the application it belongs to, as well as a sequence number to maintain the correct order of the segments, ensuring they arrive in the proper sequence at the receiving device after the reassembly process (de-segmentation).

B-Flow Control
It means that it controls the amount of data being transferred; for example, if you want to send data from a computer to a mobile phone, the computer might send 100 megabytes per second, while the mobile phone can only receive 10 megabytes per second.

For example, if we transmit data at a rate of 100 MB—which exceeds the rate the mobile device can handle—the device will send feedback to the computer to reduce the speed to 10 MB, thereby preventing data loss. Conversely, if the computer is transmitting at 5 MB, the mobile device will send feedback to the computer to increase the rate to 10 MB, ensuring optimal performance.

C-Determine Protocol
Here, we specify the type of protocol to be used for data transmission; there are two types of protocols, which are:

-TCP
It is a connection-oriented transmission, which is highly precise in data delivery; for instance, it sends a specific segment to the receiver, waits for the receiver to confirm that the segment arrived intact, and only after receiving that confirmation does it send the next segment.

For example, if you want to send an important email, speed is not the priority; rather, the accurate and intact delivery of the data is what matters—which is why we use the TCP protocol.

-UDP
Connectionless transmission: This protocol is not highly precise in its data delivery, but it is extremely fast. It simply identifies that a device needs to receive data and proceeds to send it.

For example, when we are on a live stream (like Zoom Live), we need the data to arrive in real time, but high precision is not essential; in this case, we use the UDP protocol.

3-Network Layer
The network layer does two things:

A-Logical Addressing
Every device on a network has a unique IP address, which can be used to communicate with it. For example, when you send something by mail, you need to know the recipient's address to ensure that what you send reaches the correct destination.

The network layer receives data segments from the transport layer, adds the sender's and receiver's IP addresses to them, and forms a packet called data unit for the network layer.

Thus, the packet consists of the sender's IP address, the receiver's IP address, and the data segment.

B-Routing
The second function performed by the network layer is routing; in short, routing is the process of selecting the best path for data to travel from the sender to the receiver.

2-Data Link Layer
We have a second type of addressing, known as physical addressing, which takes place at the data link layer using MAC (Media Access Control)addresses.

The data link layer receives data packets from the network layer and adds the MAC addresses of the sender and the receiver to form a "frame"—the unit of data at the data link layer. This process, performed by the device sending the data, is called "frame encapsulation." Once the receiving device gets the frame and reads the MAC addresses, it performs "frame decapsulation."

-MAC Address
A MAC address is a physical address assigned to a network interface card by its manufacturer. It consists of hexadecimal digits (numbers and letters) for example, 11-S0-G0-78-M8-88 where each digit represents four bits, making a MAC address 48 bits long in total.


1-Physical Layer
Data is broken down into segments at the transport layer. It then reaches the network layer, where the source and destination IP addresses are added, forming what is known as a packet. Next, at the data link layer, the source and destination MAC addresses are added, creating a frame—a collection of bits (zeros and ones). As data passes through all these layers, it eventually reaches the physical layer in the form of bits. At this stage, the physical layer converts these bits into signals so they can be handled by the transmission medium, as no transmission medium can directly interpret the zeros and ones understood by the device.

These signals can be converted into electrical signals—in the case of copper cables, such as an Ethernet connection—or into optical signals when using fiber-optic cables, or even into radio signals in the case of wireless media.![[osi_model_samir_to_medhat.png]]
