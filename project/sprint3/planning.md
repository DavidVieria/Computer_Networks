# 📚 Planning

## 👨‍💻 Students

| **Name**                 | **Building** |
|--------------------------|:------------:|
| Igor Coutinho (1230543)  |      1       |
| David Vieira (1230487)   |      2       |
| Rafael Barbosa (1230544) |      3       |
| Daniel Silva (1231046)   |      4       |

---

## 📌 Task Assignment

| **Task** | **Task Description**                                                                                                                                                                                                                                                | **Student** |
|:--------:|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------:|
| **3.1**  | Update the Packet Tracer simulation (building1.pkt) from the previous sprint's Layer 3, to include the features described in this sprint for building one.                                                                                                          | **1230543** |
| **3.2**  | Update the Packet Tracer simulation (building2.pkt) from the previous sprint's Layer 3, to include the features described in this sprint for building two. Final integration of each member's Packet Tracer simulations into a single simulation file (campus.pkt). | **1230487** |
| **3.3**  | Update the Packet Tracer simulation (building3.pkt) from the previous sprint's Layer 3, to include the features described in this sprint for building three.                                                                                                        | **1230544** |
| **3.4**  | Update the Packet Tracer simulation (building4.pkt) from the previous sprint's Layer 3, to include the features described in this sprint for building four.                                                                                                         | **1231046** |

---

## 🧩 Subtasks by Building

> Each building follows a very similar plan. For greater clarity, the subtasks are organized into sections and detailed in the full content below.

- ### 🏢 Building 1

|   **Task**   | **Task Description**                                                                                                 |
|:------------:|----------------------------------------------------------------------------------------------------------------------|
| OSPF Routing | Configure OSPF with a dedicated area for the building and include the default route (default-information originate). |
| HTTP Server  | Add a second HTTP/HTTPS server in the DMZ with a static IP and an HTML page identifying the building.                |
|    DHCPv4    | Configure DHCPv4 for all VLANs except DMZ and backbone; include option 150 for VoIP.                                 |
|     VoIP     | Configure VoIP service with two IP phones model 7960 and voice VLANs on the switches.                                |
|     DNS      | Create the main domain, configure the DNS server. Know the IPs of the subdomain servers (buildings 2-4).             |
|   Firewall   | Configure the firewall to block unwanted traffic.                                                                    |

<br>

- ### 🏢 Building 2

|   **Task**   | **Task Description**                                                                                  |
|:------------:|-------------------------------------------------------------------------------------------------------|
| OSPF Routing | Configure OSPF with a dedicated area for the building.                                                |
| HTTP Server  | Add a second HTTP/HTTPS server in the DMZ with a static IP and an HTML page identifying the building. |
|    DHCPv4    | Configure DHCPv4 for all VLANs except DMZ and backbone; include option 150 for VoIP.                  |
|     VoIP     | Configure VoIP service with two IP phones model 7960 and voice VLANs on the switches.                 |
|     DNS      | Create subdomain, configure DNS server. Know the IP of the DNS server of building 1.                  |
|   Firewall   | Configure the firewall to block unwanted traffic.                                                     |

<br>

- ### 🏢 Building 3

|   **Task**   | **Task Description**                                                                                  |
|:------------:|-------------------------------------------------------------------------------------------------------|
| OSPF Routing | Configure OSPF with a dedicated area for the building.                                                |
| HTTP Server  | Add a second HTTP/HTTPS server in the DMZ with a static IP and an HTML page identifying the building. |
|    DHCPv4    | Configure DHCPv4 for all VLANs except DMZ and backbone; include option 150 for VoIP.                  |
|     VoIP     | Configure VoIP service with two IP phones model 7960 and voice VLANs on the switches.                 |
|     DNS      | Create subdomain, configure DNS server. Know the IP of the DNS server of building 1.                  |
|   Firewall   | Configure the firewall to block unwanted traffic.                                                     |

<br>

- ### 🏢 Building 4

|   **Task**   | **Task Description**                                                                                  |
|:------------:|-------------------------------------------------------------------------------------------------------|
| OSPF Routing | Configure OSPF with a dedicated area for the building.                                                |
| HTTP Server  | Add a second HTTP/HTTPS server in the DMZ with a static IP and an HTML page identifying the building. |
|    DHCPv4    | Configure DHCPv4 for all VLANs except DMZ and backbone; include option 150 for VoIP.                  |
|     VoIP     | Configure VoIP service with two IP phones model 7960 and voice VLANs on the switches.                 |
|     DNS      | Create subdomain, configure DNS server. Know the IP of the DNS server of building 1.                  |
|   Firewall   | Configure the firewall to block unwanted traffic.                                                     |

---

## ⚙️ Technical Decisions

- **Packet Tracer:**
    - version 8.2.2


- **VTP Domain:**
    - `r2425ddg2`


- **Device Naming:**
    - `Building_Device_Floor` (ex: `B2_PC_F0`)
    - `Building_Device_Number` (ex: `B2_Laptop_1`)


- **VLANs ID:**
    - 362 – 383


- **Router Model:**
    - 2811

---

## 🗂️ VLAN Database


> Table with 21 VLANs of the buildings + Backbone (ID 362 to 382) defined, with names and descriptions for each type of traffic:


| VLAN ID | name VLAN       | description VLAN                                              |
|---------|-----------------|---------------------------------------------------------------|
| 362     | B1_floor0       | Building 1 - Floor 0 (outlets)                                |
| 363     | B1_floor1       | Building 1 - Floor 1 (outlets)                                |
| 364     | B1_wifi_network | Building 1 - Wifi Network (access points)                     |
| 365     | B1_DMZ          | Building 1 - DMZ (Servers, administration and infrastructure) |
| 366     | B1_VoIP         | Building 1 - VoIP (IP-phones)                                 |
| 367     | B2_floor0       | Building 2 - Floor 0 (outlets)                                |
| 368     | B2_floor1       | Building 2 - Floor 1 (outlets)                                |
| 369     | B2_wifi_network | Building 2 - Wifi Network (access points)                     |
| 370     | B2_DMZ          | Building 2 - DMZ (Servers, administration and infrastructure) |
| 371     | B2_VoIP         | Building 2 - VoIP (IP-phones)                                 |
| 372     | B3_floor0       | Building 3 - Floor 0 (outlets)                                |
| 373     | B3_floor1       | Building 3 - Floor 1 (outlets)                                |
| 374     | B3_wifi_network | Building 3 - Wifi Network (access points)                     |
| 375     | B3_DMZ          | Building 3 - DMZ (Servers, administration and infrastructure) |
| 376     | B3_VoIP         | Building 3 - VoIP (IP-phones)                                 |
| 377     | B4_floor0       | Building 4 - Floor 0 (outlets)                                |
| 378     | B4_floor1       | Building 4 - Floor 1 (outlets)                                |
| 379     | B4_wifi_network | Building 4 - Wifi Network (access points)                     |
| 380     | B4_DMZ          | Building 4 - DMZ (Servers, administration and infrastructure) |
| 381     | B4_VoIP         | Building 4 - VoIP (IP-phones)                                 |
| 382     | Backbone        | Backbone's VLAN (common to all buildings)                     |

---

## 🏗️ IP Addresses of Router Interfaces in the Campus Backbone Network (VLAN 382)

To ensure connectivity between the buildings, it was established that each router would receive an IP address 
in VLAN 382 (Backbone). These addresses support communication between routers and traffic forwarding between different OSPF areas.


| Building   | Router | IP Address in VLAN 382 |
|------------|--------|------------------------|
| Building 1 | R1     | 10.22.97.1             |
| Building 2 | R2     | 10.22.97.3             |
| Building 3 | R3     | 10.22.97.4             |
| Building 4 | R4     | 10.22.97.5             |

---


## 🏠 Definition of the OSPF Domain in the Campus


### Define the OSPF Domain (Autonomous System):

As requested in the statement of this sprint, the new infrastructure will operate as a single 
OSPF domain, considered a single autonomous system by the other routing protocols.


### Table: Definition of OSPF Areas in the Campus

As established in the planning meeting, the OSPF areas were distributed as follows:

| Building       | Role in the OSPF Network | OSPF Area ID (Decimal) | OSPF Area ID (Dot-decimal) |
|----------------|--------------------------|------------------------|----------------------------|
| **Backbone**   | Main Area (*Backbone*)   | 0                      | 0.0.0.0                    |
| **Building 1** | Local Network Area       | 1                      | 0.0.0.1                    |
| **Building 2** | Local Network Area       | 2                      | 0.0.0.2                    |
| **Building 3** | Local Network Area       | 3                      | 0.0.0.3                    |
| **Building 4** | Local Network Area       | 4                      | 0.0.0.4                    |


### Definition of the OSPF Router IDs in the Campus

| **Building**              | **Router-ID (IPv4)** |
|---------------------------|----------------------|
| **Building 1 (Backbone)** | 1.1.1.1              |
| **Building 2**            | 2.2.2.2              |
| **Building 3**            | 3.3.3.3              |
| **Building 4**            | 4.4.4.4              |

**Note:** The router in Building 1 will introduce the default route 
into OSPF (command `default-information originate`).


### Configuration of OSPF Areas and IPv4 Addresses by Building

| Building       | Network / Interface      | Network Address | Netmask         | Wildcard Mask | OSPF Area |
|----------------|--------------------------|-----------------|-----------------|---------------|-----------|
| **Backbone**   | Backbone between routers | 10.22.97.0      | 255.255.255.0   | 0.0.0.255     | 0         |
|                | Internet Connection      | 87.5.127.92     | 255.255.255.252 | 0.0.0.3       | 0         |
| **Building 1** | F0 (VLAN 362)            | 10.22.98.0      | 255.255.255.192 | 0.0.0.63      | 1         |
|                | F1 (VLAN 363)            | 10.22.98.64     | 255.255.255.192 | 0.0.0.63      | 1         |
|                | WIFI (VLAN 364)          | 10.22.98.128    | 255.255.255.128 | 0.0.0.127     | 1         |
|                | VoIP (VLAN 366)          | 10.22.99.0      | 255.255.255.128 | 0.0.0.127     | 1         |
|                | DMZ (VLAN 365)           | 10.22.99.128    | 255.255.255.128 | 0.0.0.127     | 1         |
| **Building 2** | WIFI (VLAN 369)          | 10.22.100.0     | 255.255.255.0   | 0.0.0.255     | 2         |
|                | F0 (VLAN 367)            | 10.22.101.0     | 255.255.255.128 | 0.0.0.127     | 2         |
|                | F1 (VLAN 368)            | 10.22.101.128   | 255.255.255.128 | 0.0.0.127     | 2         |
|                | VoIP (VLAN 371)          | 10.22.102.0     | 255.255.255.128 | 0.0.0.127     | 2         |
|                | DMZ (VLAN 370)           | 10.22.102.128   | 255.255.255.192 | 0.0.0.63      | 2         |
| **Building 3** | WIFI (VLAN 374)          | 10.22.104.0     | 255.255.255.0   | 0.0.0.255     | 3         |
|                | VoIP (VLAN 376)          | 10.22.105.0     | 255.255.255.0   | 0.0.0.255     | 3         |
|                | F1 (VLAN 373)            | 10.22.106.0     | 255.255.255.0   | 0.0.0.255     | 3         |
|                | F0 (VLAN 372)            | 10.22.107.0     | 255.255.255.128 | 0.0.0.127     | 3         |
|                | DMZ (VLAN 375)           | 10.22.107.128   | 255.255.255.192 | 0.0.0.63      | 3         |
| **Building 4** | WIFI (VLAN 379)          | 10.22.108.0     | 255.255.255.0   | 0.0.0.255     | 4         |
|                | VoIP (VLAN 381)          | 10.22.109.0     | 255.255.255.0   | 0.0.0.255     | 4         |
|                | F1 (VLAN 378)            | 10.22.110.0     | 255.255.255.0   | 0.0.0.255     | 4         |
|                | F0 (VLAN 377)            | 10.22.111.0     | 255.255.255.128 | 0.0.0.127     | 4         |
|                | DMZ (VLAN 380)           | 10.22.111.128   | 255.255.255.192 | 0.0.0.63      | 4         |

---


## 🖥️ DHCPv4 Service


### 🏢 DHCP Configuration - Building 1

| DHCP Pool | Subnet       | Netmask         | Default Router | Excluded Addresses                         | DHCP Options            | VLAN |
|-----------|--------------|-----------------|----------------|--------------------------------------------|-------------------------|------|
| F0_B1     | 10.22.98.0   | 255.255.255.192 | 10.22.98.1     | 10.22.98.1 - 10.22.98.10                   | None                    | F0   |
| F1_B1     | 10.22.98.64  | 255.255.255.192 | 10.22.98.65    | 10.22.98.65 - 10.22.98.74                  | None                    | F1   |
| WIFI_B1   | 10.22.98.128 | 255.255.255.128 | 10.22.98.129   | 10.22.98.129 - 10.22.98.138                | None                    | WIFI |
| VOIP_B1   | 10.22.99.0   | 255.255.255.128 | 10.22.99.1     | 10.22.99.1 - 10.22.99.10, 10.22.99.100     | Option 150: 10.22.99.1  | VoIP |


### 🏢 DHCP Configuration- Building 2

| DHCP Pool | Subnet        | Netmask         | Default Router | Excluded Addresses                        | DHCP Options            | VLAN |
|-----------|---------------|-----------------|----------------|-------------------------------------------|-------------------------|------|
| WIFI_B2   | 10.22.100.0   | 255.255.255.0   | 10.22.100.1    | 10.22.100.1 - 10.22.100.10                | None                    | WIFI |
| F0_B2     | 10.22.101.0   | 255.255.255.128 | 10.22.101.1    | 10.22.101.1 - 10.22.101.10                | None                    | F0   |
| F1_B2     | 10.22.101.128 | 255.255.255.128 | 10.22.101.129  | 10.22.101.129 - 10.22.101.139             | None                    | F1   |
| VOIP_B2   | 10.22.102.0   | 255.255.255.128 | 10.22.102.1    | 10.22.102.1 - 10.22.102.10, 10.22.102.100 | Option 150: 10.22.102.1 | VoIP |


### 🏢 DHCP Configuration - Building 3

| DHCP Pool | Subnet        | Netmask         | Default Router | Excluded Addresses                        | DHCP Options            | VLAN |
|-----------|---------------|-----------------|----------------|-------------------------------------------|-------------------------|------|
| WIFI_B3   | 10.22.104.0   | 255.255.255.0   | 10.22.104.1    | 10.22.104.1 - 10.22.104.10                | None                    | WIFI |
| VOIP_B3   | 10.22.105.0   | 255.255.255.0   | 10.22.105.1    | 10.22.105.1 - 10.22.105.10, 10.22.105.100 | Option 150: 10.22.105.1 | VoIP |
| F1_B3     | 10.22.106.0   | 255.255.255.0   | 10.22.106.1    | 10.22.106.1 - 10.22.106.10                | None                    | F1   |
| F0_B3     | 10.22.107.0   | 255.255.255.128 | 10.22.107.1    | 10.22.107.1 - 10.22.107.10                | None                    | F0   |


### 🏢 DHCP Configuration - Building 4

| DHCP Pool | Subnet        | Netmask         | Default Router | Excluded Addresses                        | DHCP Options            | VLAN |
|-----------|---------------|-----------------|----------------|-------------------------------------------|-------------------------|------|
| WIFI_B4   | 10.22.108.0   | 255.255.255.0   | 10.22.108.1    | 10.22.108.1 - 10.22.108.10                | None                    | WIFI |
| VOIP_B4   | 10.22.109.0   | 255.255.255.0   | 10.22.109.1    | 10.22.109.1 - 10.22.109.10, 10.22.109.100 | Option 150: 10.22.109.1 | VoIP |
| F1_B4     | 10.22.110.0   | 255.255.255.0   | 10.22.110.1    | 10.22.110.1 - 10.22.110.10                | None                    | F1   |
| F0_B4     | 10.22.111.0   | 255.255.255.128 | 10.22.111.1    | 10.22.111.1 - 10.22.111.10                | None                    | F0   |


---


## ☎️ VoIP service

Each building provides the local VoIP service with Cisco IP phones (model 7960) connected to the internal network. This service allows:

- Internal calls within the same building.

- Call forwarding between buildings through the VoIP link between routers.

- Correct configuration of VLANs on switches to separate voice traffic from data traffic.

- DHCP configuration with option 150 pointing to the IP of the local router (TFTP server) for phone configuration distribution.


### Telephone Prefixes, Dial-Peers, and Router IPs by Building

| Building   | Dial-Peer (voice X voip) | Telephone Prefix | Router IP (VoIP VLAN) |
|------------|--------------------------|------------------|-----------------------|
| Building 1 | 1                        | 1xxx             | 10.22.99.1            |
| Building 2 | 2                        | 2xxx             | 10.22.102.1           |
| Building 3 | 3                        | 3xxx             | 10.22.105.1           |
| Building 4 | 4                        | 4xxx             | 10.22.109.1           |


**Dial-Peers for Inter-Building Calls:** Each router will include dial-peers to forward calls to other buildings' prefixes to 
the IP of the corresponding router. For example, calls to prefixes starting with **3**... are forwarded to **IP 10.22.105.1**.


---


## 🌐 DNS

The DNS architecture defined for the project establishes a hierarchy of domains based on the buildings:

- Top-level domain: `rcomp-24-25-dd-g2`, hosted in Building 1.

- Subdomains: `building-X.rcomp-24-25-dd-g2`, where X represents the building number (2, 3, or 4).

- Each building uses the server in its DMZ as the authoritative DNS server for its respective domain.

- All names defined in the DNS databases are FQDN, ending in rcomp-24-25-dd-g2.


### 📛 DNS Server Names

All DNS servers are named ns. Thus, the FQDN of each server is:

| Building   | Domain                       | DNS Server FQDN                 | DNS Server IP   | HTTP Server IP  |
|------------|------------------------------|---------------------------------|-----------------|-----------------|
| Building 1 | rcomp-24-25-dd-g2            | ns.rcomp-24-25-dd-g2            | `10.22.99.130`  | `10.22.99.131`  |
| Building 2 | building-2.rcomp-24-25-dd-g2 | ns.building-2.rcomp-24-25-dd-g2 | `10.22.102.130` | `10.22.102.131` |
| Building 3 | building-3.rcomp-24-25-dd-g2 | ns.building-3.rcomp-24-25-dd-g2 | `10.22.107.130` | `10.22.107.131` |
| Building 4 | building-4.rcomp-24-25-dd-g2 | ns.building-4.rcomp-24-25-dd-g2 | `10.22.111.130` | `10.22.111.131` |


### 🌳 Delegation Structure and Glue Records

- The DNS server of the domain rcomp-24-25-dd-g2 (Building 1) knows the IPs of the DNS servers of the subdomains (buildings 2, 3, and 4).

- The DNS servers of the other buildings know the IP of the DNS server of the top-level domain.

- Each delegation includes:

  - An NS (Name Server) record pointing to the FQDN of the authoritative server.
  - An A record (glue record) associating the FQDN with its IPv4 address.


### 📜 Other DNS Records

In each domain we define:

- **A record:** for `server1` → IP of the web server of the domain.

  - **CNAME** records:

    - www → server1

    - web → server1

    - dns → ns


### 💻 DNS Client Configuration

All end devices in a building will use the local DNS server.

The configuration is done:

- Automatically via DHCP (options `dns-server` and `domain-name` inserted in the DHCP pools).

- Manually on the servers (DMZ) with static IP, indicating the IP of the local DNS server.

---


## 🔀 NAT (Network Address Translation)

As requested for this sprint, we decided to implement static NAT to redirect external HTTP/HTTPS requests to the DNS servers in the DMZ of each building.

### ⚙️ Enabling HTTP/HTTPS Service on the DNS Server in the DMZ

In each building, the DNS server was accessed (e.g., 10.22.99.130 in Building 1) and the HTTP and HTTPS services were enabled in the Services tab.

A custom HTML page was created, identifying the building, domain, and FQDN (e.g., ns.rcomp-24-25-dd-g2 for Building 1).


### 🌐 Static NAT Rules on the Router

On the router of each building, **Port Forwarding (Static NAT)** rules were created to redirect the ports:

- **TCP 80 (HTTP)**
- **TCP 443 (HTTPS)**

The rules redirect the requests:

- Received on the **backbone interface** (external connection)
- To the **IP of the local DNS server** (in the DMZ)

**Example for Building 1:**
```
ip nat inside source static tcp 10.22.99.130 80 10.22.97.1 80
ip nat inside source static tcp 10.22.99.130 443 10.22.97.1 443
```

### 🔁 NAT Interface Association

We chose to associate the NAT interfaces as follows:

- **DMZ** → **ip nat inside**
- **Backbone** → **ip nat outside**


### Expected Outcome

- The HTML page of the DNS server will be accessible from outside the building through the IP of the router's backbone interface.

- Access to the DNS server via the public IP, from inside the building, will not be available — exactly as expected by the NAT configuration on the external interface.


---


## 🔒 ACLs

A static firewall should be implemented on the router of each building, using **Access Control Lists (ACLs)**.
Its configuration will be tested after the main functionalities are completed, so as not to interfere with the already operational services.


### ✅ Objectives to Achieve

The ACLs should follow the following sequence of rules:

1. **Spoofing Prevention**  
   Block all incoming traffic destined for IPs assigned to the router itself.
2. **ICMP Traffic Permission**  
   Allow `echo-request` and `echo-reply` on all interfaces, for diagnostics and monitoring.
3. **DMZ Protection**
  - Block any traffic destined for the DMZ, except:
    - DNS (UDP/TCP 53)
    - HTTP (TCP 80)
    - HTTPS (TCP 443)
  - Allow all traffic from the DMZ to the outside.
4. **Router Access Restriction**  
   Block traffic directed to the router, with exceptions for:
  - DHCP (bootpc → bootps)
  - TFTP (UDP 69)
  - VoIP / ITS (TCP 2000, SIP UDP/TCP 5060)
  - OSPF
  - Static NAT rules (HTTP, HTTPS, and DNS for the DMZ)
5. **Legitimate Traffic Permission**  
   Authorize communication between internal VLANs and access to the outside, according to network policies.

### 🔧 Technical Implementation

The ACLs will be defined with clear names and applied to the respective router interfaces:

- `INTERNET_ACL` – applied to the incoming interface of the backbone (VLAN 382)
- `WIFI_ACL`, `VOIP_ACL`, `GROUND_FLOOR_ACL`, `FLOOR1_ACL` – applied to the interfaces of the corresponding internal VLANs

Each ACL will end with `deny ip any any`, reinforcing the denial by default and ensuring greater clarity in the security policy.


---