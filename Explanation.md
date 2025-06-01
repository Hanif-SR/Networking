# Computer Network Overview

---

## Networking Fundamentals

### IP Addressing & Subnetting
Every device in a network requires an IP address to communicate. IP addresses are often grouped using **subnets**, which define how many devices can exist within a particular range. These are based on binary values and categorized into **classes** (A, B, C, etc.) depending on network size.

### Static vs. Dynamic IP
- **Static IP**: Manually configured and fixed.
- **Dynamic IP**: Assigned automatically, typically by a **DHCP server**.

### LAN & VLAN
- A **LAN (Local Area Network)** connects devices in a small physical area.
- A **VLAN (Virtual LAN)** can group devices logically, even if they’re not physically close.

### Network Devices
- **Router**: Directs data between networks.
- **Switch**: Connects devices within the same LAN.
- **Access Point**: Provides wireless network access.
- **Server**: Offers services like DHCP or file sharing.
- **Endpoint Devices**: PCs, laptops, and other user-side devices.

### IoT Devices
**Internet of Things (IoT)** devices (e.g., webcams, fans, lights) are typically lightweight, wirelessly connected, and can be remotely monitored or controlled.

---

## Network Topology Structure

The network is split into three segments, all connected through a central **router**:

### 1. Office LAN (Left)

![image](https://github.com/user-attachments/assets/30fb6356-b687-4c3a-b798-4c746a6a9182)

- 20 PCs connected to a **switch**.
- A **server** provides DHCP services for dynamic ip addressing (automatic ip addressing) for all 20 PCs.

### 2. Admin LAN (Center)

![image](https://github.com/user-attachments/assets/6b50d138-3965-44f9-b9ce-5fe0e456c8ce)

- 4 administrative PCs connected through a central **switch**.
- Possibly isolated via a VLAN for security or management.

### 3. IoT & Wireless LAN (Right)

![image](https://github.com/user-attachments/assets/f541ae10-28db-4355-aa87-22d85b95fbc9)

- IoT devices (Smartphone, Speaker, and AC) connected via an **Access Point**.
- Includes a **server**, **laptop**, and **PCs** to manage or monitor IoT operations.

---
## Configuration

This part will cover the documentation of every device's configuration.

### Setting-up Router


### Setting-up Switch

### Setting-up Server

### Setting-up Access Pointer

### Setting-up PC (Endpoint Devices)

### Setting-up IoT Devices
