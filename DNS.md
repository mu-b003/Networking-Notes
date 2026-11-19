# Domain Name System (DNS)

## 1. What is DNS?

The **Domain Name System (DNS)** is a naming system that translates human-readable domain names into IP addresses that computers use to identify and communicate with one another.

For example, when you enter `google.com` in your browser, your device needs to find the IP address associated with that domain. DNS helps it find the address so the browser can connect to Google's server and request the website's content.

**Important:** DNS helps locate a server; it does not download the website itself. After the browser obtains an IP address, it connects to the web server and requests the page, images, videos, HTML, and other resources.

## 2. What is a DNS server?

A DNS server is a computer or service that stores, looks up, or provides DNS information. DNS servers work together to help devices find the IP addresses and other DNS records associated with domain names.

A DNS server is not necessarily the computer that hosts the website. The website's server and its DNS servers may be operated by different providers.

## 3. The main types of DNS servers

A typical DNS lookup can involve four main types of DNS servers:

### 1. DNS Resolver (Recursive Resolver)

A **DNS resolver** receives DNS queries from a device or application and works to find the requested DNS information.

It often checks its cache first. If it already has a valid answer, it can return that answer without contacting other DNS servers.

The resolver is commonly provided by an Internet Service Provider (ISP), but users can also use public DNS resolvers, such as Google Public DNS or Cloudflare DNS.

### 2. Root Name Server

A **root name server** is the first step in the DNS hierarchy when a resolver needs to look up a name and does not already have the answer.

Root servers do not normally provide the website's IP address. Instead, they direct the resolver to the appropriate **Top-Level Domain (TLD) name servers**.

There are **13 logical root-server identities**, named A through M. However, this does not mean there are only 13 physical machines: each identity is served by many instances distributed around the world, largely using a technology called **anycast**.

### 3. TLD Name Server

A **Top-Level Domain (TLD) name server** provides information about the next level of the DNS hierarchy.

A TLD is the final part of a domain name, such as:

- `.com`
- `.org`
- `.net`
- `.edu`

For example, when a resolver looks up `facebook.com`, the root server directs it to the name servers responsible for `.com`. The `.com` TLD server then directs the resolver to the authoritative name servers for `facebook.com`.

The TLD server does not normally provide the website's final IP address.

### 4. Authoritative Name Server

An **authoritative name server** holds the DNS records for a domain and provides authoritative answers for that domain.

For example, it may return the IP address associated with `facebook.com`, if an appropriate record exists.

Authoritative DNS servers provide DNS information; they do not normally decide whether a user is allowed to access a website. Website access permissions are generally handled by the website's server and application.

## 4. How does DNS work?

Let's use `facebook.com` as an example.

1. **You enter the domain name:** You type `facebook.com` into your browser.
2. **The device checks for an existing answer:** The browser and operating system may check their DNS caches. If a valid answer is already available, the lookup may finish without contacting an external resolver.
3. **The query reaches a DNS resolver:** If the device does not have the answer, it sends a DNS query to a recursive resolver, which may be provided by your ISP or another DNS service.
4. **The resolver checks its cache:** If it has a valid cached answer, it returns it to your device. Otherwise, it begins looking up the domain through the DNS hierarchy.
5. **The resolver contacts a root server:** The root server does not return the website's IP address. It refers the resolver to the name servers for the relevant TLD, such as `.com`.
6. **The resolver contacts the TLD server:** The `.com` TLD server refers the resolver to the authoritative name servers for `facebook.com`.
7. **The resolver contacts an authoritative name server:** The authoritative server returns the requested DNS record, such as an A record containing an IPv4 address or an AAAA record containing an IPv6 address.
8. **The resolver caches and returns the answer:** The resolver may cache the result for the period specified by its Time to Live (TTL), then sends the answer back to the device.
9. **The browser connects to the website:** The browser uses the returned IP address to connect to the web server and request the website's content.

The browser can then receive the page and its resources, such as HTML, CSS, JavaScript, images, and videos.

## 5. DNS cache and TTL

A **DNS cache** temporarily stores DNS lookup results so the same information does not need to be looked up from the beginning every time.

A **Time to Live (TTL)** value, measured in seconds, tells DNS caches how long a record may be kept before it should be refreshed.

Caching helps:
- Reduce lookup time.
- Reduce repeated DNS traffic.
- Reduce the work required from DNS servers.

A cached record may expire, after which the resolver can perform another lookup to obtain updated information.

## 6. Common DNS record types

DNS stores different types of records, each serving a particular purpose.

| Record | Purpose |
|---|---|
| **A** | Maps a domain name to an IPv4 address. |
| **AAAA** | Maps a domain name to an IPv6 address. |
| **CNAME** | Makes one domain name an alias of another domain name. |
| **MX** | Identifies mail servers that receive email for a domain. |
| **NS** | Identifies the authoritative name servers for a DNS zone. |
| **TXT** | Stores text information, often used for domain verification and email-security settings. |
| **PTR** | Used for reverse DNS lookups, mapping an IP address to a domain name. |

## 7. Which transport protocols and ports does DNS use?

Traditional DNS commonly uses:

- **UDP port 53:** Used for most ordinary DNS queries because it is efficient and has low overhead.
- **TCP port 53:** Also used by DNS, including for responses that require TCP and for some other DNS operations, such as zone transfers.

There are also encrypted DNS methods, including **DNS over HTTPS (DoH)** and **DNS over TLS (DoT)**, which protect DNS queries while they travel between a client and a resolver.

## 8. Important points 

- DNS stands for **Domain Name System**.
- DNS translates domain names into DNS records, commonly IP addresses.
- A recursive resolver performs the lookup on behalf of the device.
- Root servers refer resolvers to TLD servers.
- TLD servers refer resolvers to authoritative name servers.
- Authoritative name servers provide the DNS records for a domain.
- Caching and TTL help make DNS lookups faster and more efficient.
- DNS locates the server; the browser connects to that server to retrieve the website.

## 9. A simple DNS lookup flow

```text
User enters facebook.com
          |
          v
Browser / Operating System
          |
          v
DNS Resolver
          |
          | If the answer is not cached:
          v
Root Name Server
          |
          | Referral to .com name servers
          v
.com TLD Name Server
          |
          | Referral to facebook.com authoritative name servers
          v
Authoritative Name Server
          |
          | Returns the requested DNS record
          v
DNS Resolver
          |
          | Returns the answer to the device
          v
Browser connects to the web server
          |
          v
Website content is requested and loaded
```
