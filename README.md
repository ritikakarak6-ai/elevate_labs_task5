# Cyber Security Internship - Task 5: Network Traffic Analysis Using Wireshark

## 📝 Objective
The objective of this task is to capture live network traffic using Wireshark, analyze basic network protocols, understand packet structures, and generate a brief analysis report.


-----------------------------------------------------------------------------------------------------------------------------


## 🛠️ Tools Used
* **Wireshark** (Open-source packet analyzer)
* **Command Prompt / Terminal** (for generating traffic via `ping`)
* **Web Browser** (for generating HTTP/DNS traffic)


-----------------------------------------------------------------------------------------------------------------------------



## 🚀 Step-by-Step Implementation

1. **Installation:** Installed Wireshark on the local system.
2. **Capture Initiation:** Opened Wireshark, selected the active network interface (e.g., Wi-Fi / Ethernet), and started the live packet capture.
3. **Traffic Generation:** 
   * Opened a web browser and visited a website.
   * Opened the terminal and executed a ping command: `ping google.com`.
4. **Stopping the Capture:** Stopped the packet capture after approximately 1-2 minutes of activity.
5. **Analysis & Filtering:** Applied display filters (`dns`, `http`, `tcp`, `icmp`) to isolate and inspect specific protocols.
6. **Export:** Saved the captured session as a `.pcap` file.



-----------------------------------------------------------------------------------------------------------------------------



## 📊 Protocols Identified & Analysis Report

During the analysis, the following key protocols were identified and inspected:

### 1. DNS (Domain Name System)
* **Purpose:** Translates human-readable domain names (e.g., google.com) into IP addresses.
* **Observation:** When the `ping google.com` command was executed, the system sent a standard DNS query packet to the DNS server, and received a DNS response containing the target IP address.

### 2. ICMP (Internet Control Message Protocol)
* **Purpose:** Used for network diagnostics and error reporting.
* **Observation:** After the DNS resolution, **Echo (ping) request** and **Echo (ping) reply** packets were captured, confirming network connectivity between the host and the server.

### 3. TCP (Transmission Control Protocol)
* **Purpose:** A connection-oriented protocol that ensures reliable data delivery.
* **Observation:** Multiple TCP packets were observed showing the **Three-Way Handshake** (`SYN` -> `SYN-ACK` -> `ACK`) process before any application data was transmitted.

### 4. HTTP / HTTPS (Hypertext Transfer Protocol / Secure)
* **Purpose:** Used for transmitting web pages across the internet.
* **Observation:** Application data packets were captured during web browsing. *(Note: HTTPS traffic appeared as encrypted TLS data packets to maintain privacy).*


---------------------------------------------------------


## 📄 Deliverables Included
* `network_capture.pcap` (The exported packet capture file)
* Screenshots of Wireshark interface showing filters applied (Optional: add your screenshots in an `images/` folder here).




-----------------------------------------------------------------------------------------------------------------------------




## 💬 Interview Questions & Answers

### Q1. What is Wireshark used for?
**Ans:** Wireshark is a free and open-source packet analyzer. It is used for network troubleshooting, analysis, software and communications protocol development, and cybersecurity auditing to inspect data passing through a network interface.

### Q2. What is a packet?
**Ans:** A packet is a small segment of a larger message sent over a network. Data sent over the internet is broken down into packets, which contain a payload (the actual data) and a header (control information like source and destination IP addresses).

### Q3. How to filter packets in Wireshark?
**Ans:** Packets can be filtered using the **Display Filter Bar** at the top of the Wireshark interface. You can filter by protocol name (e.g., `tcp`, `udp`, `dns`), by IP address (e.g., `ip.addr == 192.168.1.1`), or by port number (e.g., `tcp.port == 80`).

### Q4. What is the difference between TCP and UDP?
**Ans:**
* **TCP (Transmission Control Protocol):** Connection-oriented, reliable, guarantees delivery of packets in order, and uses a three-way handshake. Used in Web Browsing (HTTP), Email (SMTP).
* **UDP (User Datagram Protocol):** Connectionless, faster but unreliable, does not guarantee packet delivery or order. Used in Video Streaming, Gaming, and DNS.

### Q5. What is a DNS query packet?
**Ans:** A DNS query packet is a request sent by a client computer to a DNS server asking for the IP address corresponding to a domain name (e.g., asking "What is the IP address for google.com?"). It typically runs over UDP port 53.

### Q6. How can packet capture help in troubleshooting?
**Ans:** Packet capture allows network administrators to see exactly what is happening on the wire. It helps identify latency issues, packet loss, unauthorized network traffic, misconfigured protocols, or connection drops by analyzing the sequence and health of individual packets.

### Q7. What is a protocol?
**Ans:** A protocol is a standardized set of rules that determines how data is transmitted and received between different devices over a network. Examples include HTTP, TCP, IP, and FTP.

### Q8. Can Wireshark decrypt encrypted traffic?
**Ans:** Wireshark cannot decrypt encrypted traffic (like HTTPS/TLS) by default because the data is scrambled using cryptographic keys. However, if you provide Wireshark with the specific private keys or the SSL/TLS pre-master secret log file from the browser, it can decrypt and display the traffic.
