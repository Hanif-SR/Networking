# Computer Network Overview

![image](https://github.com/user-attachments/assets/02c91e0a-758f-4356-9b00-00fe380f9e85)

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
Using Router 2911, set the name into "Main Router"

![image](https://github.com/user-attachments/assets/72288203-82ab-46d9-aabb-cc7228fd0d9e)



### Setting-up Switch
Using Switch 2960-24TT, set up 3 switches with 3 subnet [`200.100.x.1`]

![image](https://github.com/user-attachments/assets/59f35742-3978-4ea8-a114-9184038c1b22)

Main Router          <-->    Switch 1 `200.100.1.1`

GigabitEthernet0/0   <-->    GigabitEthernet0/1

![image](https://github.com/user-attachments/assets/b5beac08-ee28-4f6a-95c4-54bee11c8587)

Main Router          <-->    Switch 2 `200.100.2.1`

GigabitEthernet0/1   <-->    GigabitEthernet0/1

![image](https://github.com/user-attachments/assets/4a5bef83-24d7-437f-8691-518ae112aca2)

Main Router          <-->    Switch 3 `200.100.3.1`

GigabitEthernet0/2   <-->    GigabitEthernet0/1

![image](https://github.com/user-attachments/assets/5fb0a16e-c769-44b2-8f42-b603389b1641)

Each switches use GigabitEthernet0/1 while the Main Router uses differet GigabitEthernet cable



### Setting-up Server
Use two server and assign the ip address statically with each own subnet, setting each server's ip address (static ip configuration)

server 1 [`200.100.1.2`]

server 2 [`200.100.2.2`]

![image](https://github.com/user-attachments/assets/bceaaf12-b946-41df-8c8e-5e33d966f18a)

Setting up DHCP service for both Servers;

![image](https://github.com/user-attachments/assets/48cbabcd-51d2-4286-8959-98b3b05e53fa)

Setting up IoT Service for Server 2;

![image](https://github.com/user-attachments/assets/c31bb7e9-4c57-4e14-b3c5-41b45f6fcde9)



### Setting-up Access Pointer
For using Access Pointer setting up the SSID is important for it will be used to connect with devices wirelessly, Open `Port 1` then set the SSID (`MainRoute` as the new SSID)

![image](https://github.com/user-attachments/assets/4f301629-1e78-46f8-a94a-1e808ba08fd7)

Pairing wireless device (such as smartphone) simply open the device's config then change the `SSID` = `Default` column into `MainRoute`

![image](https://github.com/user-attachments/assets/76d99e16-ef12-4e99-95d7-3b36c5fa3968)



### Setting-up PC (Endpoint Devices)

Setting up Endpoint devices such as PC can be done with both Static or Dynamic IP Configuration, before assign the ip address make sure the cable is connected if using direct connection, if using wireless connection then make sure to have wireless option such as laptop, tablet, or smartphone then change the SSID to connect into Access pointer like previous attempt.

![image](https://github.com/user-attachments/assets/88a68f95-93f6-4087-8eaa-a06dcff1bcf8)

Examples of Static and Dynamic IP Addressing/Configuration, taken from subnet [`200.100.1.0`] and [`200.100.3.0`], since subnet [`200.100.1.0`] uses DHCP service then it's Dynamic IP Configuration while [`200.100.3.0`] is only 4 devices thus using DHCP services will not be efficient that is why Static IP Configuration will be easier



### Setting-up IoT Devices

Setting IoT Devices in this case will need Server (IoT Service), Access Pointer (wireless connection), and Endpoint Devices (PC, Laptop, or smartphone)

![image](https://github.com/user-attachments/assets/61df2a63-1fa1-42f5-8ea3-7e4e1c616d4d)

-Setting the IoT Service in Server 2
-Setting Access pointer SSID for connection
-Setting the IoT Devices for example Air Conditioner (AC)
Connect the IoT Server into `Remote Server` then server address `200.100.2.2` which is the Server's IP address
make sure to create the IoT account by openning

![image](https://github.com/user-attachments/assets/66f63dc3-71e1-4d5f-8737-1c28d7f38b57)

then try login in with server's ip address and wait until it fails then sign up

![image](https://github.com/user-attachments/assets/f86e9c0e-81b5-4f8b-81ad-7cc9e492dd27)


Create the Username and Password [`admin`,`admin`] for simple account

![image](https://github.com/user-attachments/assets/6c0ae23c-693c-4e17-bb4c-ffae8764b9d7)


after the account is created then log in

![image](https://github.com/user-attachments/assets/2e5081d1-2142-4f4c-aaf1-64d4f89aef5a)

Monitoring IoT devices can be done within the same subnet of any Endpoint Devices



### Setting-up VLAN (Virtual Local Area Network)

Use Switch 3 configuration by openning config and VLAN Database, add VLAN Number and Name `10` and `VLAN-Tesing`

![image](https://github.com/user-attachments/assets/16678729-dc15-4f97-af55-eae10cb9b792)

VLAN 10

![image](https://github.com/user-attachments/assets/b1783e52-d7b7-4276-845b-997937d9fb4a)

VLAN 1 (Default)

![image](https://github.com/user-attachments/assets/2cd05c5b-30e1-4aa0-a61a-00d4abd49b02)

Testing Connection via packets and ping ip address

Both PC are in the same subnet

![image](https://github.com/user-attachments/assets/0c25ef4e-f915-4f04-8a3b-87053a736c35)


![image](https://github.com/user-attachments/assets/ba1b89e5-0336-4173-9649-1af537572097)


![image](https://github.com/user-attachments/assets/3a460bec-49ba-45cd-9734-ce28cc9f0a0e)


---
