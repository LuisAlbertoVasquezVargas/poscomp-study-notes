<!-- File: networking/ip_routing.md -->

# 🌐 IP Routing and Network Matching

Routers forward IP packets based on the **destination IP address** by matching it against their routing table entries. Each entry consists of a network address and a subnet mask (CIDR notation).

---

## How Routing Decisions Are Made

- The router compares the destination IP with the network prefixes in its routing table.
- It selects the **most specific route** (longest prefix match) that contains the destination IP.
- If multiple matches exist, the route with the longest subnet mask (largest number after the slash) is preferred.

---

## Example Scenario

- **Destination IP:** 11.1.2.5
- **Routing Table Contains:**
  - 13.0.0.0/8
  - 13.1.0.0/16
  - **11.1.0.0/16**
  - 13.1.2.0/24
  - 11.1.2.0/24

---

## Matching the Destination

- The destination IP `11.1.2.5` falls within:
  - `11.1.0.0/16` (range 11.1.0.0 to 11.1.255.255)
  - `11.1.2.0/24` (range 11.1.2.0 to 11.1.2.255)

- If both `11.1.0.0/16` and `11.1.2.0/24` are present, the router chooses **`11.1.2.0/24`** due to longer prefix (more specific).

- If only `11.1.0.0/16` is in the routing table, the router forwards the packet to that route.

---

## POSCOMP Tip

- Always identify the **destination IP**.
- Compare with network entries using subnet masks.
- Pick the route with the **longest prefix match** containing the IP.

---
