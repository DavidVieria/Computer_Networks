# Edifício 2

## ⚙️ Estrutura Packet Tracer

![](Edifício-2.png)

<br>

## 🧩 Subtarefas

| **Tarefa** | **Descrição da tarefa**                                                                                         |
|:----------:|-----------------------------------------------------------------------------------------------------------------|
| **2.2.1**  | Coloque os dispositivos no Edifício 2: PCs, computadores portáteis, servidores, telefones IP, switches, routers |
| **2.2.2**  | Nomeie os dispositivos no Edifício 2 utilizando as convenções de equipa                                         |
| **2.2.3**  | Configurar o domínio VTP (`r2425ddg2`) no switch principal do Edifício 2 (modo servidor)                        |
| **2.2.4**  | Adicionar 4 VLANs de construção (F0, F1, WiFi, DMZ, VoIP) + VLAN de backbone ao switch principal                |
| **2.2.5**  | Ligue os switches do Edifício 2 com fibra/cobre de acordo com o projeto de cablagem                             |
| **2.2.6**  | Defina todas as ligações entre switches para o modo trunk (todas as VLAN permitidas)                            |
| **2.2.7**  | Configurar os switches não principais no Edifício 2 como clientes VTP                                           |
| **2.2.8**  | Atribuir portas de acesso: VLANs F0/F1 para PCs, VLAN WiFi para AP, VLAN VoIP para telefones                    |
| **2.2.9**  | Atribuir endereços IPv2 estáticos aos dispositivos do Edifício 2                                                |
| **2.2.10** | Configurar subinterfaces do router para cada VLAN                                                               |
| **2.2.11** | Ligue o router do Edifício 2 à VLAN do backbone e atribua um IP                                                 |
| **2.2.12** | Adicionar rotas estáticas no router do Edifício 2 para o backbone e outros edifícios                            |
| **2.2.13** | Simular ligações de backbone para outros edifícios (modo trunk)                                                 |
| **2.2.14** | Validar os caminhos de redundância entre os switches do Edifício 2                                              |
| **2.2.15** | Documento Building 2 especificações: IDs de VLAN, intervalos de IP, tabelas de encaminhamento em `planning.md`  |

<br>

## 🔌 VLANs

- **Piso 0**: VLAN para todas as tomadas.
- **Piso 1**: VLAN para todas as tomadas.
- **Rede Wi-Fi**: VLAN para todas as tomadas de APs dentro do edifício.
- **DMZ**: VLAN para servidores, estações de trabalho de administração e dispositivos de rede da infraestrutura.
- **VoIP**: VLAN para todos os telefones IP dentro do edifício.

<br>

| VLAN ID | nome VLAN       | descrição VLAN                                                |
|---------|-----------------|---------------------------------------------------------------|
| 367     | B2_floor0       | Building 2 - Floor 0 (outlets)                                |
| 368     | B2_floor1       | Building 2 - Floor 1 (outlets)                                |
| 369     | B2_wifi_network | Building 2 - Wifi Network (access points)                     |
| 370     | B2_DMZ          | Building 2 - DMZ (Servers, administration and infrastructure) |
| 371     | B2_VoIP         | Building 2 - VoIP (IP-phones)                                 |

<br>

## 🌐 Requisitos de Endereçamento

Os endereços de rede IPv4 para cada VLAN devem ser atribuídos de acordo com os seguintes requisitos de número de nós do Building 2:

- **Pontos de acesso - Piso 0**: 100 nós
- **Pontos de acesso - Piso 1**: 110 nós
- **Wi-Fi**: 200 nós
- **DMZ (Servidores, estações de trabalho administrativas e dispositivos de infraestrutura de rede)**: 60 nós
- **VoIP (Telefones IP)**: 120 nós
- **B2**: 690 nós

<br>

## 🔧 Espaço de Endereços IPv4

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

## 💻 Dispositivos Finais na Simulação

- PC (piso 0)
- PC (piso 1)
- Laptops
- Smartphones
- Tablets
- Servidor (DMZ)
- Telefones VoIP modelo **7960**