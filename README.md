# 📡 Wireshark Network Traffic Capture & Analysis

This project demonstrates real-time packet capture and analysis using Wireshark, a core tool in cybersecurity and network troubleshooting. The goal was to observe live HTTP and DNS traffic on a real network, analyze packet content, and apply protocol-specific filters to isolate and interpret web-based communication.

---

## 🛠 Tools Used

- **Wireshark** (open-source network analyzer)
- **Npcap** (for packet sniffing support)
- **Windows 10**
- **Browser: Chrome**
- **Command Prompt** (`ipconfig` for IP verification)

---

## 🎯 Project Objective

- Capture and inspect live network traffic on a home Wi-Fi network
- Apply filters to isolate HTTP, DNS, and ARP traffic
- Follow an HTTP stream between a client and a web server
- Use protocol hierarchy tools to summarize traffic distribution

---

## ✅ Actions Performed

- Selected the active **Wi-Fi interface** in Wireshark
- Located device IP using `ipconfig` → `10.0.0.211`
- Opened `supreme.com` in a browser to generate HTTP traffic
- Applied key Wireshark filters:
  - `http` — to isolate website traffic
  - `dns` — to observe domain resolution
  - `arp` — to identify local MAC address mapping
- Used **Follow HTTP Stream** to inspect end-to-end request/response content
- Ran **Protocol Hierarchy Statistics** to break down all captured protocols

---

## 🔍 Key Observations

| Feature | Details |
|--------|---------|
| **HTTP Response** | `HTTP/1.1 206 Partial Content` — partial delivery of a file (possibly media) |
| **Headers Noted** | `Content-Range`, `Connection: keep-alive`, `User-Agent` |
| **Common Protocols** | HTTP, TLSv1.2, TCP, DNS, ARP, mDNS, IGMPv3, ICMPv6 |
| **Wireshark Colors** | Blue = HTTP, Red = retransmissions, Black = TCP reset, Gray/Pink = multicast/local discovery |
| **TCP Flags** | Observed PSH and ACK indicating data transmission |
| **Followed Stream** | Revealed raw request/response data between client and server |
| **Notable IPs** | My device: `10.0.0.211`; Remote servers: `20.42.73.30`, `2600:1409:9800::`, `2601:601:907::`; Multicast: `224.0.0.251` |

---

## ⚠️ Technical Issues Encountered

| Problem | Resolution |
|--------|------------|
| HTTP stream showed status 206 | Investigated and found it was a partial content delivery from the server, often used for loading chunks of large assets like media or images |
| Red/black packets in capture | Analyzed further and confirmed they were TCP retransmissions and resets — common in brief connection interruptions or content retries |

---

## 🧠 Skills Demonstrated

- Live packet capture and interpretation
- Applying protocol filters in Wireshark
- Recognizing normal vs. error-level TCP behavior
- Following application-layer data using stream tracking
- Summarizing network traffic using protocol hierarchy tools
- Identifying internal vs. external network communication paths

---

## 📁 Files Included

- `capture.pcapng` — Wireshark packet capture file
- `README.md` — project overview and full analysis

---

## 🚀 Next Steps

- Capture and analyze encrypted HTTPS traffic (TLS handshake)
- Create filters to detect potential DNS tunneling or anomalies
- Export stream data for further offline analysis or parsing

---

## 📌 Why It Matters

This project demonstrates core technical skills in packet analysis, protocol investigation, and live traffic interpretation — essential for roles in cybersecurity, network engineering, and SOC operations.

---

