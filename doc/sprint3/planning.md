# 📚 Planning

## 👨‍💻 Alunos

| **Nome**               | **Building** |
|------------------------|:------------:|
| Igor (1230543)         |      1       |
| David (1230487)        |      2       |
| Rafael (1230544)       |      3       |
| Daniel (1231046)       |      4       |

---

## 📌 Atribuição de Tarefas

| **Tarefa** | **Descrição da tarefa**                                                                                                                                                                                                                                                     |  **Aluno**  |
|:----------:|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------:|
|  **3.1**   | Atualizar a simulação Packet Tracer (building1.pkt) de camada 3 do sprint anterior, para incluir as funcionalidades descritas neste sprint para o edifício um.                                                                                                              | **1230543** |
|  **3.2**   | Atualizar a simulação Packet Tracer (building2.pkt) de camada 3 do sprint anterior, para incluir as funcionalidades descritas neste sprint para o edifício dois. Integração final das simulações Packet Tracer de cada membro num único ficheiro de simulação (campus.pkt). | **1230487** |
|  **3.3**   | Atualizar a simulação Packet Tracer (building3.pkt) de camada 3 do sprint anterior, para incluir as funcionalidades descritas neste sprint para o edifício três.                                                                                                            | **1230544** |
|  **3.4**   | Atualizar a simulação Packet Tracer (building4.pkt) de camada 3 do sprint anterior, para incluir as funcionalidades descritas neste sprint para o edifício quatro.                                                                                                          | **1231046** |

---

## 🧩 Subtarefas por Edifício

> Cada edifício segue um plano muito semelhante. Para maior clareza, as subtarefas estão organizadas em secções e detalhadas no conteúdo completo abaixo.

- ### 🏢 Building 1

|  **Tarefa**  | **Descrição da tarefa**                                                                                        |
|:------------:|----------------------------------------------------------------------------------------------------------------|
| OSPF Routing | Configurar OSPF com área dedicada ao edifício e incluir a rota por omissão (default-information originate).    |
| HTTP Server  | Adicionar segundo servidor HTTP/HTTPS na DMZ com IP estático e página HTML que identifique o edifício.         |
|    DHCPv4    | Configurar DHCPv4 para todas as VLANs exceto DMZ e backbone; incluir a opção 150 para VoIP.                    |
|     VoIP     | Configurar serviço de VoIP com dois telefones IP modelo 7960 e VLAN de voz nos switches.                       |
|     DNS      | Criar domínio principal, configurar servidor DNS. Conhecer IPs dos servidores dos subdomínios (buildings 2-4). |
|   Firewall   | Configurar firewall para bloquear tráfego indesejado.                                                          |

<br>

- ### 🏢 Building 2

|  **Tarefa**  | **Descrição da tarefa**                                                                                |
|:------------:|--------------------------------------------------------------------------------------------------------|
| OSPF Routing | Configurar OSPF com área própria para o edifício.                                                      |
| HTTP Server  | Adicionar segundo servidor HTTP/HTTPS na DMZ com IP estático e página HTML que identifique o edifício. |
|    DHCPv4    | Configurar DHCPv4 para todas as VLANs exceto DMZ e backbone; incluir a opção 150 para VoIP.            |
|     VoIP     | Configurar serviço de VoIP com dois telefones IP modelo 7960 e VLAN de voz nos switches.               |
|     DNS      | Criar subdomínio, configurar servidor DNS. Conhecer IP do servidor DNS de building 1.                  |
|   Firewall   | Configurar firewall para bloquear tráfego indesejado.                                                  |

<br>

- ### 🏢 Building 3

|  **Tarefa**  | **Descrição da tarefa**                                                                                |
|:------------:|--------------------------------------------------------------------------------------------------------|
| OSPF Routing | Configurar OSPF com área própria para o edifício.                                                      |
| HTTP Server  | Adicionar segundo servidor HTTP/HTTPS na DMZ com IP estático e página HTML que identifique o edifício. |
|    DHCPv4    | Configurar DHCPv4 para todas as VLANs exceto DMZ e backbone; incluir a opção 150 para VoIP.            |
|     VoIP     | Configurar serviço de VoIP com dois telefones IP modelo 7960 e VLAN de voz nos switches.               |
|     DNS      | Criar subdomínio, configurar servidor DNS. Conhecer IP do servidor DNS de building 1.                  |
|   Firewall   | Configurar firewall para bloquear tráfego indesejado.                                                  |

<br>

- ### 🏢 Building 4

|  **Tarefa**  | **Descrição da tarefa**                                                                                |
|:------------:|--------------------------------------------------------------------------------------------------------|
| OSPF Routing | Configurar OSPF com área própria para o edifício.                                                      |
| HTTP Server  | Adicionar segundo servidor HTTP/HTTPS na DMZ com IP estático e página HTML que identifique o edifício. |
|    DHCPv4    | Configurar DHCPv4 para todas as VLANs exceto DMZ e backbone; incluir a opção 150 para VoIP.            |
|     VoIP     | Configurar serviço de VoIP com dois telefones IP modelo 7960 e VLAN de voz nos switches.               |
|     DNS      | Criar subdomínio, configurar servidor DNS. Conhecer IP do servidor DNS de building 1.                  |
|   Firewall   | Configurar firewall para bloquear tráfego indesejado.                                                  |

---

## ⚙️ Decisões Técnicas

- **Packet Tracer:**
    - versão 8.2.2


- **Domínio VTP:**
    - `r2425ddg2`


- **Nomenclatura dos dispositivos:**
    - `Building_Device_Floor` (ex: `B2_PC_F0`)
    - `Building_Device_Number` (ex: `B2_Laptop_1`)


- **VLANs ID:**
    - 362 – 383


- **Modelo de router:**
    - 2811

---

## 🗂️ Base de Dados de VLANs


> Tabela com 21 VLANs dos edifícios + Backbone (ID 362 a 382) definidos, com nomes e descrições para cada tipo de tráfego:


| VLAN ID | nome VLAN       | descrição VLAN                                                |
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

## 🏗️ Endereços IP das Interfaces dos Routers na Rede Backbone do Campus (VLAN 382)

Para assegurar a conectividade entre os edifícios, foi estabelecido que cada router recebesse um endereço IP 
na VLAN 382 (Backbone). Estes endereços suportam a comunicação entre routers e o encaminhamento de tráfego entre as diferentes áreas OSPF.


| Edifício   | Router | Endereço IP na VLAN 382 |
|------------|--------|-------------------------|
| Edifício 1 | R1     | 10.22.97.1              |
| Edifício 2 | R2     | 10.22.97.3              |
| Edifício 3 | R3     | 10.22.97.4              |
| Edifício 4 | R4     | 10.22.97.5              |

---


## 🏠 Definição do Domínio OSPF no Campus


### Definir o Domínio OSPF (Autonomous System):

Tal como foi pedido no enunciado deste sprint, a nova infraestrutura funcionará como um único 
domínio OSPF, considerado um único sistema autónomo pelos restantes protocolos de encaminhamento.


### Tabela: Definição das Áreas OSPF no Campus

Conforme estabelecido na reunião de planeamento, as áreas OSPF foram distribuídas da seguinte forma:

| Edifício       | Função na Rede OSPF         | ID da Área OSPF (Decimal) | ID da Área OSPF (Ponto-decimal) |
|----------------|-----------------------------|---------------------------|---------------------------------|
| **Backbone**   | Área Principal (*Backbone*) | 0                         | 0.0.0.0                         |
| **Edifício 1** | Área de Rede Local          | 1                         | 0.0.0.1                         |
| **Edifício 2** | Área de Rede Local          | 2                         | 0.0.0.2                         |
| **Edifício 3** | Área de Rede Local          | 3                         | 0.0.0.3                         |
| **Edifício 4** | Área de Rede Local          | 4                         | 0.0.0.4                         |


### Definição dos Router-IDs OSPF do Campus

| **Edifício**              | **Router-ID (IPv4)** |
|---------------------------|----------------------|
| **Edifício 1 (Backbone)** | 1.1.1.1              |
| **Edifício 2**            | 2.2.2.2              |
| **Edifício 3**            | 3.3.3.3              |
| **Edifício 4**            | 4.4.4.4              |

**Nota:** O router do Edifício 1 introduzirá a rota por omissão 
no OSPF (comando `default-information originate`).


### Configuração de Áreas OSPF e Endereços IPv4 por Edifício

| Edifício       | Rede / Interface             | Endereço de Rede | Netmask         | Wildcard Mask   | Área OSPF |
|----------------|------------------------------|------------------|-----------------|-----------------|-----------|
| **Backbone**   | Backbone entre routers       | 10.22.97.0       | 255.255.255.0   | 0.0.0.255       | 0         |
|                | Ligação à Internet           | 87.5.127.92      | 255.255.255.252 | 0.0.0.3         | 0         |
| **Edifício 1** | F0 (VLAN 362)                | 10.22.98.0       | 255.255.255.192 | 0.0.0.63        | 1         |
|                | F1 (VLAN 363)                | 10.22.98.64      | 255.255.255.192 | 0.0.0.63        | 1         |
|                | WIFI (VLAN 364)              | 10.22.98.128     | 255.255.255.128 | 0.0.0.127       | 1         |
|                | VoIP (VLAN 366)              | 10.22.99.0       | 255.255.255.128 | 0.0.0.127       | 1         |
|                | DMZ (VLAN 365)               | 10.22.99.128     | 255.255.255.128 | 0.0.0.127       | 1         |
| **Edifício 2** | WIFI (VLAN 369)              | 10.22.100.0      | 255.255.255.0   | 0.0.0.255       | 2         |
|                | F0 (VLAN 367)                | 10.22.101.0      | 255.255.255.128 | 0.0.0.127       | 2         |
|                | F1 (VLAN 368)                | 10.22.101.128    | 255.255.255.128 | 0.0.0.127       | 2         |
|                | VoIP (VLAN 371)              | 10.22.102.0      | 255.255.255.128 | 0.0.0.127       | 2         |
|                | DMZ (VLAN 370)               | 10.22.102.128    | 255.255.255.192 | 0.0.0.63        | 2         |
| **Edifício 3** | WIFI (VLAN 374)              | 10.22.104.0      | 255.255.255.0   | 0.0.0.255       | 3         |
|                | VoIP (VLAN 376)              | 10.22.105.0      | 255.255.255.0   | 0.0.0.255       | 3         |
|                | F1 (VLAN 373)                | 10.22.106.0      | 255.255.255.0   | 0.0.0.255       | 3         |
|                | F0 (VLAN 372)                | 10.22.107.0      | 255.255.255.128 | 0.0.0.127       | 3         |
|                | DMZ (VLAN 375)               | 10.22.107.128    | 255.255.255.192 | 0.0.0.63        | 3         |
| **Edifício 4** | WIFI (VLAN 379)              | 10.22.108.0      | 255.255.255.0   | 0.0.0.255       | 4         |
|                | VoIP (VLAN 381)              | 10.22.109.0      | 255.255.255.0   | 0.0.0.255       | 4         |
|                | F1 (VLAN 378)                | 10.22.110.0      | 255.255.255.0   | 0.0.0.255       | 4         |
|                | F0 (VLAN 377)                | 10.22.111.0      | 255.255.255.128 | 0.0.0.127       | 4         |
|                | DMZ (VLAN 380)               | 10.22.111.128    | 255.255.255.192 | 0.0.0.63        | 4         |

---


## 🖥️ DHCPv4 Service


### 🏢 Configuração DHCP - Building 1

| DHCP Pool | Subnet       | Netmask         | Default Router | Excluded Addresses                         | DHCP Options            | VLAN |
|-----------|--------------|-----------------|----------------|--------------------------------------------|-------------------------|------|
| F0_B1     | 10.22.98.0   | 255.255.255.192 | 10.22.98.1     | 10.22.98.1 - 10.22.98.10                   | None                    | F0   |
| F1_B1     | 10.22.98.64  | 255.255.255.192 | 10.22.98.65    | 10.22.98.65 - 10.22.98.74                  | None                    | F1   |
| WIFI_B1   | 10.22.98.128 | 255.255.255.128 | 10.22.98.129   | 10.22.98.129 - 10.22.98.138                | None                    | WIFI |
| VOIP_B1   | 10.22.99.0   | 255.255.255.128 | 10.22.99.1     | 10.22.99.1 - 10.22.99.10, 10.22.99.100     | Option 150: 10.22.99.1  | VoIP |


### 🏢 Configuração DHCP- Building 2

| DHCP Pool | Subnet        | Netmask         | Default Router | Excluded Addresses                        | DHCP Options            | VLAN |
|-----------|---------------|-----------------|----------------|-------------------------------------------|-------------------------|------|
| WIFI_B2   | 10.22.100.0   | 255.255.255.0   | 10.22.100.1    | 10.22.100.1 - 10.22.100.10                | None                    | WIFI |
| F0_B2     | 10.22.101.0   | 255.255.255.128 | 10.22.101.1    | 10.22.101.1 - 10.22.101.10                | None                    | F0   |
| F1_B2     | 10.22.101.128 | 255.255.255.128 | 10.22.101.129  | 10.22.101.129 - 10.22.101.139             | None                    | F1   |
| VOIP_B2   | 10.22.102.0   | 255.255.255.128 | 10.22.102.1    | 10.22.102.1 - 10.22.102.10, 10.22.102.100 | Option 150: 10.22.102.1 | VoIP |


### 🏢 Configuração DHCP - Building 3

| DHCP Pool | Subnet        | Netmask         | Default Router | Excluded Addresses                        | DHCP Options            | VLAN |
|-----------|---------------|-----------------|----------------|-------------------------------------------|-------------------------|------|
| WIFI_B3   | 10.22.104.0   | 255.255.255.0   | 10.22.104.1    | 10.22.104.1 - 10.22.104.10                | None                    | WIFI |
| VOIP_B3   | 10.22.105.0   | 255.255.255.0   | 10.22.105.1    | 10.22.105.1 - 10.22.105.10, 10.22.105.100 | Option 150: 10.22.105.1 | VoIP |
| F1_B3     | 10.22.106.0   | 255.255.255.0   | 10.22.106.1    | 10.22.106.1 - 10.22.106.10                | None                    | F1   |
| F0_B3     | 10.22.107.0   | 255.255.255.128 | 10.22.107.1    | 10.22.107.1 - 10.22.107.10                | None                    | F0   |


### 🏢 Configuração DHCP - Building 4

| DHCP Pool | Subnet        | Netmask         | Default Router | Excluded Addresses                        | DHCP Options            | VLAN |
|-----------|---------------|-----------------|----------------|-------------------------------------------|-------------------------|------|
| WIFI_B4   | 10.22.108.0   | 255.255.255.0   | 10.22.108.1    | 10.22.108.1 - 10.22.108.10                | None                    | WIFI |
| VOIP_B4   | 10.22.109.0   | 255.255.255.0   | 10.22.109.1    | 10.22.109.1 - 10.22.109.10, 10.22.109.100 | Option 150: 10.22.109.1 | VoIP |
| F1_B4     | 10.22.110.0   | 255.255.255.0   | 10.22.110.1    | 10.22.110.1 - 10.22.110.10                | None                    | F1   |
| F0_B4     | 10.22.111.0   | 255.255.255.128 | 10.22.111.1    | 10.22.111.1 - 10.22.111.10                | None                    | F0   |


---


## ☎️ VoIP service

Cada edifício disponibiliza o serviço VoIP local com telefones IP Cisco (modelo 7960) ligados à rede interna. Este serviço permite:

- Chamadas internas dentro do mesmo edifício.

- Encaminhamento (forwarding) de chamadas entre edifícios através da ligação VoIP entre routers.

- Configuração correta das VLANs nos switches para separar o tráfego de voz do tráfego de dados.

- Configuração DHCP com a opção 150 a apontar para o IP do router local (servidor TFTP) para distribuição das configurações dos telefones.


### Prefixos Telefónicos, Dial-Peers e IP dos Routers por Edifício

| Edifício   | Dial-Peer (voice X voip) | Prefixo Telefónico | IP do Router (VLAN VoIP) |
|------------|--------------------------|--------------------|--------------------------|
| Building 1 | 1                        | 1xxx               | 10.22.99.1               |
| Building 2 | 2                        | 2xxx               | 10.22.102.1              |
| Building 3 | 3                        | 3xxx               | 10.22.105.1              |
| Building 4 | 4                        | 4xxx               | 10.22.109.1              |


**Dial-Peers para Chamadas Inter-Edifícios:** Cada router incluirá dial-peers para encaminhar chamadas a prefixos de outros edifícios para 
o IP do router correspondente. Por exemplo, chamadas para prefixos que começam por **3**... são encaminhadas para o **IP 10.22.105.1**.


---


## 🌐 DNS

A arquitetura DNS definida para o projeto estabelece uma hierarquia de domínios baseada nos edifícios:

- Domínio de topo: `rcomp-24-25-dd-g2`, alojado no Building 1.

- Subdomínios: `building-X.rcomp-24-25-dd-g2`, onde X representa o número do edifício (2, 3 ou 4).

- Cada edifício utiliza o servidor na sua DMZ como servidor DNS autoritativo para o respetivo domínio.

- Todos os nomes definidos nas bases de dados DNS são FQDN, terminando em rcomp-24-25-dd-g2.


### 📛 Nomes dos Servidores DNS

Todos os servidores DNS têm o nome não qualificado ns. Assim, o FQDN de cada servidor é:

| Edifício   | Domínio                      | FQDN do Servidor DNS            | IP do Servidor DNS | IP do Servidor HTTP |
|------------|------------------------------|---------------------------------|--------------------|---------------------|
| Building 1 | rcomp-24-25-dd-g2            | ns.rcomp-24-25-dd-g2            | `10.22.99.130`     | `10.22.99.131`      |
| Building 2 | building-2.rcomp-24-25-dd-g2 | ns.building-2.rcomp-24-25-dd-g2 | `10.22.102.130`    | `10.22.102.131`     |
| Building 3 | building-3.rcomp-24-25-dd-g2 | ns.building-3.rcomp-24-25-dd-g2 | `10.22.107.130`    | `10.22.107.131`     |
| Building 4 | building-4.rcomp-24-25-dd-g2 | ns.building-4.rcomp-24-25-dd-g2 | `10.22.111.130`    | `10.22.111.131`     |


### 🌳 Estrutura de Delegação e Glue Records

- O servidor DNS do domínio rcomp-24-25-dd-g2 (Building 1) conhece os IPs dos servidores DNS dos subdomínios (buildings 2, 3 e 4).

- Os servidores DNS dos outros edifícios conhecem o IP do servidor DNS do domínio de topo.

- Cada delegação inclui:

  - Um registo NS (Name Server) que aponta para o FQDN do servidor autoritativo.
  - Um registo A (glue record) que associa o FQDN ao respetivo endereço IPv4.


### 📜 Outros Registos DNS

Em cada domínio definimos:

- **A record:** para `server1` → IP do servidor web do domínio.

  - **CNAME** records:

    - www → server1

    - web → server1

    - dns → ns


### 💻 Configuração dos Clientes DNS

Todos os dispositivos finais (end-nodes) de um edifício utilizarão o servidor DNS local.

A configuração é feita:

- Automaticamente via DHCP (opções `dns-server` e `domain-name` inseridas nas DHCP pools).

- Manualmente nos servidores (DMZ) com IP estático, indicando o IP do servidor DNS local.

---


## 🔀 NAT (Network Address Translation)

De acordo com o que foi pedido para este sprint, decidimos implementar NAT estático para redirecionar pedidos externos de HTTP/HTTPS para os servidores DNS na DMZ de cada edifício.

### ⚙️ Ativação do serviço HTTP/HTTPS no servidor DNS da DMZ

Em cada edifício, foi acedido o servidor DNS (por exemplo, 10.22.99.130 no Building 1) e ativados os serviços HTTP e HTTPS no separador Services.

Criada uma página HTML personalizada, identificando o edifício, domínio e FQDN (ex.: ns.rcomp-24-25-dd-g2 para o Building 1).


### 🌐 Regras de NAT Estático no Router

No router de cada edifício, foram criadas regras de **Port Forwarding (NAT Estático)** para redirecionar as portas:

- **TCP 80 (HTTP)**
- **TCP 443 (HTTPS)**

As regras redirecionam os pedidos:

- Recebidos na **interface da backbone** (ligação externa)
- Para o **IP do servidor DNS local** (na DMZ)

**Exemplo para o Building 1:**
```
ip nat inside source static tcp 10.22.99.130 80 10.22.97.1 80
ip nat inside source static tcp 10.22.99.130 443 10.22.97.1 443
```

### 🔁 Associação das Interfaces NAT

Optámos por associar as interfaces NAT da seguinte forma:

- **DMZ** → **ip nat inside**
- **Backbone** → **ip nat outside**


### Resultado Previsto

- A página HTML do servidor DNS ficará acessível a partir do exterior do edifício através do IP da interface da backbone do router.

- O acesso ao servidor DNS pelo IP público, a partir do interior do edifício, não estará disponível — exatamente como previsto pela configuração de NAT na interface externa.


---


## 🔒 ACLs

Deverá ser implementada uma firewall estática no router de cada edifício, utilizando **Access Control Lists (ACLs)**.
A sua configuração será testada depois de concluídas as principais funcionalidades, de modo a não interferir com os serviços já operacionais.


### ✅ Objetivos a Cumprir

As ACLs deverão obedecer à seguinte sequência de regras:

1. **Prevenção de spoofing**  
   Bloquear todo o tráfego de entrada com destino a IPs atribuídos ao próprio router.
2. **Permissão de tráfego ICMP**  
   Permitir `echo-request` e `echo-reply` em todas as interfaces, para diagnóstico e monitorização.
3. **Proteção da DMZ**
  - Bloquear qualquer tráfego com destino à DMZ, exceto:
    - DNS (UDP/TCP 53)
    - HTTP (TCP 80)
    - HTTPS (TCP 443)
  - Permitir todo o tráfego de saída da DMZ para o exterior.
4. **Restrição de acesso ao router**  
   Bloquear tráfego dirigido ao router, com exceções para:
  - DHCP (bootpc → bootps)
  - TFTP (UDP 69)
  - VoIP / ITS (TCP 2000, SIP UDP/TCP 5060)
  - OSPF
  - Regras de NAT estático (HTTP, HTTPS e DNS para a DMZ)
5. **Permissão de tráfego legítimo**  
   Autorizar a comunicação entre VLANs internas e o acesso ao exterior, conforme as políticas de rede.

### 🔧 Implementação Técnica

As ACLs serão definidas com nomes claros e aplicadas nas respetivas interfaces do router:

- `INTERNET_ACL` – aplicada à interface de entrada da backbone (VLAN 382)
- `WIFI_ACL`, `VOIP_ACL`, `GROUND_FLOOR_ACL`, `FLOOR1_ACL` – aplicadas às interfaces das VLANs internas correspondentes

Cada ACL terminará com `deny ip any any`, reforçando a negação por omissão e garantindo maior clareza na política de segurança.


---