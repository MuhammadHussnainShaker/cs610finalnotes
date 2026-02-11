# cs610finalnotes
## Lecture 19

### Label Switching

An ATM network is built from interconnected ATM switches. The attachment points or ports can be connected to computers or other ATM switches. As cells arrive at an ATM switch, their VPI/VCI is modified using a forwarding table that gives the new VPI/VCI for the next leg of the cell’s trip.
The forwarding table is essentially indexed by the incoming cell’s VPI/VCI and the contents yield the new VPI/VCI.

#### LABEL REWRITING:

The replacement of the incoming cell’s VPI/VCI with a probably different VPI/VCI is called rewriting. ATM is thus called a label rewriting or label switching system. Thus two computers with a connection through an ATM network will likely have different VPI/VCI values for each end of the connection as shown in the figure below.

### An Example ATM Network

### Permanent Virtual Circuits (PVC’s)

### Switched Virtual Circuits (SVC’s)

### Quality of Service (QoS)

## Lab 1
### a)- Introduction and gathering addresses (IP/MAC) information
#### Introduction to IP and Mac addressing
- MAC address, or Media Access Control address is a 48 bit address associated with a network adapter.
- TCP: Transmission Control Protocol.
#### Gather TCP/IP configuration information.
- ipconfig
#### Check additional TCP/IP configuration information.
- ipconfig/all
### b) Verification of network connectivity using Ping and trace route
#### Using PING and TRACERT from a Workstation
- ping www.vu.edu.pk
- round-trip time calculation
- The TTL value specifies approximately how many router (i.e. hops) the packet has gone through.
#### Error messages:
- Destination Host Unreachable \
It occurs if host is not found or there is no route to the destination.
- Request Timed Out: happends after 4 seconds. \
This is an indicator that the destination device is not connected to the network, is powered off, or is not configured correctly.
#### Ping the computer’s loopback IP address.
- ping 127.0.0.1 \
If the ping is successful, then TCP/IP is properly installed and functioning on this computer.
#### Using trace route command 
- tracert www.mit.edu \
echoes the router in the request

## Lab  2
- Two workspaces are supported; logical and physical.
- It supports two operating modes—real-time mode and simulation mode. 
Main toolbar: This bar contains shortcut icons to menu options that are frequently accessed. For example, open, save, zoom, undo, and redo.
- Common tools bar: With help of this toolbar, we can manipulate topologies. For example, select, move layout, place note, delete, resize shape, add simple/complex Protocol data unit (PDU).


- Step 1: Start Packet Tracer and enter in logical work space 
- Step 2: Choosing Devices and Connections
- Step 3: Adding Hosts using device selection option 
- Step 4: Connect the Hosts to Hub and Switch 
    - Adding a Hub
    - Adding a Switch
        - The switch port is temporarily not forwarding frames, while it goes through the stages for the Spanning Tree Protocol (STP) process.
- Step 5: Configuring IP Addresses and Subnet Masks on the Hosts
    - Assigning IP and Default Gateway to PC's
    - Connecting Hub0 to Switch0 thorugh crossover cable
    - Adding routers
      - Click on the router to bring up the Configuration Window. This window has three modes: Physical, Config, and CLI (Physical is the default mode). 
      - The Physical mode is used to add modules to a device, such as a WAN Interface Card (WIC). 
      - The Config mode is used for basic configuration. Commands are entered in a simple GUI format, with actual equivalent IOS commands shown in the lower part of the window. 
      - The CLI mode allows for advanced configuration of the device. This mode requires the user to enter the actual IOS commands just as they would on a live device.

## Lab 4
### Different physical equipment used for networking Cables
- Thick Coaxial Cables (thick net) (RG-11)
    - 10base5 Ethernet standard: 10 Mbps, 500 m max length, Baseband, 5 repeaters max, 2500m network diameter.
- Thin coaxial cables (thin net) (RG-58)
    - The maximum length of thin wire Ethernet segment is 185 meters.
    - BNC connectors are used to terminate each end of the cable. 
- Coaxial Cable Connectors
    - Bayone-Neil-Concelman, in short, BNC connector.
    - The three popular types of connectors are: the BNC connector, the BNC T connector, and the BNC terminator. 
    - 10Base-2, or thin Ethernet, uses RG-58 coax cable with BNC connectors.
    - 10Base-5, or thick Ethernet, uses RG-11 coax cable with specialized connectors.
- Twisted pair cables
    -	Unshielded Twisted Pair (UTP)
        - A twisted pair segment can’t exceed 100 meters.
        - used for 10/100 based Ethernet networks
        - wired as straight through or crossover cables. 
        - Crossover cables are used for direct NIC-to-NIC communication and for connecting two hubs when a dedicated crossover (MDI-X) port is unavailable.
    -	Shielded Twisted Pair (STP)
    - Characteristics of twisted pair cable
        1.	Requires amplifiers every 5-6 km for analog signals
        2.	Requires repeaters every 2-3 km for digital signals
        3.	Attenuation increases with frequency
        4.	Susceptible to interference and noise
    - Applications
        1. Used in telephone lines to provide voice and data channels.
        2.	The local loop –the line connecting the subscriber to the central telephone office- commonly consists of UTP cables.
        3.	DSL lines are also UTP cables.
        4.	LANs such as, 10Base-T and 100Base-T use UTP cables.
- Fiber Optic
    - A popular multimode fiber has core/cladding dimensions of 62.5/125 nanometers.
- Configure IP address to routers of two PC's
    - Router(config)#interface fastEthernet 0/0
    - Router(config-if)#ip address 10.0.0.1 255.0.0.0
    - Router(config-if)#no shutdown
    - Router(config-if)#exit
    - Interface Line protocol on FastEthernet0/0, changed state to up
    - --
    - Router(config)#interface fastethernet 1/0
    - Router(config-if)#ip address 20.0.0.1 255.0.0.0
    - Router(config-if)#no shutdown
    - Router(config-if)#exit
    - Interface Line protocol on FastEthernet1/0, changed state to up

## Lab 5
1.	Repeater:
2.	Hub
3.	Bridge
4.  Switch
    - connects network segments
    - operates at the data link layer (Layer 2) of the OSI model
    - can also operate at the network layer (Layer 3) and then is called multilayer switch
    - connects two LAN segments together
5. Router
    - interconnects two or more computer networks.
6. Gateway
    - Used for interfacing one network to another network that uses different protocols. 
    - A gateway may contain devices such as protocol translators, impedance matching devices, rate converters, fault isolators, or signal translators as necessary to provide system interoperability. 

| Feature | Hub | Bridge | Switch |
| :--- | :--- | :--- | :--- |
| **Traffic Direction** | Broadcasts to everyone | Filters between two segments | Directs to specific port |
| **Intelligence** | None | Low (MAC addresses) | High (MAC address table) |
| **Ports** | Usually 4–24 | Usually 2 | Usually 4–48+ |
| **Efficiency** | Low (Frequent collisions) | Medium | High (No collisions) |
| **OSI Layer** | Layer 1 | Layer 2 | Layer 2 |

## Lab 6
### Routing Protocol
- used by routers to dynamically find all the networks in the internetwork
- Examples of routing protocols are RIP, RIPv2, EIGRP, and OSPF.
### Routed Protocol
- used to send user data (packets) through the established routing table.
- determines the method of packet delivery.
- Examples of routed protocols are IP and IPv6.
### Routing Basis
If a destination host is not on the same network, then the router delivers the packet to the remote network using two routing methods:
#### Static Routing
The manual configuration of network routes by an administrator rather than using dynamic protocols. Best suited for small, stable environments.
| Pros | Cons |
| :--- | :--- |
| **Low Overhead:** No CPU/RAM strain on routers. | **Complex Setup:** Requires deep network knowledge. |
| **Bandwidth Saving:** No routing updates sent over links. | **Not Scalable:** Manual updates needed for every new network. |
| **High Security:** Total control over allowed paths. | **No Redundancy:** No auto-rerouting if a link fails. |
#### Dynamic Routing
A technique where routers use protocols (like RIP: Routing Information Protocol or OSPF: Open Shortest Path First) to automatically discover paths and update routing tables in real-time based on network changes.
| Pros | Cons |
| :--- | :--- |
| **Scalable:** Easy to configure and manage on large networks. | **Resource Heavy:** Consumes more CPU, RAM, and bandwidth. |
| **Adaptive:** Automatically reroutes data if a link fails. | **Lower Security:** Protocol updates can be intercepted or spoofed. |
| **Efficient:** Automatically discovers the best paths/remote networks. | **Complexity:** Requires setup of protocols like OSPF or EIGRP. |

## Lab 7
### Introduction to Wireshark
Wireshark is a network protocol analyzer that enables you to capture and interactively browse the traffic running on a computer network.
#### Wireshark’s Features
    1- Available for UNIX and Windows.
    2- Capture live packet data.
    3- Display packets with very detailed protocol information.
    4- Filter packets on many criteria.
    5- Save packet data captured.

#### Installation Components
    • Wireshark - The network protocol analyzer.
    • TShark - A command-line network protocol analyzer.
    • Plugins & Extensions - Extras for the Wireshark and TShark dissection engines.
    • Tools - Additional command line tools to work with capture files
    • User’s Guide
#### Installing WinPcap
With WinPcap installed you would be able to capture live network traffic.
#### Packet List Pane Columns in Wireshark
By default, the Packet List pane contains: No. (number), Time, Source, Destination, Protocol, Length, and Info columns.

## Lab 8
Assign IP to the computer on windows 7

## Lab 9
### Address Resolution Protocol (ARP)

**Definition:** Maps a known **Layer 3 (IP) address** to a physical **Layer 2 (MAC) address** within a local network.

---

#### How it Works

1. **Check Table:** Computer looks at its local **ARP Table**.
2. **Broadcast:** If the MAC is unknown, it broadcasts an **ARP Request** ("Who has this IP?").
3. **Reply:** The device with that IP sends an **ARP Reply** with its MAC address.
4. **Update:** The requesting computer saves the IP/MAC pair in its table.
5. **Timeout:** Entries are dropped after a few minutes of inactivity to keep the table current.

> **Note:** For non-local traffic, the computer ARPs for the **Default Gateway's** MAC address.

---

#### ARP Header Structure

| Field | Description |
| --- | --- |
| **Hardware Type** | Type of hardware (e.g., Ethernet = 1). |
| **Protocol Type** | The protocol being mapped (e.g., IPv4). |
| **Hardware Size** | Length of MAC address (6 bytes for Ethernet). |
| **Protocol Size** | Length of IP address (4 bytes for IPv4). |
| **OpCode** | **1** for Request, **2** for Reply. |
| **Sender MAC** | Layer 2 address of the sender. |
| **Sender IP** | Layer 3 address of the sender. |
| **Target MAC** | MAC of receiver (empty during Request). |
| **Target IP** | IP of the intended receiver. |

- arp -a: Displays the ARP table on Windows.

## Lab 10
### IPv4 Address Subnetting & Classful Addressing

### 1. IP Address Classes
| Class | First Octet Range | Bit Pattern | Network/Host Split | Max Hosts |
| :--- | :--- | :--- | :--- | :--- |
| **A** | 1 – 126 | `0.......` | N.H.H.H | 16.7 Million |
| **B** | 128 – 191 | `10......` | N.N.H.H | 65,534 |
| **C** | 192 – 223 | `110.....` | N.N.N.H | 254 |
<br>
---
---
---

| IP Address Class | Network ID Bits | Host ID Bits | Intended Use |
| --- | --- | --- | --- |
| Class A | 8 | 24 | Used for addressing very large organizations with hundreds of thousands or millions of hosts to connect to the Internet. |
| Class B | 16 | 16 | Used for addressing medium-to-large organizations with hundreds to thousands of hosts to connect to the Internet. |
| Class C | 24 | 8 | Used for addressing smaller organizations with no more than about 250 hosts to connect to the Internet. |
| Class D | n/a | n/a | IP multicasting. |
| Class E | n/a | n/a | Reserved for "experimental use". |

---
---
---

| IP Address Class | Lowest Binary Value of First Octet | Highest Binary Value of First Octet | Range of First Octet Decimal Values | Theoretical IP Address Range |
| --- | --- | --- | --- | --- |
| Class A | **0000** 0001 | **0111** 1110 | 1 to 126 | **1.0.0.0** to **126.255.255.255** |
| Class B | **1000** 0000 | **1011** 1111 | 128 to 191 | **128.0.0.0** to **191.255.255.255** |
| Class C | **1100** 0000 | **1101** 1111 | 192 to 223 | **192.0.0.0** to **223.255.255.255** |
| Class D | **1110** 0000 | **1110** 1111 | 224 to 239 | 224.0.0.0 to 239.255.255.255 |
| Class E | **1111** 0000 | **1111** 1111 | 240 to 255 | 240.0.0.0 to 255.255.255.255 |

---
---
---
---


| IP Address Class | Network ID Bits/ Host ID Bits | First Octet of IP Address | Number of Possible Network IDs | # Of Host IDs Per Network ID |
| --- | --- | --- | --- | --- |
| Class A | 8 / 24 | **0**xxx xxxx |  |  |
| Class B | 16 / 16 | **10**xx xxxx |  |  |
| Class C | 24 / 8 | **110**x xxxx |  |  |

---


### 2. Special Address Patterns
* **All Zeros:** Represents the **Network ID** (the network's identity).
* **All Ones:** Represents the **Broadcast ID** (communication to all hosts).

### 3. Reserved Ranges
* **Loopback (127.0.0.0/8):** Used for internal testing (Software).
* **Private Addresses:** Used for local networks (not public-routable).

## Lab 11
### 1.	Subnetting of Classful IP Addressing 
The host ID can be split into, say, 3 bits for a subnet ID and 5 for the host ID
### 2.	Classless Addressing 
If either Subnetting or classless addressing is used, then the subnet mask or “slash number” are required to fully qualify the address.
### 3.	IP Subnet Addressing ("Subnetting") Concepts 
- Subnetting is the process of dividing a network into smaller subnetworks (subnets).
- A three-level hierarchy is thus created: networks, which contain subnets, each of which then has a number of hosts.

### 4. IP Subnet Masks, Notation and Subnet Calculations
Subnetting uses a **Boolean AND** operation between an **IP Address** and a **Subnet Mask** to determine the **Network ID**.

#### CIDR (Slash) Notation

Instead of writing out the full mask (e.g., `255.255.248.0`), we use a slash followed by the number of "1" bits in the mask.

* **Example:** `154.71.150.42/21`
* **The "/21":** Represents 21 network bits and 11 host bits ().

#### Key Concepts

* **VLSM (Variable-Length Subnet Masking):** Allows for subnets of different sizes within the same network to prevent IP waste.
* **CIDR (Classlesss Inter-Domain Routing ):** The modern standard for classless addressing, replacing the old Class A, B, and C system.

### 6.	Deciding How Many Subnet Bits to Use
#### The Golden Formulas

To determine your network's capacity, use these two equations:

1. **Number of Subnets** = $2^s$
* *Where **s** is the number of bits "borrowed" from the host portion*.
2. **Number of Hosts per Subnet** = $(2^h) - 2$
* *Where **h** is the number of bits remaining in the host portion*.
##### Why do we subtract 2?
In every subnet, two addresses are reserved and cannot be assigned to devices:

* **The Network ID:** The very first address (all host bits are 0).
* **The Broadcast Address:** The very last address (all host bits are 1).

---

## Lab 12
### Network Subnetting: Requirements Analysis

To analyze network requirements for subnetting, focus on five core questions regarding the current state and near-future growth:

* **IP Class**: Identify the existing IP address block class (A, B, or C).
* **Physical Subnets**: Determine the current number of physical subnets (broadcast domains bounded by routers).
* **Subnet Growth**: Plan for the number of additional physical networks required in the near future.
* **Current Host Density**: Identify the number of hosts in the largest existing subnet.
* **Future Host Density**: Forecast the number of hosts for the largest subnet in the near future.

---
### 7. VLSM & Route Summarization:
How to calculate subnet ID and Subnet Address?
### Formula:

* **The Increment**: The distance between one subnet and the next.
* **The Formula**: $2^h$, where $h$ is the number of host bits remaining.
* **The Application**: Take the starting address of a subnet and add the increment to find where the next subnet begins.

---

## Lab 14
| Feature | IPv4 | IPv6 |
| --- | --- | --- |
| Address Length | 32-bit length | 128-bit length |
| Representation | Binary numbers represented in decimals | Binary numbers represented in hexadecimals |
| IPsec Support | Only optional | Inbuilt IPsec support |
| Fragmentation | Done by sender and forwarding routers | Done only by sender |
| Packet Flow Identification | No packet flow identification | Available using the Flow Label field |
| Options/Extension Headers | Options fields are available in header | No option fields; uses Extension headers |
| Broadcast | Broadcast messages are available | Not available; uses "All nodes" multicast (FF02::1) |
| Configuration | Manual (Static) or DHCP (Dynamic) | Auto-configuration is available |
