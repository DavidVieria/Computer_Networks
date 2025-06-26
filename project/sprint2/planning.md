# 📚 Planning

## 👨‍💻 Students

| **Name**               | **Building** |
|------------------------|:------------:|
| Igor (1230543)         |      1       |
| David (1230487)        |      2       |
| Rafael (1230544)       |      3       |
| Daniel (1231046)       |      4       |

---

## 📌 Task Assignment

| **Task** | **Task Description**                                                                                                                                                                                       | **Student** |
|:--------:|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------:|
| **2.1**  | Development of a Packet Tracer simulation for both layer two and layer three for building 1, covering the campus backbone. Integration of each member's Packet Tracer simulation into a single simulation. | **1230543** |
| **2.2**  | Development of a Packet Tracer simulation for both layer two and layer three for building 2, covering the campus backbone.                                                                                 | **1230487** |
| **2.3**  | Development of a Packet Tracer simulation for both layer two and layer three for building 3, covering the campus backbone.                                                                                 | **1230544** |
| **2.4**  | Development of a Packet Tracer simulation for both layer two and layer three for building 4, covering the campus backbone.                                                                                 | **1231046** |

---

## 🧩 Subtasks by Building

> Each building follows a very similar plan. For clarity, the subtasks are organized in sections and detailed in the full content below.

- ### 🏢 Building 1

|  **Task**  | **Task Description**                                                                     |
|:----------:|------------------------------------------------------------------------------------------|
| **2.1.1**  | Place devices in Building 1: PCs, laptops, servers, IP phones, switches, routers         |
| **2.1.2**  | Name the devices in Building 1 using the team conventions                                |
| **2.1.3**  | Configure the VTP domain (`r2425ddg2`) on the main switch of Building 1 (server mode)    |
| **2.1.4**  | Add 4 building VLANs (F0, F1, WiFi, DMZ, VoIP) + backbone VLAN to the main switch        |
| **2.1.5**  | Connect the switches in Building 1 with fiber/copper according to the cabling project    |
| **2.1.6**  | Set all connections between switches to trunk mode (all VLANs allowed)                   |
| **2.1.7**  | Configure non-main switches in Building 1 as VTP clients                                 |
| **2.1.8**  | Assign access ports: F0/F1 VLANs for PCs, WiFi VLAN for AP, VoIP VLAN for phones         |
| **2.1.9**  | Assign static IPv4 addresses to devices in Building 1                                    |
| **2.1.10** | Configure router subinterfaces for each VLAN                                             |
| **2.1.11** | Connect Building 1's router to the backbone VLAN and assign an IP                        |
| **2.1.12** | Add static routes on Building 1's router for the backbone and other buildings            |
| **2.1.13** | Simulate backbone connections to other buildings (trunk mode)                            |
| **2.1.14** | Validate redundancy paths between switches in Building 1                                 |
| **2.1.15** | Document Building 1 specifications: VLAN IDs, IP ranges, routing tables in `planning.md` |

<br>

- ### 🏢 Building 2

|  **Task**  | **Task Description**                                                                     |
|:----------:|------------------------------------------------------------------------------------------|
| **2.2.1**  | Place devices in Building 2: PCs, laptops, servers, IP phones, switches, routers         |
| **2.2.2**  | Name the devices in Building 2 using the team conventions                                |
| **2.2.3**  | Configure the VTP domain (`r2425ddg2`) on the main switch of Building 2 (server mode)    |
| **2.2.4**  | Add 4 building VLANs (F0, F1, WiFi, DMZ, VoIP) + backbone VLAN to the main switch        |
| **2.2.5**  | Connect the switches in Building 2 with fiber/copper according to the cabling project    |
| **2.2.6**  | Set all connections between switches to trunk mode (all VLANs allowed)                   |
| **2.2.7**  | Configure non-main switches in Building 2 as VTP clients                                 |
| **2.2.8**  | Assign access ports: F0/F1 VLANs for PCs, WiFi VLAN for AP, VoIP VLAN for phones         |
| **2.2.9**  | Assign static IPv2 addresses to devices in Building 2                                    |
| **2.2.10** | Configure router subinterfaces for each VLAN                                             |
| **2.2.11** | Connect Building 2's router to the backbone VLAN and assign an IP                        |
| **2.2.12** | Add static routes on Building 2's router for the backbone and other buildings            |
| **2.2.13** | Simulate backbone connections to other buildings (trunk mode)                            |
| **2.2.14** | Validate redundancy paths between switches in Building 2                                 |
| **2.2.15** | Document Building 2 specifications: VLAN IDs, IP ranges, routing tables in `planning.md` |

<br>

- ### 🏢 Building 3

|  **Task**  | **Task Description**                                                                     |
|:----------:|------------------------------------------------------------------------------------------|
| **2.3.1**  | Place devices in Building 3: PCs, laptops, servers, IP phones, switches, routers         |
| **2.3.2**  | Name the devices in Building 3 using the team conventions                                |
| **2.3.3**  | Configure the VTP domain (`r2425ddg2`) on the main switch of Building 3 (server mode)    |
| **2.3.4**  | Add 4 building VLANs (F0, F1, WiFi, DMZ, VoIP) + backbone VLAN to the main switch        |
| **2.3.5**  | Connect the switches in Building 3 with fiber/copper according to the cabling project    |
| **2.3.6**  | Set all connections between switches to trunk mode (all VLANs allowed)                   |
| **2.3.7**  | Configure non-main switches in Building 3 as VTP clients                                 |
| **2.3.8**  | Assign access ports: F0/F1 VLANs for PCs, WiFi VLAN for AP, VoIP VLAN for phones         |
| **2.3.9**  | Assign static IPv3 addresses to devices in Building 3                                    |
| **2.3.10** | Configure router subinterfaces for each VLAN                                             |
| **2.3.11** | Connect Building 3's router to the backbone VLAN and assign an IP                        |
| **2.3.12** | Add static routes on Building 4's router for the backbone and other buildings            |
| **2.3.13** | Simulate backbone connections to other buildings (trunk mode)                            |
| **2.3.14** | Validate redundancy paths between switches in Building 3                                 |
| **2.3.15** | Document Building 3 specifications: VLAN IDs, IP ranges, routing tables in `planning.md` |

<br>

- ### 🏢 Building 4

|  **Task**  | **Task Description**                                                                     |
|:----------:|------------------------------------------------------------------------------------------|
| **2.4.1**  | Place devices in Building 4: PCs, laptops, servers, IP phones, switches, routers         |
| **2.4.2**  | Name the devices in Building 4 using the team conventions                                |
| **2.4.3**  | Configure the VTP domain (`r2425ddg2`) on the main switch of Building 4 (server mode)    |
| **2.4.4**  | Add 4 building VLANs (F0, F1, WiFi, DMZ, VoIP) + backbone VLAN to the main switch        |
| **2.4.5**  | Connect the switches in Building 4 with fiber/copper according to the cabling project    |
| **2.4.6**  | Set all connections between switches to trunk mode (all VLANs allowed)                   |
| **2.4.7**  | Configure non-main switches in Building 4 as VTP clients                                 |
| **2.4.8**  | Assign access ports: F0/F1 VLANs for PCs, WiFi VLAN for AP, VoIP VLAN for phones         |
| **2.4.9**  | Assign static IPv4 addresses to devices in Building 4                                    |
| **2.4.10** | Configure router subinterfaces for each VLAN                                             |
| **2.4.11** | Connect Building 4's router to the backbone VLAN and assign an IP                        |
| **2.4.12** | Add static routes on Building 4's router for the backbone and other buildings            |
| **2.4.13** | Simulate backbone connections to other buildings (trunk mode)                            |
| **2.4.14** | Validate redundancy paths between switches in Building 4                                 |
| **2.4.15** | Document Building 4 specifications: VLAN IDs, IP ranges, routing tables in `planning.md` |

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


>Table includes 21 VLANs from the buildings + Backbone (ID 362 to 382), with names and descriptions for each type of traffic.


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

## 🎯 General Objectives

- Create a simulation of the networks by building including the common backbone.
- Standardize the naming of devices.
- Simulate cabling structure with appropriate switches and cables.

---

## 🧱 Layer 2 Configuration

- VLANs by floor, WiFi, DMZ, and VoIP in each building.
- Common Backbone VLAN for all.
- Switches connected in trunk.
- VTP configured with one server per building.
- STP active on all switches.

---

## 🌐 Layer 3 Configuration

- Each VLAN with dedicated IPv4 subnet.
- Router model 2811 per building with subinterfaces.
- Inter-VLAN traffic routed via backbone.
- Addressing based on `10.22.96.0/20` block (see complete tables by building).

---

## 📄 Detailed Technical Content

### 🔌 VLANs
In each building, the following VLANs must be configured:

- **Floor 0**: VLAN for all outlets.
- **Floor 1**: VLAN for all outlets.
- **Wi-Fi Network**: VLAN for all APs' outlets within the building.
- **DMZ**: VLAN for servers, administrative workstations, and network infrastructure devices.
- **VoIP**: VLAN for all IP phones within the building.

These VLANs, despite being associated with a specific building, must be available on all switches of all buildings. Each switch must maintain a local database with all VLANs, and all interconnections between switches must be configured in trunk mode to carry all VLANs.

Additionally, a VLAN for the Campus Backbone must be configured, shared by all buildings. This VLAN must be available on all switches, in their local databases.
<br><br>

### ⚙️ VLAN Trunking Protocol (VTP)
To ensure consistency among switches, use VTP, which facilitates the propagation of VLAN information.

- **VTP Domain**: All switches must be in the same VTP domain, with the domain name configured uniformly (vtp domain ...).
- **Server mode**: At least one switch must be in server mode (vtp mode server), where the VLAN database can be manually configured.
- **Client mode**: Other switches can be in client mode (vtp mode client), where they receive updates of the VLAN database propagated by switches in server mode.
- **Trunk mode**: The interconnection ports between switches must be configured in trunk mode (switchport mode trunk), allowing the propagation of all VLANs.
  <br><br>

### 📊 VLAN Database & VTP Domain

- **VLANs**: Each VLAN must have a unique and meaningful name, with a unique VLANID (between 2 and 1000, to avoid interference).
- **VTP Domain**: The name of the VTP domain must be the same on all switches to ensure correct propagation.
  <br><br>

### 🌐 IPv4 Networks

#### Addressing Requirements

IPv4 network addresses for each VLAN must be assigned according to the following node number requirements:

- **Building Campus Backbone**:
  - **Backbone**: 220 nodes


- **Building 1**:
  - **Access points - Floor 0**: 40 nodes
  - **Access points - Floor 1**: 45 nodes
  - **Wi-Fi**: 95 nodes
  - **DMZ (Servers, administrative workstations, and network infrastructure devices)**: 110 nodes
  - **VoIP (IP Phones)**: 70 nodes
  - **B1**: 360 nodes


- **Building 2**:
  - **Access points - Floor 0**: 100 nodes
  - **Access points - Floor 1**: 110 nodes
  - **Wi-Fi**: 200 nodes
  - **DMZ (Servers, administrative workstations, and network infrastructure devices)**: 60 nodes
  - **VoIP (IP Phones)**: 120 nodes
  - **B2**: 690 nodes


- **Building 3**:
  - **Access points - Floor 0**: 115 nodes
  - **Access points - Floor 1**: 135 nodes
  - **Wi-Fi**: 220 nodes
  - **DMZ (Servers, administrative workstations, and network infrastructure devices)**: 50 nodes
  - **VoIP (IP Phones)**: 170 nodes
  - **B3**: 690 nodes


- **Building 4**:
  - **Access points - Floor 0**: 125 nodes
  - **Access points - Floor 1**: 170 nodes
  - **Wi-Fi**: 200 nodes
  - **DMZ (Servers, administrative workstations, and network infrastructure devices)**: 45 nodes
  - **VoIP (IP Phones)**: 160 nodes
  - **B4**: 700 nodes


- **General**:
  - **Sprint Planning**: The team must define:
    - The IPv4 network address for the Campus Backbone.
    - The IPv4 address of the routers for the connection to the backbone network.
    - The address block for each team member within their building, ensuring no overlap between blocks.
      <br><br>

#### 🔧 IPv4 Address Space

- **IPv4 Address Block to be used**: 10.22.96.0/20
<br><br>

#### 🏠 IPv4 Addressing Distribution by Zone/Building

| **Subnet address** |  **Netmask**  |   **Range of addresses**    |       **Usable IPs**        | **Hosts** | **Zones/Buildings** |
|:------------------:|:-------------:|:---------------------------:|:---------------------------:|:---------:|:-------------------:|
|   10.22.96.0/24    | 255.255.255.0 |  10.22.96.0 - 10.22.96.255  |  10.22.96.1 - 10.22.96.254  |    254    |          -          |
|   10.22.97.0/24    | 255.255.255.0 |  10.22.97.0 - 10.22.97.255  |  10.22.97.1 - 10.22.97.254  |    254    |   Campus Backbone   |
|   10.22.98.0/23    | 255.255.254.0 |  10.22.98.0 - 10.22.99.255  |  10.22.98.1 - 10.22.99.254  |    510    |     Building 1      |
|   10.22.100.0/22   | 255.255.252.0 | 10.22.100.0 - 10.22.103.255 | 10.22.100.1 - 10.22.103.254 |   1022    |     Building 2      |
|   10.22.104.0/22   | 255.255.252.0 | 10.22.104.0 - 10.22.107.255 | 10.22.104.1 - 10.22.107.254 |   1022    |     Building 3      |
|   10.22.108.0/22   | 255.255.252.0 | 10.22.108.0 - 10.22.111.255 | 10.22.108.1 - 10.22.111.254 |   1022    |     Building 4      |

<br>

#### 🏢 Building 1

|  **Subnet address**  |     Netmask     |      Range of addresses      |         Useable IPs          | Hosts  | VLAN |
|:--------------------:|:---------------:|:----------------------------:|:----------------------------:|:------:|:----:|
|  **10.22.98.0/26**   | 255.255.255.192 |   10.22.98.0 - 10.22.98.63   |   10.22.98.1 - 10.22.98.62   |   62   |  F0  |
|  **10.22.98.64/26**  | 255.255.255.192 |  10.22.98.64 - 10.22.98.127  |  10.22.98.65 - 10.22.98.126  |   62   |  F1  |
| **10.22.98.128/25**  | 255.255.255.128 | 10.22.98.128 - 10.22.98.255  | 10.22.98.129 - 10.22.98.254  |  126   | WIFI |
|  **10.22.99.0/25**   | 255.255.255.128 |  10.22.99.0 - 10.22.99.127   |  10.22.99.1 - 10.22.99.126   |  126   | VoIP |
| **10.22.99.128/25**  | 255.255.255.128 | 10.22.99.128 - 10.22.99.255  | 10.22.99.129 - 10.22.99.254  |  126   | DMZ  |

<br>

#### 🏢 Building 2

| **Subnet address**  |   **Netmask**    |     **Range of addresses**     |        **Useable IPs**         | **Hosts**  | **VLAN**  |
|:-------------------:|:----------------:|:------------------------------:|:------------------------------:|:----------:|:---------:|
|   10.22.100.0/24    |  255.255.255.0   |  10.22.100.0 - 10.22.100.255   |  10.22.100.1 - 10.22.100.254   |    254     |   WIFI    |
|   10.22.101.0/25    | 255.255.255.128  |  10.22.101.0 - 10.22.101.127   |  10.22.101.1 - 10.22.101.126   |    126     |    F0     |
|  10.22.101.128/25   | 255.255.255.128  | 10.22.101.128 - 10.22.101.255  | 10.22.101.129 - 10.22.101.254  |    126     |    F1     |
|   10.22.102.0/25    | 255.255.255.128  |  10.22.102.0 - 10.22.102.127   |  10.22.102.1 - 10.22.102.126   |    126     |   VoIP    |
|  10.22.102.128/26   | 255.255.255.192  | 10.22.102.128 - 10.22.102.191  | 10.22.102.129 - 10.22.102.190  |     62     |    DMZ    |
|  10.22.102.192/26   | 255.255.255.192  | 10.22.102.192 - 10.22.102.255  | 10.22.102.193 - 10.22.102.254  |     62     |     -     |
|   10.22.103.0/24    |  255.255.255.0   |  10.22.103.0 - 10.22.103.255   |  10.22.103.1 - 10.22.103.254   |    254     |     -     |

<br>

#### 🏢 Building 3

| **Subnet address**  |   **Netmask**    |     **Range of addresses**     |        **Useable IPs**         | **Hosts**  | **VLAN**  |
|:-------------------:|:----------------:|:------------------------------:|:------------------------------:|:----------:|:---------:|
|   10.22.104.0/24    |  255.255.255.0   |  10.22.104.0 - 10.22.104.255   |  10.22.104.1 - 10.22.104.254   |    254     |   WIFI    |
|   10.22.105.0/24    |  255.255.255.0   |  10.22.105.0 - 10.22.105.255   |  10.22.105.1 - 10.22.105.254   |    254     |   VoIP    |
|   10.22.106.0/24    |  255.255.255.0   |  10.22.106.0 - 10.22.106.255   |  10.22.106.1 - 10.22.106.254   |    254     |    F1     |
|   10.22.107.0/25    | 255.255.255.128  |  10.22.107.0 - 10.22.107.127   |  10.22.107.1 - 10.22.107.126   |    126     |    F0     |
|  10.22.107.128/26   | 255.255.255.192  | 10.22.107.128 - 10.22.107.191  | 10.22.107.129 - 10.22.107.190  |     62     |    DMZ    |
|  10.22.107.192/26   | 255.255.255.192  | 10.22.107.192 - 10.22.107.255  | 10.22.107.193 - 10.22.107.254  |     62     |     -     |

<br>

#### 🏢 Building 4

| **Subnet address**  |   **Netmask**    |     **Range of addresses**     |        **Useable IPs**         | **Hosts**  | **VLAN**  |
|:-------------------:|:----------------:|:------------------------------:|:------------------------------:|:----------:|:---------:|
|   10.22.108.0/24    |  255.255.255.0   |  10.22.108.0 - 10.22.108.255   |  10.22.108.1 - 10.22.108.254   |    254     |   WIFI    |
|   10.22.109.0/24    |  255.255.255.0   |  10.22.109.0 - 10.22.109.255   |  10.22.109.1 - 10.22.109.254   |    254     |   VoIP    |
|   10.22.110.0/24    |  255.255.255.0   |  10.22.110.0 - 10.22.110.255   |  10.22.110.1 - 10.22.110.254   |    254     |    F1     |
|   10.22.111.0/25    | 255.255.255.128  |  10.22.111.0 - 10.22.111.127   |  10.22.111.1 - 10.22.111.126   |    126     |    F0     |
|  10.22.111.128/26   | 255.255.255.192  | 10.22.111.128 - 10.22.111.191  | 10.22.111.129 - 10.22.111.190  |     62     |    DMZ    |
|  10.22.111.192/26   | 255.255.255.192  | 10.22.111.192 - 10.22.111.255  | 10.22.111.193 - 10.22.111.254  |     62     |     -     |

<br>

### 🔗 IPv4 Address of the ISP Router Node
- **Address**: 87.5.127.93/30


---

## 💻 End Devices in the Simulation

Each building must contain at least:

- PC (floor 0)
- PC (floor 1)
- Laptop and/or Smartphone and/or Tablet
- Server (DMZ)
- VoIP Phone

The end devices must be connected to the correct VLANs by configuring the corresponding switch ports in access mode (`switchport mode access`) and assigning the correct VLAN to them (`switchport access vlan ...`).

Except for VoIP phones, all other end devices must have a static and manually defined IPv4 configuration, including the default gateway.

For VoIP phones, the model **7960** must be used. The corresponding port on the switch must also be configured in access mode (`switchport mode access`), however, the access VLAN must be deactivated (`no switchport access vlan`), and the voice VLAN must be used instead (`switchport voice vlan ...`).

The IPv4 configuration of the VoIP phones is out of scope for now and will be addressed in the next sprint.
<br>

- ### Routers and Static Routing

In each building, there must be a router. Use exclusively the model **2811**, as other models may not support VoIP in Packet Tracer, which will be necessary in the next sprint.

The router in each building will be responsible for forwarding IPv4 traffic between the local IPv4 networks (within the building) and the IPv4 networks of other buildings. Traffic to other buildings will be routed through the IPv4 backbone network, directed to the appropriate router.

The IPv4 addresses of the nodes used by each router in the backbone network are defined in the planning meeting. Along with the address blocks assigned to each building, this enables the construction of the static routing table in each router.

Each team member is responsible for creating the Packet Tracer simulation for one building. Each simulation will cover a single building but must include the campus backbone network. The **main cross-connect** and all **intermediate cross-connects** must be represented by a switch, and a **router (model 2811)** must be connected to each of them.

As each router is connected to **six different IPv4 networks**, a router with six network interfaces would be expected. However, just as a single connection in trunk mode between two switches can connect multiple VLANs, the same concept applies to the connection to a router. In the router, each VLAN will appear as a **logical network interface (subinterface)**.

Thus, to connect the router to these six networks, the best solution is to use **a single cable connection to a port configured in trunk mode on the switch**.

Regarding the configuration of the routers outside the building, it should cover only the connection to the backbone VLAN and the respective IP address. The complete configuration of the router for each building is the responsibility of the team member in charge of that building. 

---

## 🌍 Internet Connection

- Only Building 1 connects to the Internet via ISP router (IPv4: `87.5.127.93/30`) with DSL connection.

---