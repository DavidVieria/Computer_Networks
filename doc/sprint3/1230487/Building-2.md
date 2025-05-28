# 🏢 Building 2

### Detalhes de Configuração e Implementação

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

## 🧩 Sub-tarefas

|   **Tarefa**   | **Descrição da tarefa**                                                                                | **Status** |
|:--------------:|--------------------------------------------------------------------------------------------------------|:----------:|
|  OSPF Routing  | Configurar OSPF com área própria para o edifício.                                                      |     ✅      |
|  HTTP Server   | Adicionar segundo servidor HTTP/HTTPS na DMZ com IP estático e página HTML que identifique o edifício. |     ✅      |
|     DHCPv4     | Configurar DHCPv4 para todas as VLANs exceto DMZ e backbone; incluir a opção 150 para VoIP.            |     ✅      |
|      VoIP      | Configurar serviço de VoIP com dois telefones IP modelo 7960 e VLAN de voz nos switches.               |     ✅      |
|      DNS       | Criar subdomínio, configurar servidor DNS. Conhecer IP do servidor DNS de building 1.                  |     ✅      |
|      NAT       | Configurar NAT estático para redirecionar HTTP/HTTPS para o servidor DNS.                              |     ✅      |
|    Firewall    | Configurar ACLs para implementar firewall estático.                                                    |     ✅      |
| **Integração** | **Integração final de todas as simulações em campus.pkt.**                                             |     ✅      |

---


## 🔄 OSPF Dynamic Routing

**Configuração implementada:**
- **Área OSPF:** 2 (0.0.0.2)
- **Router-ID:** 2.2.2.2
- **Remoção:** Todas as rotas estáticas foram removidas

**Redes anunciadas no OSPF:**
- 10.22.100.0/24 (VLAN 369 - WiFi)
- 10.22.101.0/25 (VLAN 367 - F0)
- 10.22.101.128/25 (VLAN 368 - F1)
- 10.22.102.0/25 (VLAN 371 - VoIP)
- 10.22.102.128/26 (VLAN 370 - DMZ)
- 10.22.97.0/24 (VLAN 382 - Backbone - Área 0)

---

## 🖥️ HTTP Server (Server 1)

**Servidor adicionado:** 10.22.102.131
- **Serviços ativos:** HTTP (porta 80) e HTTPS (porta 443)
- **Página HTML:** Identifica o Edifício 2 e o aluno responsável por ele
- **Configuração:** IP estático na DMZ

---

## 🏠 DHCPv4 Service

| DHCP Pool | Subnet        | Netmask         | Default Router | Excluded Addresses                        | DHCP Options              | VLAN |
|-----------|---------------|-----------------|----------------|-------------------------------------------|---------------------------|------|
| WIFI_B2   | 10.22.100.0   | 255.255.255.0   | 10.22.100.1    | 10.22.100.1 - 10.22.100.10                | None                      | WIFI |
| F0_B2     | 10.22.101.0   | 255.255.255.128 | 10.22.101.1    | 10.22.101.1 - 10.22.101.10                | None                      | F0   |
| F1_B2     | 10.22.101.128 | 255.255.255.128 | 10.22.101.129  | 10.22.101.129 - 10.22.101.139             | None                      | F1   |
| VOIP_B2   | 10.22.102.0   | 255.255.255.128 | 10.22.102.1    | 10.22.102.1 - 10.22.102.10, 10.22.102.100 | Option 150: 10.22.102.1   | VoIP |

**Configurações adicionais:**
- **Domain-name:** building-2.rcomp-24-25-dd-g2 (configurado em todas as pools)
- **DNS Server:** 10.22.102.130 (servidor DNS local)

---

## ☎️ VoIP Service

**Configuração implementada:**
- **Prefixo telefónico:** 2xxx
- **Números atribuídos:** 2001, 2002
- **TFTP Server:** 10.22.102.1 (IP do router na VLAN VoIP)
- **Telefones instalados:** 2x Cisco IP Phone 7960
- **MACs configurados:**
    - ephone 1: 0040.0BD3.9911 (número 2001)
    - ephone 2: 00D0.584E.A81E (número 2002)

**Configuração telephony-service:**
- **Max ephones:** 20
- **Max dn:** 20
- **IP source-address:** 10.22.102.1 port 2000
- **Auto assign:** 1 to 20

**Configuração dos switches:**
- **Access VLAN:** Desabilitada (`no switchport access vlan`)
- **Voice VLAN:** VLAN 371 (`switchport voice vlan 371`)

**Dial-peers para outros edifícios:**
- **Prefixo 1xxx → 10.22.99.1** (Building 1)
- **Prefixo 3xxx → 10.22.105.1** (Building 3)
- **Prefixo 4xxx → 10.22.109.1** (Building 4)

---

## 🌐 DNS Configuration

**Servidor DNS:** 10.22.102.130 (ns.building-2.rcomp-24-25-dd-g2)
**Subdomínio:** building-2.rcomp-24-25-dd-g2

### Base de Dados DNS

| No. |                 Name                 |   Type   |                Detail                |
|:---:|:------------------------------------:|:--------:|:------------------------------------:|
|  0  |     building-2.rcomp-24-25-dd-g2     |    NS    |   ns.building-2.rcomp-24-25-dd-g2    |
|  1  |   dns.building-2.rcomp-24-25-dd-g2   |  CNAME   |   ns.building-2.rcomp-24-25-dd-g2    |
|  2  |   ns.building-2.rcomp-24-25-dd-g2    | A Record |            10.22.102.130             |
|  3  |         ns.rcomp-24-25-dd-g2         | A Record |             10.22.99.130             |
|  4  |          rcomp-24-25-dd-g2           |    NS    |         ns.rcomp-24-25-dd-g2         |
|  5  | server1.building-2.rcomp-24-25-dd-g2 | A Record |            10.22.102.131             |
|  6  |   web.building-2.rcomp-24-25-dd-g2   |  CNAME   | server1.building-2.rcomp-24-25-dd-g2 |
|  7  |   www.building-2.rcomp-24-25-dd-g2   |  CNAME   | server1.building-2.rcomp-24-25-dd-g2 |

<br>

![DNSDatabase.png](DNS_Database_2.png)


**Configuração dos clientes:**
- **Servidores (IP estático):** DNS configurado manualmente para 10.22.102.130
- **Clientes DHCP:** DNS configurado automaticamente via DHCP

---

## 🔀 NAT (Network Address Translation)

**Regras implementadas:**
```cisco
ip nat inside source static tcp 10.22.102.130 80 10.22.97.3 80
ip nat inside source static tcp 10.22.102.130 443 10.22.97.3 443
```

**Interfaces:**
- **DMZ (Fa0/0.370):** `ip nat inside`
- **Backbone (Fa0/0.382):** `ip nat outside`

**Resultado:** Pedidos HTTP/HTTPS recebidos na interface backbone (10.22.97.3) são redirecionados para o servidor DNS (10.22.102.130).

---

## 🔒 Static Firewall (ACLs)

### ACLs Implementadas

#### **INTERNET_ACL_B2** (aplicada à VLAN 382 - Backbone - entrada)
**Objetivo:** Controlar tráfego vindo da internet/backbone

```cisco
ip access-list extended INTERNET_ACL_B2
 permit tcp any host 10.22.102.1 eq 2000
 permit udp any host 10.22.102.1 eq 5060
 permit tcp any host 10.22.102.1 eq 5060
 permit ip any 10.22.102.0 0.0.0.127
 permit ip any 10.22.100.0 0.0.0.255
 permit ip any 10.22.101.0 0.0.0.127
 permit ip any 10.22.101.128 0.0.0.127
 permit icmp any any
 permit tcp any host 10.22.97.3 eq www
 permit tcp any host 10.22.97.3 eq 443
 permit tcp any host 10.22.97.3 eq domain
 permit udp any host 10.22.97.3 eq domain
 permit ospf any any
 permit ip any any
 deny ip any any
```

#### **WIFI_ACL_B2** (aplicada à VLAN 369 - WiFi - entrada)
**Objetivo:** Restringir acesso da rede WiFi a recursos internos

```cisco
ip access-list extended WIFI_ACL_B2
 deny ip any host 10.22.101.1
 deny ip any host 10.22.101.129
 deny ip any host 10.22.100.1
 deny ip any host 10.22.102.129
 deny ip any host 10.22.102.1
 deny ip any host 10.22.97.3
 permit icmp any any
 permit tcp any host 10.22.102.130 eq www
 permit tcp any host 10.22.102.130 eq 443
 permit udp any host 10.22.102.130 eq domain
 permit tcp any host 10.22.102.130 eq domain
 deny ip any 10.22.102.128 0.0.0.63
 permit ip 10.22.102.128 0.0.0.63 any
 permit ip 10.22.101.128 0.0.0.127 any
 permit udp any eq bootpc any eq bootps
 permit udp any eq tftp any eq tftp
 permit ospf any any
 deny ip any any
```

#### **VOIP_ACL_B2** (aplicada à VLAN 371 - VoIP - entrada)
**Objetivo:** Permitir tráfego VoIP e restringir acesso a outros recursos

```cisco
ip access-list extended VOIP_ACL_B2
 permit udp any host 10.22.102.1 eq bootps
 permit udp any host 10.22.102.1 eq tftp
 permit tcp any host 10.22.102.1 eq 2000
 permit udp any host 10.22.102.1 eq 5060
 permit tcp any host 10.22.102.1 eq 5060
 deny ip any host 10.22.101.1
 deny ip any host 10.22.101.129
 deny ip any host 10.22.100.1
 deny ip any host 10.22.102.129
 deny ip any host 10.22.102.1
 deny ip any host 10.22.97.3
 permit icmp any any
 permit tcp any host 10.22.102.130 eq www
 permit tcp any host 10.22.102.130 eq 443
 permit udp any host 10.22.102.130 eq domain
 permit tcp any host 10.22.102.130 eq domain
 deny ip any 10.22.102.128 0.0.0.63
 permit ip 10.22.102.128 0.0.0.63 any
 permit ip 10.22.102.0 0.0.0.127 any
 permit udp any eq bootpc any eq bootps
 permit udp any eq tftp any eq tftp
 permit ospf any any
 deny ip any any
```

#### **GROUND_FLOOR_ACL_B2** (aplicada à VLAN 367 - F0 - entrada)
**Objetivo:** Controlar acesso do piso térreo

```cisco
ip access-list extended GROUND_FLOOR_ACL_B2
 deny ip any host 10.22.101.1
 deny ip any host 10.22.101.129
 deny ip any host 10.22.100.1
 deny ip any host 10.22.102.129
 deny ip any host 10.22.102.1
 deny ip any host 10.22.97.3
 permit icmp any any
 permit tcp any host 10.22.102.130 eq www
 permit tcp any host 10.22.102.130 eq 443
 permit udp any host 10.22.102.130 eq domain
 permit tcp any host 10.22.102.130 eq domain
 deny ip any 10.22.102.128 0.0.0.63
 permit ip 10.22.102.128 0.0.0.63 any
 permit ip 10.22.101.0 0.0.0.127 any
 permit udp any eq bootpc any eq bootps
 permit udp any eq tftp any eq tftp
 permit ospf any any
 deny ip any any
```

#### **FLOOR1_ACL_B2** (aplicada à VLAN 368 - F1 - entrada)
**Objetivo:** Controlar acesso do primeiro andar

```cisco
ip access-list extended FLOOR1_ACL_B2
 deny ip any host 10.22.101.1
 deny ip any host 10.22.101.129
 deny ip any host 10.22.100.1
 deny ip any host 10.22.102.129
 deny ip any host 10.22.102.1
 deny ip any host 10.22.97.3
 permit icmp any any
 permit tcp any host 10.22.102.130 eq www
 permit tcp any host 10.22.102.130 eq 443
 permit udp any host 10.22.102.130 eq domain
 permit tcp any host 10.22.102.130 eq domain
 deny ip any 10.22.102.128 0.0.0.63
 permit ip 10.22.102.128 0.0.0.63 any
 permit ip 10.22.101.128 0.0.0.127 any
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



### 📊 Interfaces e VLANs Configuradas

| **Interface** | **VLAN** | **IP/Máscara**        | **Descrição**       | **ACL Aplicada**      |
|---------------|----------|-----------------------|---------------------|-----------------------|
| Fa0/0.367     | 367      | 10.22.101.1/25        | Ground Floor (F0)   | GROUND_FLOOR_ACL_B2   |
| Fa0/0.368     | 368      | 10.22.101.129/25      | Floor 1 (F1)        | FLOOR1_ACL_B2         |
| Fa0/0.369     | 369      | 10.22.100.1/24        | WiFi                | WIFI_ACL_B2           |
| Fa0/0.370     | 370      | 10.22.102.129/26      | DMZ                 | -                     |
| Fa0/0.371     | 371      | 10.22.102.1/25        | VoIP                | VOIP_ACL_B2           |
| Fa0/0.382     | 382      | 10.22.97.3/24         | Backbone            | INTERNET_ACL_B2       |


---