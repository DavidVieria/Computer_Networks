# 🏢 Building 1

### Configuration and Implementation Details

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## 🧩 Subtasks

|   **Task**   | **Task Description**                                                                                                 | **Status** |
|:------------:|----------------------------------------------------------------------------------------------------------------------|:----------:|
| OSPF Routing | Configure OSPF with a dedicated area for the building and include the default route (default-information originate). |     ✅      |
| HTTP Server  | Add a second HTTP/HTTPS server in the DMZ with a static IP and an HTML page identifying the building.                |     ✅      |
|    DHCPv4    | Configure DHCPv4 for all VLANs except DMZ and backbone; include option 150 for VoIP.                                 |     ✅      |
|     VoIP     | Configure VoIP service with two Cisco 7960 IP phones and voice VLANs on the switches.                                |     ✅      |
|     DNS      | Create the main domain, configure the DNS server. Know the IPs of the subdomain servers (buildings 2-4).             |     ✅      |
|     NAT      | Configure static NAT to redirect HTTP/HTTPS to the DNS server.                                                       |     ✅      |
|   Firewall   | Configure ACLs to implement a static firewall.                                                                       |     ✅      |

---


## 🔄 OSPF Dynamic Routing

**Implemented configuration:**
- **OSPF Area:** 1 (0.0.0.1)
- **Router-ID:** 1.1.1.1
- **Default route:** Inserted into OSPF via `default-information originate`
- **ISP connection:** 87.5.127.92/30 (advertised in area 0)
- **Removal:** All static routes were removed except the default route to the ISP

**Networks advertised in OSPF:**
- 10.22.98.0/26 (VLAN 362 - F0)
- 10.22.98.64/26 (VLAN 363 - F1)
- 10.22.98.128/25 (VLAN 364 - WiFi)
- 10.22.99.0/25 (VLAN 366 - VoIP)
- 10.22.99.128/25 (VLAN 365 - DMZ)
- 10.22.97.0/24 (VLAN 382 - Backbone - Área 0)
- 87.5.127.92/30 (Conexão ISP - Área 0)

---

## 🖥️ HTTP Server (Server 1)

**Server added:** 10.22.99.131
- **Active services:** HTTP (port 80) and HTTPS (port 443)
- **HTML page:** Identifies Building 1 and the domain rcomp-24-25-dd-g2
- **Configuration:** Static IP in the DMZ

---

## 🏠 DHCPv4 Service

| DHCP Pool | Subnet       | Netmask         | Default Router | Excluded Addresses                         | DHCP Options            | VLAN |
|-----------|--------------|-----------------|----------------|--------------------------------------------|-------------------------|------|
| F0_B1     | 10.22.98.0   | 255.255.255.192 | 10.22.98.1     | 10.22.98.1 - 10.22.98.10                   | None                    | F0   |
| F1_B1     | 10.22.98.64  | 255.255.255.192 | 10.22.98.65    | 10.22.98.65 - 10.22.98.74                  | None                    | F1   |
| WIFI_B1   | 10.22.98.128 | 255.255.255.128 | 10.22.98.129   | 10.22.98.129 - 10.22.98.138                | None                    | WIFI |
| VOIP_B1   | 10.22.99.0   | 255.255.255.128 | 10.22.99.1     | 10.22.99.1 - 10.22.99.10, 10.22.99.100     | Option 150: 10.22.99.1  | VoIP |

**Additional configurations:**
- **Domain-name:** rcomp-24-25-dd-g2 (configured in all pools)
- **DNS Server:** 10.22.99.130 (local DNS server)

---

## ☎️ VoIP Service

**Configuration implemented:**
- **Phone prefix:** 1xxx
- **Assigned numbers:** 1001, 1002
- **TFTP Server:** 10.22.99.1 (Router IP in the VoIP VLAN)
- **Phones installed:** 2x Cisco IP Phone 7960
- **MACs configured:**
    - ephone 1: 0002.4A49.A2A8 (number 1001)
    - ephone 2: 00E0.8F6D.904E (number 1002)

**Telephony-service configuration:**
- **Max ephones:** 15
- **Max dn:** 15
- **IP source-address:** 10.22.99.1 port 2000
- **Auto assign:** 1 to 15

**Switch configurations:**
- **Access VLAN:** Disabled (`no switchport access vlan`)
- **Voice VLAN:** VLAN 366 (`switchport voice vlan 366`)

**Dial-peers for other buildings:**
- **Prefix 2xxx → 10.22.102.1** (Building 2)
- **Prefix 3xxx → 10.22.105.1** (Building 3)
- **Prefix 4xxx → 10.22.109.1** (Building 4)

---

## 🌐 DNS Configuration

**DNS Server:** 10.22.99.130 (ns.rcomp-24-25-dd-g2)
**Main domain:** rcomp-24-25-dd-g2

### DNS Database

| No. |                 Name                  |   Type   |               Detail               |
|:---:|:-------------------------------------:|:--------:|:----------------------------------:|
|  0  |     building-2.rcomp-24-25-dd-g2      |    NS    |  ns.building-2.rcomp-24-25-dd-g2   |
|  1  |     building-3.rcomp-24-25-dd-g2      |    NS    |  ns.building-3.rcomp-24-25-dd-g2   |
|  2  |     building-4.rcomp-24-25-dd-g2      |    NS    |  ns.building-4.rcomp-24-25-dd-g2   |
|  3  |         dns.rcomp-24-25-dd-g2         |  CNAME   |        ns.rcomp-24-25-dd-g2        |
|  4  |    ns.building-2.rcomp-24-25-dd-g2    | A Record |           10.22.102.130            |
|  5  |    ns.building-3.rcomp-24-25-dd-g2    | A Record |           10.22.107.130            |
|  6  |    ns.building-4.rcomp-24-25-dd-g2    | A Record |           10.22.111.130            |
|  7  |         ns.rcomp-24-25-dd-g2          | A Record |            10.22.99.130            |
|  8  |           rcomp-24-25-dd-g2           |    NS    |        ns.rcomp-24-25-dd-g2        |
|  9  |       server1.rcomp-24-25-dd-g2       | A Record |            10.22.99.131            |
| 10  |         web.rcomp-24-25-dd-g2         |  CNAME   |     server1.rcomp-24-25-dd-g2      |
| 11  |         www.rcomp-24-25-dd-g2         |  CNAME   |     server1.rcomp-24-25-dd-g2      |

<br>

![DNSDatabase.png](DNS_Database_1.png)


**Client configuration:**
- **Servers (static IP):** DNS manually configured to 10.22.99.130
- **DHCP clients:** DNS automatically configured via DHCP

---


## 🔀 NAT (Network Address Translation)

**Implemented rules:**
```cisco
ip nat inside source static tcp 10.22.99.130 80 10.22.97.1 80
ip nat inside source static tcp 10.22.99.130 443 10.22.97.1 443
```

**Interfaces:**
- **DMZ (Fa0/0.365):** `ip nat inside`
- **Backbone (Fa0/0.382):** `ip nat outside`

**Result:** HTTP/HTTPS requests received on the backbone interface (10.22.97.1) are redirected to the DNS server (10.22.99.130).

---

## 🔒 Static Firewall (ACLs)

### Implemented ACLs

#### **INTERNET_ACL** (applied to VLAN 382 - Backbone - inbound)
**Objective:** Control traffic coming from the internet/backbone

```cisco
ip access-list extended INTERNET_ACL
 permit tcp any host 10.22.99.1 eq 2000
 permit udp any host 10.22.99.1 eq 5060
 permit tcp any host 10.22.99.1 eq 5060
 permit ip any 10.22.99.0 0.0.0.127
 permit ip any 10.22.98.0 0.0.0.255
 permit icmp any any
 permit tcp any host 10.22.97.1 eq www
 permit tcp any host 10.22.97.1 eq 443
 permit tcp any host 10.22.97.1 eq domain
 permit udp any host 10.22.97.1 eq domain
 permit ospf any any
 permit ip any any
 deny ip any any
```

#### **WIFI_ACL** (applied to VLAN 364 - WiFi - inbound)
**Objective:** Restrict access from the WiFi network to internal resources

```cisco
ip access-list extended WIFI_ACL
 deny ip any host 10.22.98.1
 deny ip any host 10.22.98.65
 deny ip any host 10.22.99.1
 deny ip any host 10.22.98.129
 deny ip any host 10.22.99.129
 deny ip any host 10.22.97.1
 permit icmp any any
 permit tcp any host 10.22.99.130 eq www
 permit tcp any host 10.22.99.130 eq 443
 permit udp any host 10.22.99.130 eq domain
 permit tcp any host 10.22.99.130 eq domain
 deny ip any 10.22.99.128 0.0.0.127
 permit ip 10.22.99.128 0.0.0.127 any
 permit ip 10.22.98.128 0.0.0.127 any
 permit udp any eq bootpc any eq bootps
 permit udp any eq tftp any eq tftp
 permit ospf any any
 deny ip any any
```

#### **VOIP_ACL** (applied to VLAN 366 - VoIP - inbound)
**Objective:** Allow VoIP traffic and restrict access to other resources

```cisco
ip access-list extended VOIP_ACL
 permit udp any host 10.22.99.1 eq bootps
 permit udp any host 10.22.99.1 eq tftp
 permit tcp any host 10.22.99.1 eq 2000
 permit udp any host 10.22.99.1 eq 5060
 permit tcp any host 10.22.99.1 eq 5060
 deny ip any host 10.22.98.1
 deny ip any host 10.22.98.65
 deny ip any host 10.22.98.129
 deny ip any host 10.22.99.129
 deny ip any host 10.22.97.1
 permit icmp any any
 permit tcp any host 10.22.99.130 eq www
 permit tcp any host 10.22.99.130 eq 443
 permit udp any host 10.22.99.130 eq domain
 permit tcp any host 10.22.99.130 eq domain
 deny ip any 10.22.99.128 0.0.0.127
 permit ip 10.22.99.128 0.0.0.127 any
 permit ip 10.22.99.0 0.0.0.127 any
 permit udp any eq bootpc any eq bootps
 permit udp any eq tftp any eq tftp
 permit ospf any any
 deny ip any any
```

#### **GROUND_FLOOR_ACL** (applied to VLAN 362 - F0 - inbound)
**Objective:** Control access from the ground floor

```cisco
ip access-list extended GROUND_FLOOR_ACL
 deny ip any host 10.22.98.1
 deny ip any host 10.22.98.65
 deny ip any host 10.22.99.1
 deny ip any host 10.22.98.129
 deny ip any host 10.22.99.129
 deny ip any host 10.22.97.1
 permit icmp any any
 permit tcp any host 10.22.99.130 eq www
 permit tcp any host 10.22.99.130 eq 443
 permit udp any host 10.22.99.130 eq domain
 permit tcp any host 10.22.99.130 eq domain
 deny ip any 10.22.99.128 0.0.0.127
 permit ip 10.22.99.128 0.0.0.127 any
 permit ip 10.22.98.0 0.0.0.63 any
 permit udp any eq bootpc any eq bootps
 permit udp any eq tftp any eq tftp
 permit ospf any any
 deny ip any any
```

#### **FLOOR1_ACL** (applied to VLAN 363 - F1 - inbound)
**Objective:** Control access from the first floor

```cisco
ip access-list extended FLOOR1_ACL
 deny ip any host 10.22.98.1
 deny ip any host 10.22.98.65
 deny ip any host 10.22.99.1
 deny ip any host 10.22.98.129
 deny ip any host 10.22.99.129
 deny ip any host 10.22.97.1
 permit icmp any any
 permit tcp any host 10.22.99.130 eq www
 permit tcp any host 10.22.99.130 eq 443
 permit udp any host 10.22.99.130 eq domain
 permit tcp any host 10.22.99.130 eq domain
 deny ip any 10.22.99.128 0.0.0.127
 permit ip 10.22.99.128 0.0.0.127 any
 permit ip 10.22.98.64 0.0.0.63 any
 permit udp any eq bootpc any eq bootps
 permit udp any eq tftp any eq tftp
 permit ospf any any
 deny ip any any
```

### Security Policy Summary

**Applied principles:**
1. **Default deny:** All ACLs end with `deny ip any any`
2. **Infrastructure protection:** Router/gateway IPs are protected
3. **Essential services:** DHCP, DNS, TFTP, and OSPF are always allowed
4. **Segmentation:** Each VLAN has specific control based on its function
5. **VoIP segregation:** The VoIP VLAN has specific rules for telephony
6. **DMZ protection:** Direct access to the DMZ is denied, only responses are allowed
7. **NAT control:** HTTP/HTTPS redirection is controlled via ACL

### 📊 Configured Interfaces and VLANs

| **Interface** | **VLAN** | **IP/Mask**     | **Description**   | **Applied ACL**  |
|---------------|----------|-----------------|-------------------|------------------|
| Fa0/0.362     | 362      | 10.22.98.1/26   | Ground Floor (F0) | GROUND_FLOOR_ACL |
| Fa0/0.363     | 363      | 10.22.98.65/26  | Floor 1 (F1)      | FLOOR1_ACL       |
| Fa0/0.364     | 364      | 10.22.98.129/25 | WiFi              | WIFI_ACL         |
| Fa0/0.365     | 365      | 10.22.99.129/25 | DMZ               | -                |
| Fa0/0.366     | 366      | 10.22.99.1/25   | VoIP              | VOIP_ACL         |
| Fa0/0.382     | 382      | 10.22.97.1/24   | Backbone          | INTERNET_ACL     |
| Fa0/1         | -        | 87.5.127.94/30  | ISP Connection    | -                |

---