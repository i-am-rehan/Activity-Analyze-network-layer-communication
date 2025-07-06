## 📡 Analyze Network Layer Communication

### 📝 Overview
In this activity, I analyzed real-time network traffic using the `tcpdump` tool to investigate communication issues between a web browser and a DNS server. The goal was to identify which protocol was impacted and determine the root cause of a connectivity error.

### 🔍 Scenario
Several users reported being unable to access the website www.yummyrecipesforme.com. The browser returned the error: "destination port unreachable". As a cybersecurity analyst for an IT services provider, I was assigned to investigate the issue.

To troubleshoot, I attempted to visit the site myself and encountered the same error. I then used the network analysis tool tcpdump to inspect traffic during the failed connection attempt. The captured data revealed DNS queries made via UDP protocol were not reaching the DNS server, and error messages were returned using ICMP protocol.

📊 **Network Packet Log Sample**  
The following screenshot shows real-time packet capture during analysis:

![Packet Log Screenshot](./packet_log.png)

### 🔧 Tools & Techniques Used
- **tcpdump** – for packet capture and protocol analysis  
- **DNS & ICMP inspection** – to examine the flow of communication  
- **UDP Protocol analysis** – used by DNS queries  

### 🧠 What I Found
- The browser sent a **DNS request** using **UDP port 53** to resolve the domain.  
- The DNS server responded with **ICMP error messages** indicating:  
  > `udp port 53 unreachable`  
- This proved that **DNS service was unavailable** on the target server, likely due to misconfiguration or downtime.

### 💡 Key Skills Demonstrated
- Analyzing captured packet data using timestamps, IP headers, and protocol information  
- Interpreting ICMP error messages  
- Understanding how DNS and UDP work at the network layer  
- Applying troubleshooting methods for real-world incident investigation

### ✅ Outcome
I successfully identified the failing protocol (**DNS over UDP**) and the root cause (**ICMP response: port unreachable**).  
The results were compiled into a detailed [incident report](https://docs.google.com/document/d/1Banl9QIvzTQb2_rvVF8RKe6wn2cp84TT3Y4V3ksyB2Y/edit?usp=sharing) and submitted to the security engineering team for further action.
