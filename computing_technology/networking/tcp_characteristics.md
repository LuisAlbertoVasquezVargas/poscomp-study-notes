<!-- File: computing_technology/networking/tcp_characteristics.md -->

# TCP Protocol – Key Characteristics

The **Transmission Control Protocol (TCP)** is a core protocol of the Internet protocol suite, providing reliable, ordered, and error-checked delivery of data between applications.

---

## ✅ Key Characteristics of TCP

1. **Acknowledgement of Delivered Data**  
   * TCP is **connection-oriented** and confirms the receipt of data using **ACKs (acknowledgements)**.  
   * This ensures reliable delivery of all transmitted messages.

2. **In-Order Delivery**  
   * TCP delivers messages **in the order they were sent**.  
   * Uses **sequence numbers** to track data segments.  
   * Out-of-order segments are buffered and reordered before delivery to the application layer.

3. **Full-Duplex Communication**  
   * TCP supports **simultaneous sending and receiving** of data.  
   * Unlike half-duplex protocols, data can flow in both directions at the same time over a TCP connection.

4. **Congestion Control**  
   * TCP includes **mandatory congestion control mechanisms**.  
   * Adjusts the transmission rate according to network congestion to prevent packet loss and overload.

---

## ⚠️ Common Misconceptions

* TCP is **not half-duplex**; it is **full-duplex**.  
* TCP **always** implements congestion control—it is not optional.  
