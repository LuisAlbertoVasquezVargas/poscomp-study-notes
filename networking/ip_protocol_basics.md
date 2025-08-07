<!-- File: networking/ip_protocol_basics.md -->

# 🌐 IP Protocol Basics and Common Exam Pitfalls

The Internet Protocol (IP) is a fundamental protocol in network communications, often called the "glue of the Internet" because it enables different networks to interconnect and communicate.

---

## Key Characteristics of IP

- **Connectionless:** IP sends packets (datagrams) without establishing a connection beforehand.
- **Best-effort delivery:** IP does not guarantee delivery, ordering, or error-free transmission. Reliability is handled by higher-level protocols like TCP.
- **Addressing:** IP packets use destination IP addresses to identify the target host; port numbers are part of transport layer protocols (TCP/UDP), not IP.
- **Inter-networking:** IP provides a universal addressing scheme and routing to connect diverse network types (Ethernet, Wi-Fi, etc.).

---

## Common Misconceptions in Exam Questions

| Statement | Correctness & Explanation                                   |
|-----------|------------------------------------------------------------|
| IP is connection-oriented | Incorrect — IP is connectionless.                  |
| IP guarantees delivery    | Incorrect — IP is best-effort and does NOT guarantee delivery. |
| IP is "glue of the Internet" because it allows other protocols to replace it | Misleading — IP *is* called "glue" for connecting networks, but it is *not* replaceable by other protocols for internet-wide routing. |
| IP delivers multiple copies intentionally | Incorrect — duplicates may occur, but not intentionally. |
| IP datagram uses port numbers | Incorrect — ports are in TCP/UDP headers, not IP. |

---

## POSCOMP Tip

- When you see "IP is the glue of the Internet," think **universal addressing and routing across diverse networks**.
- Remember, **IP is connectionless and best-effort**, and reliability is handled at higher layers.
- Ports belong to transport protocols, not IP.

---
