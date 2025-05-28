# Edifício 1

## ⚙️ Estrutura Packet Tracer

![](Edifício-1.png)

<br>

## 🧩 Subtarefas

| **Tarefa** | **Descrição da tarefa**                                                                                         |
|:----------:|-----------------------------------------------------------------------------------------------------------------|
| **2.1.1**  | Coloque os dispositivos no Edifício 1: PCs, computadores portáteis, servidores, telefones IP, switches, routers |
| **2.1.2**  | Nomeie os dispositivos no Edifício 1 utilizando as convenções de equipa                                         |
| **2.1.3**  | Configurar o domínio VTP (`r2425ddg2`) no switch principal do Edifício 1 (modo servidor)                        |
| **2.1.4**  | Adicionar 4 VLANs de construção (F0, F1, WiFi, DMZ, VoIP) + VLAN de backbone ao switch principal                |
| **2.1.5**  | Ligue os switches do Edifício 1 com fibra/cobre de acordo com o projeto de cablagem                             |
| **2.1.6**  | Defina todas as ligações entre switches para o modo trunk (todas as VLAN permitidas)                            |
| **2.1.7**  | Configurar os switches não principais no Edifício 1 como clientes VTP                                           |
| **2.1.8**  | Atribuir portas de acesso: VLANs F0/F1 para PCs, VLAN WiFi para AP, VLAN VoIP para telefones                    |
| **2.1.9**  | Atribuir endereços IPv4 estáticos aos dispositivos do Edifício 1                                                |
| **2.1.10** | Configurar subinterfaces do router para cada VLAN                                                               |
| **2.1.11** | Ligue o router do Edifício 1 à VLAN do backbone e atribua um IP                                                 |
| **2.1.12** | Adicionar rotas estáticas no router do Edifício 1 para o backbone e outros edifícios                            |
| **2.1.13** | Simular ligações de backbone para outros edifícios (modo trunk)                                                 |
| **2.1.14** | Validar os caminhos de redundância entre os switches do Edifício 1                                              |
| **2.1.15** | Documento Building 1 especificações: IDs de VLAN, intervalos de IP, tabelas de encaminhamento em `planning.md`  |

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
| 362     | B1_floor0       | Building 1 - Floor 0 (outlets)                                |
| 363     | B1_floor1       | Building 1 - Floor 1 (outlets)                                |
| 364     | B1_wifi_network | Building 1 - Wifi Network (access points)                     |
| 365     | B1_DMZ          | Building 1 - DMZ (Servers, administration and infrastructure) |
| 366     | B1_VoIP         | Building 1 - VoIP (IP-phones)                                 |

<br>

## 🌐 Requisitos de Endereçamento

Os endereços de rede IPv4 para cada VLAN devem ser atribuídos de acordo com os seguintes requisitos de número de nós do Building 1:

- **Pontos de acesso - Piso 0**: 40 nós 
- **Pontos de acesso - Piso 1**: 45 nós
- **Wi-Fi**: 95 nós
- **DMZ (Servidores, estações de trabalho administrativas e dispositivos de infraestrutura de rede)**: 110 nós
- **VoIP (Telefones IP)**: 70 nós
- **B1**: 360 nós

<br>

## 🔧 Espaço de Endereços IPv4

|  **Subnet address**  |     Netmask     |      Range of addresses      |         Useable IPs          | Hosts  | VLAN |
|:--------------------:|:---------------:|:----------------------------:|:----------------------------:|:------:|:----:|
|  **10.22.98.0/26**   | 255.255.255.192 |   10.22.98.0 - 10.22.98.63   |   10.22.98.1 - 10.22.98.62   |   62   |  F0  |
|  **10.22.98.64/26**  | 255.255.255.192 |  10.22.98.64 - 10.22.98.127  |  10.22.98.65 - 10.22.98.126  |   62   |  F1  |
| **10.22.98.128/25**  | 255.255.255.128 | 10.22.98.128 - 10.22.98.255  | 10.22.98.129 - 10.22.98.254  |  126   | WIFI |
|  **10.22.99.0/25**   | 255.255.255.128 |  10.22.99.0 - 10.22.99.127   |  10.22.99.1 - 10.22.99.126   |  126   | VoIP |
| **10.22.99.128/25**  | 255.255.255.128 | 10.22.99.128 - 10.22.99.255  | 10.22.99.129 - 10.22.99.254  |  126   | DMZ  |

<br>

## 💻 Dispositivos Finais na Simulação

- PC (piso 0)
- PC (piso 1)
- Laptops
- Smartphones
- Servidor (DMZ)
- Telefones VoIP modelo **7960**