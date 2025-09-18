
# What is CIA Triad?

The CIA Triad which stands for Confidentiality, Integrity, and Availability is a foundational model in information security. It serves as a guiding framework for policies and practices that aim to protect critical information and ensure the reliability of systems within an organization.

The triad’s three core principles are

**Confidentiality:** Ensures that sensitive data is accessible only to authorized users and protected from unauthorized access.
**Integrity:** Maintains the accuracy and trustworthiness of data, ensuring it hasn’t been tampered with or altered by unauthorized individuals.
**Availability:** Guarantees that data and systems are accessible when needed by authorized users, minimizing downtime or disruptions.
\assets\Pasted image 20250917181028.png
![[Pasted image 20250917181028.png]]

## Confidentiality
Confidentiality ensures that sensitive information is accessible only to authorized individuals or systems and prevents unauthorized access. The goal is to protect private data from being viewed, accessed, or used by unauthorized persons.

### Risks to Confidentiality

- **Unauthorized Access:** This occurs when an unauthorized individual gains access to sensitive data, either by bypassing security measures or exploiting weaknesses.
- **Weak Encryption:** Description: If encryption standards are not robust enough, encrypted data may be easily decrypted by attackers.
- **Insider Threats:** Description: Employees or other trusted individuals within the organization intentionally or unintentionally leak sensitive information.

### How to ensure Confidentiality?
- **Encryption:** Use encryption techniques (e.g., AES, DES) to protect data. Even if attackers intercept the data, they won't be able to decrypt it.
- **VPN:** A Virtual Private Network (VPN) ensures secure data transmission over the network by creating a protected tunnel.

![[Pasted image 20250917181241.png]]

## Integrity 
Integrity ensures that data remains unaltered during transmission or storage. If the data is modified in any way, its integrity is compromised. When data is corrupted, it means the integrity is lost, leading to potential errors or malicious changes.

### Risks to Integrity 
- **Data Tampering:** Attackers or unauthorized users may intentionally alter, corrupt, or destroy data to manipulate information for malicious purposes or personal gain.
- **Malware and Ransomware:** Malicious software can infect systems, altering or encrypting data, and rendering it unusable until a ransom is paid or it is repaired.

### How is Integrity Ensured?
To check if our data has been modified or not, we make use of a hash function. 

**Common Hash Functions:**
- *MD5:* A 128-bit hash function.
- *SHA:* A family of hash functions, with SHA-1 being a 160-bit hash. Other versions include SHA-0, SHA-2, and SHA-3.

**How Hash Functions Work**
- **Host A Sends Data:** Suppose Host 'A' wants to send data to Host 'B'. To maintain integrity, Host 'A' generates a hash value (H1) by running a hash function over the data.
- Attaching the Hash: The generated hash value (H1) is attached to the data before transmission.
- **Host B Verifies Integrity:** When Host 'B' receives the data, it runs the same hash function over the received data to generate a new hash value (H2).
- **Comparison:** If the two hash values, H1 and H2, are equal (H1 = H2), this confirms that the data has not been modified, and its integrity has been maintained.

![[Pasted image 20250917181459.png]]

Note: Even a small change in the input (like altering a single word or character) will completely change the resulting hash."

## Availability 

Availability ensures that the network, systems, and data are accessible and operational for users when needed. A network that is unavailable can disrupt business operations, causing significant issues for companies and users relying on it.

### Risks to Availability
- **DoS and DDoS Attacks:** Denial of Service (DoS) or Distributed Denial of Service (DDoS) attacks can overwhelm network resources, making the network unavailable to legitimate users.
- **Impact:** These attacks can severely disrupt services, causing downtime and losses for companies.

### How to Ensure Availability
To ensure availability, the network administrator should keep a check on the following factors:

- **Hardware Maintenance:** Network administrators need to regularly maintain and upgrade hardware to prevent failures and ensure smooth operation.
- **Regular Upgrades:** Keeping systems and software updated helps in maintaining performance and security.
- **Failover Plan:** A failover system ensures that if one component fails, another can take over, minimizing downtime.
- **Preventing Bottlenecks:** Network congestion or bottlenecks should be prevented to ensure consistent performance and prevent slowdowns.

![[Pasted image 20250917181644.png]]

---

# Domain Name System (DNS)

DNS is a hierarchical and distributed naming system that translates domain names into IP addresses. When you type a domain name like www.geeksforgeeks.org into your browser, DNS ensures that the request reaches the correct server by resolving the domain to its corresponding IP address.

Without DNS, we’d have to remember the numerical IP address of every website we want to visit, which is highly impractical.

## How Does DNS Work?
The DNS process can be broken down into several steps, ensuring that users can access websites by simply typing a domain name into their browser.

![[Pasted image 20250917192228.png]]
![[Pasted image 20250917192235.png]]
![[Pasted image 20250917192244.png]]
![[Pasted image 20250917192253.png]]
![[Pasted image 20250917192300.png]]

1. **User Input:** You enter a website address (for example, www.geeksforgeeks.org) into your web browser.
2. **Local Cache Check:** Your browser first checks its local cache to see if it has recently looked up the domain. If it finds the corresponding IP address, it uses that directly without querying external servers.
3. **DNS Resolver Query:** If the IP address isn’t in the local cache, your computer sends a request to a DNS resolver. The resolver is typically provided by your Internet Service Provider (ISP) or your network settings.
4. **Root DNS Server:** The resolver sends the request to a root DNS server. The root server doesn’t know the exact IP address for www.geeksforgeeks.org but knows which Top-Level Domain (TLD) server to query based on the domain’s extension (e.g., .org).
5. **TLD Server:** The TLD server for .org directs the resolver to the authoritative DNS server for geeksforgeeks.org.
6. **Authoritative DNS Server:** This server holds the actual DNS records for geeksforgeeks.org, including the IP address of the website’s server. It sends this IP address back to the resolver.
7. **Final Response:** The DNS resolver sends the IP address to your computer, allowing it to connect to the website’s server and load the page.

*Note:* This entire process happens in milliseconds, enabling a fast and efficient browsing experience.

## Structure of DNS
DNS operates through a hierarchical structure, ensuring scalability and reliability across the global internet infrastructure. Here's how it’s organized:

- **Root DNS Servers:** These are the highest-level DNS servers and know where to find the TLD servers. They are crucial for directing DNS queries to the correct locations.
- **TLD Servers:** These servers manage domain extensions like .com, .org, .net, .edu, .gov and others. They help route queries to the authoritative DNS servers for specific domains.
- **Authoritative DNS Servers:** These are the servers that store the actual DNS records for domain names. They are responsible for providing the correct IP addresses that allow users to reach websites.
![[Pasted image 20250917192539.png]]
This hierarchical approach allows DNS to handle billions of queries every day, ensuring the stability and scalability of the internet.

## Types of Domains
DNS helps manage a wide variety of domain types to organize the vast number of websites on the internet. Here are the primary categories:

- **Generic Domains:** These include top-level domains like .com, .org, .net and .edu. These are widely used and recognized across the world.
- **Country Code Domains:** These domains represent specific countries or regions, such as .in for India, .us for the United States, .uk for the United Kingdom and .jp for Japan.
- **Inverse Domains:** Used for reverse DNS lookups, these domains help map IP addresses back to domain names. Reverse DNS lookups are useful for diagnostics and security purposes, ensuring that the source of network traffic is legitimate. So DNS can provide both the mapping for example to find the IP addresses of geeksforgeeks.org then we have to type
![[Pasted image 20250917192655.png]]

Understanding these categories is essential for managing domains effectively and recognizing the purpose behind different types of domains.

## Domain Name Server
The client machine sends a request to the local name server, which, if the root does not find the address in its database, sends a request to the root name server, which in turn, will route the query to a top-level domain (TLD) or authoritative name server. The root name server can also contain some hostName to IP address mappings. The Top-level domain (TLD) server always knows who the authoritative name server is. So finally the IP address is returned to the local name server which in turn returns the IP address to the host.

## DNS Lookup
DNS Lookup, also called DNS Resolution, is the process of translating a human-readable domain name (like www.example.com) into its corresponding IP address (like 192.0.2.1), which computers use to locate and communicate with each other on the internet. It allows users to access websites easily using names instead of remembering numeric IP addresses.

- DNS Lookup starts when a user types a domain name into their browser.
- The query goes through a series of servers: the DNS resolver, Root server, TLD server and authoritative server.
- Each server plays a role in finding the correct IP address for the domain.
- Once the IP address is found, the browser connects to the website’s server and loads the page.

## DNS Resolver
DNS Resolver is simply called a DNS Client and has the functionality for initiating the process of DNS Lookup which is also called DNS Resolution. By using the DNS Resolver, applications can easily access different websites and services present on the Internet by using domain names that are very much friendly to the user and that also resolves the problem of remembering IP Address.

**Types of DNS Queries**
There are basically three types of DNS Queries that occur in DNS Lookup. These are stated below.

![[Pasted image 20250917192816.png]]

- **Recursive Query:** In this query, if the resolver is unable to find the record, in that case, DNS client wants the DNS Server will respond to the client in any way like with the requested source record or an error message.
- **Iterative Query:** Iterative Query is the query in which DNS Client wants the best answer possible from the DNS Server.
- **Non-Recursive Query:** Non-Recursive Query is the query that occurs when a DNS Resolver queries a DNS Server for some record that has access to it because of the record that exists in its cache.

## DNS Caching and TTL (Time-to-Live)
DNS caching is a mechanism that stores DNS records locally to avoid querying external DNS servers repeatedly for the same information. This speeds up the browsing experience and reduces network traffic.

TTL (Time-to-Live) is the amount of time that a DNS record is cached before it expires. When the TTL expires, the cache is cleared and a fresh DNS query must be made. The TTL is defined by the authoritative DNS server, which can adjust this based on the nature of the domain.

**For example,** if the TTL for www.geeksforgeeks.org is set to 3600 seconds (1 hour), then the DNS record will be stored in the cache for one hour before it expires and requires a new lookup.

By understanding how DNS caching and TTL work, students can learn how to optimize website performance and troubleshoot issues related to stale or outdated DNS records.

## DNS Security and DNSSEC (DNS Security Extensions)
Although DNS is essential for smooth internet navigation, it can be vulnerable to security threats. One common risk is DNS cache poisoning, where malicious actors inject harmful DNS records into caches, redirecting users to fraudulent websites.

DNS Security Extensions (DNSSEC) is a protocol designed to address these security concerns. It adds cryptographic signatures to DNS records, allowing resolvers to verify the authenticity and integrity of DNS responses. DNSSEC ensures that the information a user receives from a DNS query has not been tampered with.

By understanding DNSSEC, students can help secure websites against DNS-based attacks, ensuring safe and authentic browsing experiences.

## Reverse DNS Lookup
Reverse DNS Lookup is the process of mapping an IP address back to its corresponding domain name. This is the opposite of the typical DNS lookup, where a domain name is resolved to an IP address. Reverse DNS is commonly used for:

![[Pasted image 20250917193158.png]]

- **Network Diagnostics:** System administrators use reverse DNS to determine the domain name associated with a specific IP address. This helps identify the source of network traffic.
- **Email Security:** Many email servers perform reverse DNS lookups to verify that incoming emails are coming from legitimate sources. This helps prevent spam and fraud.

A reverse DNS lookup is typically used in conjunction with standard DNS to ensure a complete and accurate mapping of network resources.


## DNS Record Types (A, CNAME, MX, TXT, etc.)
DNS records are essential for defining how domain names are used and how services are configured. Here are some of the most commonly used DNS record types:

- **A Record:** This record maps a domain name to an IPv4 address (e.g., geeksforgeeks.org to 185.199.109.153). This is the most common DNS record used to point a domain to its website's IP address.
- **CNAME Record:** The Canonical Name (CNAME) record allows you to alias one domain name to another. For example, www.geeksforgeeks.org can be an alias for geeksforgeeks.org.
- **MX Record:** The Mail Exchange (MX) record defines which mail servers are responsible for receiving emails for a domain. This is crucial for setting up email services.
- **TXT Record:** The Text (TXT) record stores text-based information. It is commonly used to verify domain ownership and to implement email security protocols like SPF (Sender Policy Framework) and DKIM (DomainKeys Identified Mail).

By understanding these record types, students can gain the knowledge needed to configure web and email services, troubleshoot issues and enhance their web development skills.

---

# Dynamic Host Configuration Protocol (DHCP)

Dynamic Host Configuration Protocol is a network protocol used to automate the process of assigning IP addresses and other network configuration parameters to devices (such as computers, smartphones and printers) on a network.

Instead of manually configuring each device with an IP address, DHCP allows devices to connect to a network and receive all necessary network information, like IP address, subnet mask, default gateway and DNS server addresses, automatically from a DHCP server.

## Components of DHCP
The main components of DHCP include:
![[Pasted image 20250917193856.png]]

- **DHCP Server:** DHCP Server is a server that holds IP Addresses and other information related to configuration.
- **DHCP Client:** It is a device that receives configuration information from the server. It can be a mobile, laptop, computer or any other electronic device that requires a connection.
- **DHCP Relay:** DHCP relays basically work as a communication channel between DHCP Client and Server.
- **IP Address Pool:** It is the pool or container of IP Addresses possessed by the DHCP Server. It has a range of addresses that can be allocated to devices.
- **Subnets:** Subnets are smaller portions of the IP network partitioned to keep networks under control.
- **Lease:** It is simply the time that how long the information received from the server is valid, in case of expiration of the lease, the tenant must have to re-assign the lease.
- **DNS Servers:** DHCP servers can also provide DNS (Domain Name System) server information to DHCP clients, allowing them to resolve domain names to IP addresses.
- **Default Gateway:** DHCP servers can also provide information about the default gateway, which is the device that packets are sent to when the destination is outside the local network.
- **Options:** DHCP servers can provide additional configuration options to clients, such as the subnet mask, domain name and time server information.
- **Renewal:** DHCP clients can request to renew their lease before it expires to ensure that they continue to have a valid IP address and configuration information.
- **Failover:** DHCP servers can be configured for failover, where two servers work together to provide redundancy and ensure that clients can always obtain an IP address and configuration information, even if one server goes down.
- **Dynamic Updates:** DHCP servers can also be configured to dynamically update DNS records with the IP address of DHCP clients, allowing for easier management of network resources.
- **Audit Logging:** DHCP servers can keep audit logs of all DHCP transactions, providing administrators with visibility into which devices are using which IP addresses and when leases are being assigned or renewed.

### DHCP Packet Format
Each field in the DHCP packet format plays a important role in enabling dynamic IP configuration, ensuring proper identification, addressing, timing, and communication between the client and server during the DHCP handshake process.
![[Pasted image 20250917194158.png]]

- **Hardware Length:** This is an 8-bit field defining the length of the physical address in bytes. e.g. for Ethernet the value is 6.
- **Hop count:** This is an 8-bit field defining the maximum number of hops the packet can travel.
- **Transaction ID:** This is a 4-byte field carrying an integer. The transaction identification is  set by the client and is used to match a reply with the request. The server returns the same value in its reply.
- **Number of Seconds:** This is a 16-bit field that indicates the number of seconds elapsed since the time the client started to boot.
- **Flag:** This is a 16-bit field in which only the leftmost bit is used and the rest of the bit should be set to 0. A leftmost bit specifies a forced broadcast reply from the server.
- **Client IP Address:** This is a 4-byte field that contains the client IP address . If the client does not have this information this field has a value of 0.
- **Your IP Address:** This is a 4-byte field that contains the client IP address. It is filled by the server at the request of the client.
- **Server IP Address:** This is a 4-byte field containing the server IP address. It is filled by the server in a reply message.
- **Gateway IP Address:** This is a 4-byte field containing the IP address of a routers. IT is filled by the server in a reply message.
- **Client Hardware Address:** This is the physical address of the client .Although the server can retrieve this address from the frame sent by the client it is more efficient if the address is supplied explicitly by the client in the request message.
- **Server** Name: This is a 64-byte field that is optionally filled by the server in a reply packet. It contains a null-terminated string consisting of the domain name of the server. If the server does not want to fill this filed with data, the server must fill it with all 0s.
- **Boot Filename:** This is a 128-byte field that can be optionally filled by the server in a reply packet. It contains a null- terminated string consisting of the full pathname of the boot file.
- **Options:** This is a 64-byte field with a dual purpose. IT can carry either additional information or some specific vendor information. The field is used only in a reply message.

## Working of DHCP
DHCP works on the Application layer of the UDP Protocol. The main task of DHCP is to dynamically assigns IP Addresses to the Clients and allocate information on TCP/IP configuration to Clients.
![[Pasted image 20250917194514.png]]

The DHCP port number for the server is 67 and for the client is 68. It is a client-server protocol that uses UDP services. An IP address is assigned from a pool of addresses. In DHCP, the client and the server exchange mainly 4 DHCP messages in order to make a connection, also called the DORA process, but there are 8 DHCP messages in the process.

### The 8 DHCP Messages
1. **DHCP Discover Message:** This is the first message generated in the communication process between the server and the client. This message is generated by the Client host in order to discover if there is any DHCP server/servers are present in a network or not. This message is broadcasted to all devices present in a network to find the DHCP server. This message is 342 or 576 bytes long.
![[Pasted image 20250917194615.png]]

As shown in the figure, the source MAC address (client PC) is 08002B2EAF2A, the destination MAC address(server) is FFFFFFFFFFFF, the source IP address is 0.0.0.0(because the PC has had no IP address till now) and the destination IP address is 255.255.255.255 (IP address used for broadcasting). As they discover message is broadcast to find out the DHCP server or servers in the network therefore broadcast IP address and MAC address is used.  

2. **DHCP Offers A Message:** The server will respond to the host in this message specifying the unleased IP address and other TCP configuration information. This message is broadcasted by the server. The size of the message is 342 bytes. If there is more than one DHCP server present in the network then the client host will accept the first DHCP OFFER message it receives. Also, a server ID is specified in the packet in order to identify the server.

![[Pasted image 20250917194713.png]]
Now, for the offer message, the source IP address is 172.16.32.12 (server's IP address in the example), the destination IP address is 255.255.255.255 (broadcast IP address), the source MAC address is 00AA00123456, the destination MAC address is 00:11:22:33:44:55 (client's MAC address). Here, the offer message is broadcast by the DHCP server therefore destination IP address is the broadcast IP address and destination MAC address is 00:11:22:33:44:55 (client's MAC address)and the source IP address is the server IP address and the MAC address is the server MAC address. 
Also, the server has provided the offered IP address 192.16.32.51 and a lease time of 72 hours(after this time the entry of the host will be erased from the server automatically). Also, the client identifier is the PC MAC address (08002B2EAF2A) for all the messages. 

3. **DHCP Request Message:** When a client receives an offer message, it responds by broadcasting a DHCP request message. The client will produce a  gratuitous ARP in order to find if there is any other host present in the network with the same IP address. If there is no reply from another host, then there is no host with the same TCP configuration in the network and the message is broadcasted to the server showing the acceptance of the IP address. A Client ID is also added to this message. 
![[Pasted image 20250917194726.png]]

Now, the request message is broadcast by the client PC therefore source IP address is 0.0.0.0(as the client has no IP right now) and destination IP address is 255.255.255.255 (the broadcast IP address) and the source MAC address is 08002B2EAF2A (PC MAC address) and destination MAC address is FFFFFFFFFFFF. 

*Note* - This message is broadcast after the ARP request broadcast by the PC to find out whether any other host is not using that offered IP. If there is no reply, then the client host broadcast the DHCP request message for the server showing the acceptance of the IP address and Other TCP/IP Configuration. 

4. **DHCP Acknowledgment Message:** In response to the request message received, the server will make an entry with a specified client ID and bind the IP address offered with lease time. Now, the client will have the IP address provided by the server. 

![[Pasted image 20250917194818.png]]
Now the server will make an entry of the client host with the offered IP address and lease time. This IP address will not be provided by the server to any other host. The destination MAC address is 00:11:22:33:44:55 (client's MAC address) and the destination IP address is 255.255.255.255 and the source IP address is 172.16.32.12 and the source MAC address is 00AA00123456 (server MAC address).  

5. **DHCP Negative Acknowledgment Message:** Whenever a DHCP server receives a request for an IP address that is invalid according to the scopes that are configured, it sends a DHCP NACK message to the client. E.g. when the server has no IP address unused or the pool is empty, then this message is sent by the server to the client. 

6. **DHCP Decline:** If the DHCP client determines the offered configuration parameters are different or invalid, it sends a DHCP decline message to the server. When there is a reply to the gratuitous ARP by any host to the client, the client sends a DHCP decline message to the server showing the offered IP address is already in use. 

7. **DHCP Release:** A DHCP client sends a DHCP release packet to the server to release the IP address and cancel any remaining lease time. 

8. **DHCP Inform:** If a client address has obtained an IP address manually then the client uses DHCP information to obtain other local configuration parameters, such as domain name. In reply to the DHCP inform message, the DHCP server generates a DHCP ack message with a local configuration suitable for the client without allocating a new IP address. This DHCP ack message is unicast to the client.  

### Security Measures for Using DHCP
To make sure your DHCP servers are safe, consider these DHCP security issues:

- **Limited IP Addresses :** A DHCP server can only offer a set number of IP addresses. This means attackers could flood the server with requests, causing essential devices to lose their connection.
- **Fake DHCP Servers :** Attackers might set up fake DHCP servers to give out fake IP addresses to devices on your network.
- **DNS Access :** When users get an IP address from DHCP, they also get DNS server details. This could potentially allow them to access more data than they should.

**Protection Against DHCP Starvation Attack**

A DHCP starvation attack happens when a hacker floods a DHCP server with requests for IP addresses. This overwhelms the server, making it unable to assign addresses to legitimate users. The hacker can then block access for authorized users and potentially set up a fake DHCP server to intercept and manipulate network traffic, which could lead to a man-in-the-middle attack.

***Advantages of DHCP***
- **Centralized Management of IP Addresses:** DHCP simplifies network administration by centralizing IP address allocation, ensuring efficient management.
- **Centralized and Automated TCP/IP Configuration:** DHCP automates the assignment of TCP/IP settings to devices, reducing manual configuration and errors.
- **Ease of Adding New Clients to a Network:** New devices are automatically assigned an IP and network configuration, simplifying network expansion.
- **Reuse of IP Addresses:** DHCP efficiently reuses IP addresses through its leasing system, minimizing the need for additional addresses.
- **Efficient Handling of IP Address Changes for Mobile Devices:** DHCP dynamically assigns IP addresses to portable devices that frequently move between networks, ensuring seamless connectivity.
- **Simple Reconfiguration of IP Address Space:** DHCP allows for easy reconfiguration of the IP address space on the server without requiring changes on individual clients.
- **Centralized Configuration Management:** DHCP provides a centralized approach to manage and configure network IP addresses, simplifying network administration.
- **Easy Handling of New Users and IP Address Reuse:** DHCP makes it easy to handle new users and efficiently reuse IP addresses, optimizing network resources.

***Disadvantages of DHCP***
- **IP Conflict Can Occur:** DHCP can sometimes cause IP conflicts when multiple devices are mistakenly assigned the same IP address.
- **Clients Accept Any Server:** Clients can connect to any DHCP server and if an unauthorized server is nearby, it may send invalid configuration data to the client.
- **Client Cannot Access the Network in Absence of a DHCP Server:** Without a DHCP server, clients will not be able to obtain an IP address and thus cannot access the network.
- **Machine Name Is Not Changed:** When a new IP address is assigned, the machine name does not automatically change, potentially causing identification issues on the network.


---
