When you open a website in your browser, the browser needs to communicate with a web server to retrieve the page and the required information. This is where HTTP and HTTPS come in.

## 1. HTTP?

It is a protocol used to transfer data and information between a user's browser and a website server. In simpler terms, it is a set of rules that defines how the browser requests information from the server and how the server responds to those requests. Let's say you want to visit the website: `http://aroundbyte.com.com`. What's happening?

1. You type the website address into your browser.
2. The browser sends an HTTP request to the website's server.
3. The server receives and processes the request.
4. The server sends an HTTP response containing the requested information.
5. The browser displays the website page to you.

       WEB BROWSER                                           WEB SERVER
   
       Browser                     ────────────►                Server         
                                  HTTP Request            
                                   ◄────────────          
                                    HTTP Response         
                                    HTML, CSS, JS         
                                      







   
**Important note:** HTTP does not encrypt data while it is in transmission, which means that the data can be readable if someone manages to intercept the connection.

## 2. HTTPS?

HTTPS stands for Hypertext Transfer Protocol Secure.

It's the secure version of HTTP and is also used to transfer data between a browser and a server, but it adds a layer of security using the TLS protocol.

In simpler terms: HTTPS performs the same function as HTTP, but it protects data during transmission between the browser and the server through encryption. When you visit a website like: `https://aroundbyte.com.com`, the following occurs:

1. The browser connects to the website server.
2. The browser and server negotiate a secure connection using TLS.
3. The website's digital certificate is verified.
4. Connection keys are generated to encrypt the data.
5. The browser and server begin exchanging requests and responses in encrypted form.

             TLS HANDSHAKE PROCESS
          Establishing a Secure Connection

       CLIENT (Browser)              SERVER (Website)
       ┌───────────────┐              ┌───────────────┐
       │               │              │               │
       │    BROWSER    │              │    SERVER     │
       │               │              │               │
       └───────┬───────┘              └───────┬───────┘
               │                              │
               │  1. CLIENT HELLO             │
               │  (Supported Versions &       │
               │   Cipher Suites)             │
               │ ────────────────────────────>│
               │                              │
               │  2. SERVER HELLO             │
               │     + SERVER CERTIFICATE     │
               │     (Public Key)             │
               │<────────────────────────────│
               │                              │
               │  3. CLIENT VERIFIES          │
               │     SERVER CERTIFICATE       │
               │     (Certificate Authority)  │
               │                              │
               │  4. KEY EXCHANGE             │
               │     (Establish Shared Secret)│
               │ ────────────────────────────>│
               │                              │
               │                              │
               │  5. BOTH GENERATE            │
               │     SESSION KEYS             │
               │                              │
               │  ┌────────────────────────┐  │
               │  │   SYMMETRIC KEY        │  │
               │  │      🔑 *******        │  │
               │  └────────────────────────┘  │
               │                              │
               │  6. SECURE CONNECTION        │
               │<═══════════════════════════>│
               │                              │
               │    ENCRYPTED DATA            │
               │    🔒 🔒 🔒 🔒 🔒             │
               │                              │
       ┌───────┴───────┐              ┌───────┴───────┐
       │    CLIENT     │              │    SERVER     │
       └───────────────┘              └───────────────┘


       ASYMMETRIC CRYPTOGRAPHY
                 │
                 ▼
       ESTABLISH SHARED SECRET
                 │
                 ▼
       SYMMETRIC ENCRYPTION
                 │
                 ▼
       FAST & SECURE COMMUNICATION

This helps to protect information such as passwords and login data as they travel across the network.

## The difference between HTTP and HTTPS

| Compare | HTTP | HTTPS |
|---|---|---|
| Encryption | does not provide encryption | it provides encryption using TLS. |
| Security | Less safe | safer |
| Data protection | Data is not encrypted during transmission | Data is encrypted during transmission. |
| Default port | 80 | 443 |
| Digital certificate | doesn't need it | TLS certificate used |

## What is TLS?

TLS stands for Transport Layer Security. It is a security protocol used to encrypt communication between devices and protect data as it travels across a network.

TLS offers three main benefits:

1. **Encryption:** Prevents others from reading data while it is in transit.
2. **Authentication:** Helps the browser verify the server's identity using a digital certificate.
3. **Integrity:** Helps detect any unauthorized modifications to data while it is in transit.


