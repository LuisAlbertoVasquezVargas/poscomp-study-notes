<!-- File: networking/dns_protocol.md -->

# 🌐 DNS Protocol

The **Domain Name System (DNS)** is a hierarchical, decentralized system used to resolve human-readable domain names into IP addresses.

---

## 📌 Role in the Internet

- DNS is a **critical application-layer protocol**.
- Converts hostnames like `www.example.com` into IP addresses such as `93.184.216.34`.
- Acts as the **“phonebook” of the Internet**.

---

## 📡 Transport Protocols Used

| Context                         | Protocol |
|--------------------------------|----------|
| Regular queries (e.g., A/AAAA) | **UDP**  |
| Zone transfers (AXFR, IXFR)    | TCP      |
| Responses > 512 bytes (legacy) | TCP      |
| DNS over HTTPS (DoH)           | HTTPS    |
| DNS over TLS (DoT)             | TCP+TLS  |

- **UDP is used for regular DNS queries** because it's faster and uses less overhead.
- **TCP is used**:
  - For zone transfers (server-to-server communication).
  - When the response is too large for a single UDP packet.
- Modern extensions like **EDNS0** allow larger UDP packets.

---

## ⚙️ Layer and Port

- **OSI Layer:** Application Layer
- **Transport Layer Protocols:** Primarily UDP, optionally TCP
- **Default Port:** `53`

---

## 🧠 Key Concepts

- **Recursive vs Iterative Queries**:
  - *Recursive:* DNS server queries others until it gets an answer.
  - *Iterative:* DNS server returns the best answer it has (or refers you to another server).
- **Caching**: DNS results are cached by resolvers and clients to improve performance.
- **TTL (Time To Live)**: Defines how long a DNS record is valid in cache.

---

## ✅ POSCOMP-style Notes

- The **DNS protocol** uses **UDP on port 53** for most regular queries.
- **TCP is used** for DNS when:
  - Transferring entire DNS zones (AXFR).
  - Responses exceed the UDP size limit.
- DNS operates at the **application layer**, not the transport layer.
- UDP is **connectionless** and **does not guarantee delivery**, which is acceptable for DNS due to its small payloads and low latency requirement.
- DNS can fall back to TCP if UDP fails.

---

## 🧪 Example POSCOMP Question

> **Which transport layer protocol does the DNS protocol use for regular queries?**
>
> A) ICMP  
> B) HTTP  
> C) TCP  
> D) FTP  
> E) **UDP** ✅

---
