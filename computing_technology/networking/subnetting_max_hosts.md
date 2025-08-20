<!-- File: computing_technology/networking/subnetting_max_hosts.md -->

# Subnetting – Maximum Number of Hosts

## 1. Understanding the Subnet Mask

A **subnet mask** is a 32-bit number that separates the **network portion** of an IP address from the **host portion**.

Example: **255.255.255.0**

### Binary Representation

* 255 = 11111111₂
* 0 = 00000000₂

So the subnet mask **255.255.255.0** in binary is:

11111111.11111111.11111111.00000000

* **1s** → network bits
* **0s** → host bits

### Host Bits

* The last octet (8 bits) is for hosts
* Number of host bits = **8**

## 2. Total Possible Addresses

The total number of IP addresses is determined by the number of host bits:

* Total addresses = 2^n, where n = number of host bits
* Total addresses = 2^8 = 256

This includes all possible addresses in the network.

## 3. Special Addresses

Two addresses are reserved in every subnet:

1. **Network Address** – all host bits are 0, identifies the network itself
2. **Broadcast Address** – all host bits are 1, used to send data to all devices

## 4. Usable Hosts

* Usable hosts = Total addresses – Reserved addresses
* Usable hosts = 256 – 2 = **254**

## 5. Conclusion

A network with a **255.255.255.0** subnet mask can support a **maximum of 254 computers**.

---
