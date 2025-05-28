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

| **Tarefa** | **Descrição da tarefa**                                                                                                                                                                                          |  **Aluno**  |
|:----------:|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------:|
|  **2.1**   | Desenvolvimento de uma simulação do Packet Tracer de camada dois e camada três para o edifício 1, abrangendo o backbone do campus. Integração da simulação do Packet Tracer de cada membro numa única simulação. | **1230543** |
|  **2.2**   | Desenvolvimento de uma simulação do Packet Tracer de camada dois e camada três para o edifício 2, abrangendo o backbone do campus.                                                                               | **1230487** |
|  **2.3**   | Desenvolvimento de uma simulação do Packet Tracer de camada dois e camada três para o edifício 3, abrangendo o backbone do campus.                                                                               | **1230544** |
|  **2.4**   | Desenvolvimento de uma simulação do Packet Tracer de camada dois e camada três para o edifício 4, abrangendo o backbone do campus.                                                                               | **1231046** |


---

## 🧩 Subtarefas por Edifício

> Cada edifício segue um plano muito semelhante. Para clareza, as subtarefas estão organizadas em secções e detalhadas no conteúdo completo abaixo.

- ### 🏢 Building 1

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

- ### 🏢 Building 2

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

- ### 🏢 Building 3

| **Tarefa** | **Descrição da tarefa**                                                                                         |
|:----------:|-----------------------------------------------------------------------------------------------------------------|
| **2.3.1**  | Coloque os dispositivos no Edifício 3: PCs, computadores portáteis, servidores, telefones IP, switches, routers |
| **2.3.2**  | Nomeie os dispositivos no Edifício 3 utilizando as convenções de equipa                                         |
| **2.3.3**  | Configurar o domínio VTP (`r2425ddg2`) no switch principal do Edifício 3 (modo servidor)                        |
| **2.3.4**  | Adicionar 4 VLANs de construção (F0, F1, WiFi, DMZ, VoIP) + VLAN de backbone ao switch principal                |
| **2.3.5**  | Ligue os switches do Edifício 3 com fibra/cobre de acordo com o projeto de cablagem                             |
| **2.3.6**  | Defina todas as ligações entre switches para o modo trunk (todas as VLAN permitidas)                            |
| **2.3.7**  | Configurar os switches não principais no Edifício 3 como clientes VTP                                           |
| **2.3.8**  | Atribuir portas de acesso: VLANs F0/F1 para PCs, VLAN WiFi para AP, VLAN VoIP para telefones                    |
| **2.3.9**  | Atribuir endereços IPv3 estáticos aos dispositivos do Edifício 3                                                |
| **2.3.10** | Configurar subinterfaces do router para cada VLAN                                                               |
| **2.3.11** | Ligue o router do Edifício 3 à VLAN do backbone e atribua um IP                                                 |
| **2.3.12** | Adicionar rotas estáticas no router do Edifício 4 para o backbone e outros edifícios                            |
| **2.3.13** | Simular ligações de backbone para outros edifícios (modo trunk)                                                 |
| **2.3.14** | Validar os caminhos de redundância entre os switches do Edifício 3                                              |
| **2.3.15** | Documento Building 3 especificações: IDs de VLAN, intervalos de IP, tabelas de encaminhamento em `planning.md`  |

<br>

- ### 🏢 Building 4

| **Tarefa** | **Descrição da tarefa**                                                                                         |
|:----------:|-----------------------------------------------------------------------------------------------------------------|
| **2.4.1**  | Coloque os dispositivos no Edifício 4: PCs, computadores portáteis, servidores, telefones IP, switches, routers |
| **2.4.2**  | Nomeie os dispositivos no Edifício 4 utilizando as convenções de equipa                                         |
| **2.4.3**  | Configurar o domínio VTP (`r2425ddg2`) no switch principal do Edifício 4 (modo servidor)                        |
| **2.4.4**  | Adicionar 4 VLANs de construção (F0, F1, WiFi, DMZ, VoIP) + VLAN de backbone ao switch principal                |
| **2.4.5**  | Ligue os switches do Edifício 4 com fibra/cobre de acordo com o projeto de cablagem                             |
| **2.4.6**  | Defina todas as ligações entre switches para o modo trunk (todas as VLAN permitidas)                            |
| **2.4.7**  | Configurar os switches não principais no Edifício 4 como clientes VTP                                           |
| **2.4.8**  | Atribuir portas de acesso: VLANs F0/F1 para PCs, VLAN WiFi para AP, VLAN VoIP para telefones                    |
| **2.4.9**  | Atribuir endereços IPv4 estáticos aos dispositivos do Edifício 4                                                |
| **2.4.10** | Configurar subinterfaces do router para cada VLAN                                                               |
| **2.4.11** | Ligue o router do Edifício 4 à VLAN do backbone e atribua um IP                                                 |
| **2.4.12** | Adicionar rotas estáticas no router do Edifício 4 para o backbone e outros edifícios                            |
| **2.4.13** | Simular ligações de backbone para outros edifícios (modo trunk)                                                 |
| **2.4.14** | Validar os caminhos de redundância entre os switches do Edifício 4                                              |
| **2.4.15** | Documento Building 4 especificações: IDs de VLAN, intervalos de IP, tabelas de encaminhamento em `planning.md`  |

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


>Tabela inclui 21 VLANs dos edifícios + Backbone (ID 362 a 382), com nomes e descrições para cada tipo de tráfego.


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

## 🎯 Objetivos Gerais

- Criar uma simulação das redes por edifício incluindo o backbone comum.
- Uniformizar a nomenclatura dos dispositivos.
- Simular estrutura de cablagem com switches e cabos apropriados.

---

## 🧱 Configuração Layer 2

- VLANs por piso, WiFi, DMZ e VoIP em cada edifício.
- Backbone VLAN comum a todos.
- Switches ligados em trunk.
- VTP configurado com um servidor por edifício.
- STP ativo em todos os switches.

---

## 🌐 Configuração Layer 3

- Cada VLAN com sub-rede IPv4 dedicada.
- Router modelo 2811 por edifício com subinterfaces.
- Tráfego inter-VLAN encaminhado via backbone.
- Endereçamento baseado em bloco `10.22.96.0/20` (ver tabelas completas por edifício).

---

## 📄 Conteúdo Técnico Detalhado

### 🔌 VLANs
Em cada edifício, as seguintes VLANs devem ser configuradas:

- **Piso 0**: VLAN para todas as tomadas.
- **Piso 1**: VLAN para todas as tomadas.
- **Rede Wi-Fi**: VLAN para todas as tomadas de APs dentro do edifício.
- **DMZ**: VLAN para servidores, estações de trabalho de administração e dispositivos de rede da infraestrutura.
- **VoIP**: VLAN para todos os telefones IP dentro do edifício.

Essas VLANs, apesar de estarem associadas a um edifício específico, devem estar disponíveis em todos os switches de todos os edifícios. Cada switch deve manter uma base de dados local com todas as VLANs, e todas as interligações entre switches devem ser configuradas em modo trunk para transportar todas as VLANs.

Adicionalmente, uma VLAN para o Campus Backbone deve ser configurada, compartilhada por todos os edifícios. Essa VLAN deve estar disponível em todos os switches, em suas bases de dados locais.
<br><br>

### ⚙️ Protocolo de Transporte de VLAN (VTP)
Para garantir a consistência entre os switches, utilize o VTP, que facilita a propagação das informações de VLANs.

- **Domínio VTP**: Todos os switches devem estar no mesmo domínio VTP, com o nome de domínio configurado uniformemente (vtp domain ...).
- **Modo de servidor**: Pelo menos um switch deve estar no modo servidor (vtp mode server), onde a base de dados de VLANs pode ser configurada manualmente.
- **Modo de cliente**: Outros switches podem estar em modo cliente (vtp mode client), onde eles recebem as atualizações da base de dados de VLAN propagadas pelos switches no modo servidor.
- **Modo trunk**: As portas de interligação entre switches devem estar configuradas no modo trunk (switchport mode trunk), permitindo a propagação de todas as VLANs.
  <br><br>

### 📊 Banco de Dados de VLAN & Domínio VTP

- **VLANs**: Cada VLAN deve ter um nome único e significativo, com um VLANID único (entre 2 e 1000, para evitar interferências).
- **Domínio VTP**: O nome do domínio VTP deve ser o mesmo em todos os switches para garantir a propagação correta.
  <br><br>

### 🌐 Redes IPv4

#### Requisitos de Endereçamento

Os endereços de rede IPv4 para cada VLAN devem ser atribuídos de acordo com os seguintes requisitos de número de nós:

- **Building Campus Backbone**:
  - **Backbone**: 220 nós


- **Building 1**:
  - **Pontos de acesso - Piso 0**: 40 nós
  - **Pontos de acesso - Piso 1**: 45 nós
  - **Wi-Fi**: 95 nós
  - **DMZ (Servidores, estações de trabalho administrativas e dispositivos de infraestrutura de rede)**: 110 nós
  - **VoIP (Telefones IP)**: 70 nós
  - **B1**: 360 nós


- **Building 2**:
  - **Pontos de acesso - Piso 0**: 100 nós
  - **Pontos de acesso - Piso 1**: 110 nós
  - **Wi-Fi**: 200 nós
  - **DMZ (Servidores, estações de trabalho administrativas e dispositivos de infraestrutura de rede)**: 60 nós
  - **VoIP (Telefones IP)**: 120 nós
  - **B2**: 690 nós


- **Building 3**:
  - **Pontos de acesso - Piso 0**: 115 nós
  - **Pontos de acesso - Piso 1**: 135 nós
  - **Wi-Fi**: 220 nós
  - **DMZ (Servidores, estações de trabalho administrativas e dispositivos de infraestrutura de rede)**: 50 nós
  - **VoIP (Telefones IP)**: 170 nós
  - **B3**: 690 nós


- **Building 4**:
  - **Pontos de acesso - Piso 0**: 125 nós
  - **Pontos de acesso - Piso 1**: 170 nós
  - **Wi-Fi**: 200 nós
  - **DMZ (Servidores, estações de trabalho administrativas e dispositivos de infraestrutura de rede)**: 45 nós
  - **VoIP (Telefones IP)**: 160 nós
  - **B4**: 700 nós


- **Gerais**:
  - **Planejamento do Sprint**: A equipe deve definir:
    - O endereço de rede IPv4 para o Campus Backbone.
    - O endereço IPv4 dos roteadores para a conexão com a rede backbone.
    - O bloco de endereços para cada membro da equipe dentro do seu edifício, assegurando que não haja sobreposição entre os blocos.
      <br><br>

#### 🔧 Espaço de Endereços IPv4

- **Bloco de Endereços IPv4 a ser utilizado**: 10.22.96.0/20
<br><br>

#### 🏠 Distribuição de Endereçamento IPv4 por Zona/Edifício

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

### 🔗 Endereço IPv4 do Nó do Router do ISP
- **Endereço**: 87.5.127.93/30


---

## 💻 Dispositivos Finais na Simulação

Cada building deve conter pelo menos:

- PC (piso 0)
- PC (piso 1)
- Laptop e/ou Smartphone e/ou Tablet
- Servidor (DMZ)
- Telefone VoIP

Os dispositivos finais devem ser conectados às VLANs corretas configurando as portas correspondentes do switch no modo de acesso (`switchport mode access`) e atribuindo a VLAN correta a elas (`switchport access vlan ...`).

Exceto os telefones VoIP, todos os outros dispositivos finais devem ter uma configuração IPv4 estática e definida manualmente, incluindo o gateway padrão.

Para os telefones VoIP, deve ser utilizado o modelo **7960**. A porta correspondente no switch também deve ser configurada no modo de acesso (`switchport mode access`), porém, a VLAN de acesso deve ser desativada (`no switchport access vlan`), e a VLAN de voz deve ser utilizada no lugar (`switchport voice vlan ...`).

A configuração IPv4 dos telefones VoIP está fora do escopo por enquanto e será abordada no próximo sprint.
<br>

- ### Routers e Roteamento Estático

Em cada edifício, deve haver um roteador. Utilize exclusivamente o modelo **2811**, pois outros modelos podem não suportar VoIP no Packet Tracer, o que será necessário no próximo sprint.

O roteador de cada edifício será responsável pelo encaminhamento do tráfego IPv4 entre as redes locais IPv4 (dentro do edifício) e as redes IPv4 de outros edifícios. O tráfego para outros edifícios será roteado através da rede IPv4 do backbone, direcionado para o roteador apropriado.

Os endereços IPv4 dos nós utilizados por cada roteador na rede backbone são definidos na reunião de planeamento. Juntamente com os blocos de endereços atribuídos a cada edifício, isso possibilita a construção da tabela de roteamento estático em cada roteador.

Cada membro da equipa é responsável por criar a simulação do Packet Tracer para um edifício. Cada simulação abrangerá um único edifício, mas deve incluir a rede backbone do campus. O **cross-connect principal** e todos os **cross-connects intermediários** devem ser representados por um switch, e um **roteador (modelo 2811)** deve estar conectado a cada um deles.

Como cada roteador está conectado a **seis redes IPv4 diferentes**, seria esperado um roteador com seis interfaces de rede. No entanto, assim como uma única conexão no modo trunk entre dois switches pode conectar várias VLANs, o mesmo conceito se aplica à conexão com um roteador. No roteador, cada VLAN aparecerá como uma **interface de rede lógica (subinterface)**.

Assim, para conectar o roteador a essas seis redes, a melhor solução é usar **uma única conexão de cabo para uma porta configurada no modo trunk no switch**.

Quanto à configuração dos roteadores fora do edifício, deve abranger apenas a conexão com a VLAN do backbone e o respetivo endereço IP. A configuração completa do roteador de cada edifício é responsabilidade do membro da equipe encarregado desse edifício. 

---

## 🌍 Ligação à Internet

- Apenas Edifício 1 liga-se à Internet via router ISP (IPv4: `87.5.127.93/30`) com ligação DSL. 

