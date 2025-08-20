<!-- File: computing_technology/networking/osi_model_data_link_sublayers.md -->

# ISO/OSI Model – Data Link Layer Sublayers

## 1. ISO/OSI Model Overview

* The **ISO/OSI model** is a conceptual framework for standardizing network functions.
* It has **7 layers**:

  1. Physical
  2. Data Link
  3. Network
  4. Transport
  5. Session
  6. Presentation
  7. Application

## 2. Data Link Layer

* Responsible for **node-to-node data transfer** and **error detection/correction**.
* Ensures reliable communication over a **physical link**.

### 2.1 Sublayers of the Data Link Layer

The data link layer is divided into **two sublayers**:

1. **Logical Link Control (LLC)**

   * Provides **interface to the network layer**.
   * Handles **error detection** and **flow control**.
   * Manages **logical addressing** and **frame synchronization**.

2. **Media Access Control (MAC)**

   * Responsible for **access control to the physical medium**.
   * Determines **how devices share the medium** (Ethernet, Wi-Fi, etc.).
   * Handles **frame delimitation** and **physical addressing** (MAC addresses).

### 2.2 Key Points

* LLC and MAC work together to ensure **reliable link-layer communication**.
* LLC focuses on **logic and control**, while MAC focuses on **physical access**.

---

