# FortiGate 50E

## Objetivo

Documentar a implantação do FortiGate 50E como firewall principal do Homelab, substituindo a arquitetura anteriormente baseada em pfSense.

---

## Equipamento

Modelo:

FortiGate 50E

Hostname:

FGT-CORE

Função:

- Firewall Principal
- NAT
- DHCP
- Gateway da Rede
- Controle de Acesso

---

## Cenário Inicial

A infraestrutura utilizava um ambiente baseado em pfSense para estudos e segmentação de rede.

Durante a evolução do laboratório foi disponibilizado um equipamento FortiGate 50E, permitindo a construção de um ambiente mais próximo da realidade corporativa.

---

## Processo de Implantação

### Acesso via Console

Procedimentos realizados:

- Instalação do driver FT232R USB UART
- Identificação da porta COM
- Conexão serial utilizando PuTTY
- Acesso ao console do equipamento

---

### Reset de Fábrica

Procedimentos:

- Reset completo do equipamento
- Reinicialização
- Retorno às configurações padrão

---

### Configuração WAN

Configuração obtida automaticamente via DHCP.

WAN1:

IP: 192.168.0.101

Gateway:

192.168.0.1

---

### Configuração LAN

Interface:

HOMELAB

Endereço:

192.168.1.1/24

---

### Configuração DHCP

Faixa configurada:

192.168.1.100
até
192.168.1.200

Gateway:

192.168.1.1

---

### Política de Firewall

Regra criada:

Origem:

HOMELAB (LAN)

Destino:

WAN1

Ação:

ACCEPT

NAT:

Habilitado

---

## Integração com Switch HPE

Switch:

HPE OfficeConnect 1920S

IP:

192.168.1.2

Gateway:

192.168.1.1

Função:

Backbone principal da infraestrutura.

---

## Topologia Final

```text
Internet
    │
Mercusys
192.168.0.1
    │
WAN FortiGate
192.168.0.101
    │
LAN FortiGate
192.168.1.1
    │
Switch HPE 1920S
192.168.1.2
    │
──────────────────────────
│           │           │
│           │           │
Proxmox    Ubuntu    Windows
1.101      1.110     1.20
```

---

## Testes Realizados

### Gateway

Ping para:

192.168.1.1

Resultado:

Sucesso

---

### Switch

Ping para:

192.168.1.2

Resultado:

Sucesso

---

### Internet

Ping para:

8.8.8.8

Resultado:

Sucesso

---

### DNS

Consulta:

google.com

Resultado:

Resolução de nomes funcional

---

## Status

🟢 Operacional

Serviços validados:

- WAN
- LAN
- DHCP
- NAT
- DNS
- Firewall IPv4
- Integração com Switch HPE
- Comunicação com Proxmox
- Comunicação com Windows Server
- Comunicação com Ubuntu Server

---

## Evidências

As capturas de tela utilizadas durante a implantação encontram-se registradas no histórico do projeto e serão adicionadas posteriormente à documentação.
