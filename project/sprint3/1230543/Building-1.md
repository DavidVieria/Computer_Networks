# 🏢 Building 1

### Detalhes de Configuração e Implementação

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## 🧩 Sub-tarefas

|  **Tarefa**  | **Descrição da tarefa**                                                                                        | **Status** |
|:------------:|----------------------------------------------------------------------------------------------------------------|:----------:|
| OSPF Routing | Configurar OSPF com área dedicada ao edifício e incluir a rota por omissão (default-information originate).    |     ✅      |
| HTTP Server  | Adicionar segundo servidor HTTP/HTTPS na DMZ com IP estático e página HTML que identifique o edifício.         |     ✅      |
|    DHCPv4    | Configurar DHCPv4 para todas as VLANs exceto DMZ e backbone; incluir a opção 150 para VoIP.                    |     ✅      |
|     VoIP     | Configurar serviço de VoIP com dois telefones IP modelo 7960 e VLAN de voz nos switches.                       |     ✅      |
|     DNS      | Criar domínio principal, configurar servidor DNS. Conhecer IPs dos servidores dos subdomínios (buildings 2-4). |     ✅      |
|     NAT      | Configurar NAT estático para redirecionar HTTP/HTTPS para o servidor DNS.                                      |     ✅      |
|   Firewall   | Configurar ACLs para implementar firewall estático.                                                            |     ✅      |

---


## 🔄 OSPF Dynamic Routing

**Configuração implementada:**
- **Área OSPF:** 1 (0.0.0.1)
- **Router-ID:** 1.1.1.1
- **Rota por omissão:** Inserida no OSPF via `default-information originate`
- **Conexão ISP:** 87.5.127.92/30 (anunciada na área 0)
- **Remoção:** Todas as rotas estáticas foram removidas, exceto a rota por omissão para o ISP

**Redes anunciadas no OSPF:**
- 10.22.98.0/26 (VLAN 362 - F0)
- 10.22.98.64/26 (VLAN 363 - F1)
- 10.22.98.128/25 (VLAN 364 - WiFi)
- 10.22.99.0/25 (VLAN 366 - VoIP)
- 10.22.99.128/25 (VLAN 365 - DMZ)
- 10.22.97.0/24 (VLAN 382 - Backbone - Área 0)
- 87.5.127.92/30 (Conexão ISP - Área 0)

---

## 🖥️ HTTP Server (Server 1)

**Servidor adicionado:** 10.22.99.131
- **Serviços ativos:** HTTP (porta 80) e HTTPS (porta 443)
- **Página HTML:** Identifica o Edifício 1 e o domínio rcomp-24-25-dd-g2
- **Configuração:** IP estático na DMZ

---

## 🏠 DHCPv4 Service

| DHCP Pool | Subnet       | Netmask         | Default Router | Excluded Addresses                         | DHCP Options            | VLAN |
|-----------|--------------|-----------------|----------------|--------------------------------------------|-------------------------|------|
| F0_B1     | 10.22.98.0   | 255.255.255.192 | 10.22.98.1     | 10.22.98.1 - 10.22.98.10                   | None                    | F0   |
| F1_B1     | 10.22.98.64  | 255.255.255.192 | 10.22.98.65    | 10.22.98.65 - 10.22.98.74                  | None                    | F1   |
| WIFI_B1   | 10.22.98.128 | 255.255.255.128 | 10.22.98.129   | 10.22.98.129 - 10.22.98.138                | None                    | WIFI |
| VOIP_B1   | 10.22.99.0   | 255.255.255.128 | 10.22.99.1     | 10.22.99.1 - 10.22.99.10, 10.22.99.100     | Option 150: 10.22.99.1  | VoIP |

**Configurações adicionais:**
- **Domain-name:** rcomp-24-25-dd-g2 (configurado em todas as pools)
- **DNS Server:** 10.22.99.130 (servidor DNS local)

---

## ☎️ VoIP Service

**Configuração implementada:**
- **Prefixo telefónico:** 1xxx
- **Números atribuídos:** 1001, 1002
- **TFTP Server:** 10.22.99.1 (IP do router na VLAN VoIP)
- **Telefones instalados:** 2x Cisco IP Phone 7960
- **MACs configurados:**
    - ephone 1: 0002.4A49.A2A8 (número 1001)
    - ephone 2: 00E0.8F6D.904E (número 1002)

**Configuração telephony-service:**
- **Max ephones:** 15
- **Max dn:** 15
- **IP source-address:** 10.22.99.1 port 2000
- **Auto assign:** 1 to 15

**Configuração dos switches:**
- **Access VLAN:** Desabilitada (`no switchport access vlan`)
- **Voice VLAN:** VLAN 366 (`switchport voice vlan 366`)

**Dial-peers para outros edifícios:**
- **Prefixo 2xxx → 10.22.102.1** (Building 2)
- **Prefixo 3xxx → 10.22.105.1** (Building 3)
- **Prefixo 4xxx → 10.22.109.1** (Building 4)

---

## 🌐 DNS Configuration

**Servidor DNS:** 10.22.99.130 (ns.rcomp-24-25-dd-g2)
**Domínio principal:** rcomp-24-25-dd-g2

### Base de Dados DNS

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


**Configuração dos clientes:**
- **Servidores (IP estático):** DNS configurado manualmente para 10.22.99.130
- **Clientes DHCP:** DNS configurado automaticamente via DHCP

---


## 🔀 NAT (Network Address Translation)

**Regras implementadas:**
```cisco
ip nat inside source static tcp 10.22.99.130 80 10.22.97.1 80
ip nat inside source static tcp 10.22.99.130 443 10.22.97.1 443
```

**Interfaces:**
- **DMZ (Fa0/0.365):** `ip nat inside`
- **Backbone (Fa0/0.382):** `ip nat outside`

**Resultado:** Pedidos HTTP/HTTPS recebidos na interface backbone (10.22.97.1) são redirecionados para o servidor DNS (10.22.99.130).

---

## 🔒 Static Firewall (ACLs)

### ACLs Implementadas

#### **INTERNET_ACL** (aplicada à VLAN 382 - Backbone - entrada)
**Objetivo:** Controlar tráfego vindo da internet/backbone

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

#### **WIFI_ACL** (aplicada à VLAN 364 - WiFi - entrada)
**Objetivo:** Restringir acesso da rede WiFi a recursos internos

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

#### **VOIP_ACL** (aplicada à VLAN 366 - VoIP - entrada)
**Objetivo:** Permitir tráfego VoIP e restringir acesso a outros recursos

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

#### **GROUND_FLOOR_ACL** (aplicada à VLAN 362 - F0 - entrada)
**Objetivo:** Controlar acesso do piso térreo

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

#### **FLOOR1_ACL** (aplicada à VLAN 363 - F1 - entrada)
**Objetivo:** Controlar acesso do primeiro andar

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

### Resumo da Política de Segurança

**Princípios aplicados:**
1. **Negação por padrão:** Todas as ACLs terminam com `deny ip any any`
2. **Proteção de infraestrutura:** IPs dos routers/gateways são protegidos
3. **Serviços essenciais:** DHCP, DNS, TFTP e OSPF são sempre permitidos
4. **Segmentação:** Cada VLAN tem controle específico baseado na sua função
5. **VoIP segregado:** VLAN VoIP tem regras específicas para telefonia
6. **DMZ protegida:** Acesso direto à DMZ é negado, apenas respostas são permitidas
7. **Controle de NAT:** Redirecionamento HTTP/HTTPS controlado via ACL

### 📊 Interfaces e VLANs Configuradas

| **Interface** | **VLAN** | **IP/Máscara**        | **Descrição**       | **ACL Aplicada**      |
|---------------|----------|-----------------------|---------------------|-----------------------|
| Fa0/0.362     | 362      | 10.22.98.1/26         | Ground Floor (F0)   | GROUND_FLOOR_ACL      |
| Fa0/0.363     | 363      | 10.22.98.65/26        | Floor 1 (F1)        | FLOOR1_ACL            |
| Fa0/0.364     | 364      | 10.22.98.129/25       | WiFi                | WIFI_ACL              |
| Fa0/0.365     | 365      | 10.22.99.129/25       | DMZ                 | -                     |
| Fa0/0.366     | 366      | 10.22.99.1/25         | VoIP                | VOIP_ACL              |
| Fa0/0.382     | 382      | 10.22.97.1/24         | Backbone            | INTERNET_ACL          |
| Fa0/1         | -        | 87.5.127.94/30        | ISP Connection      | -                     |

---