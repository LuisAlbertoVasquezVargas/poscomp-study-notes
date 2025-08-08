<!-- File: networking/cidr_notation.md -->

# 🌐 CIDR Notation (Classless Inter-Domain Routing)

CIDR notation is a method for representing IP addresses and their associated network prefixes in a concise way, replacing the old class-based system.

---

## 🧩 What is CIDR?

- CIDR stands for **Classless Inter-Domain Routing**.
- It expresses an IP address followed by a slash (`/`) and a number indicating the length of the network prefix.
- Example: `192.168.1.0/24`

---

## 📏 Format

```

<IP address>/<prefix length>

```

- `<IP address>`: The base address (IPv4 or IPv6).
- `<prefix length>`: Number of bits used for the network part.
  - For IPv4, ranges from 0 to 32.
  - For IPv6, ranges from 0 to 128.

Example:  
`10.0.0.0/8` means the first 8 bits are network bits, remaining 24 bits for hosts.

---

## 🧮 Calculations with CIDR

- **Network Mask:**  
  The subnet mask derived from prefix length, e.g., `/24` → `255.255.255.0`.
  
- **Number of Hosts:**  
  Number of usable hosts in the subnet is:

```

2^(32 - prefix\_length) - 2

```

(Subtracting 2 for network and broadcast addresses.)

- **Network Address:**  
Obtained by zeroing out the host bits of the IP.

- **Broadcast Address:**  
Obtained by setting all host bits to 1.

---

## ⚖️ Advantages over Classful Addressing

- More flexible allocation of IP addresses.
- Reduces waste of IP addresses.
- Enables route aggregation, reducing size of routing tables.

---

## 📌 Summary

| CIDR Notation | Network Mask       | Number of Hosts      |
|---------------|--------------------|---------------------|
| /8            | 255.0.0.0          | 16,777,214          |
| /16           | 255.255.0.0        | 65,534              |
| /24           | 255.255.255.0      | 254                 |

---

