# Documentação do HomeLab

Área destinada à documentação detalhada de cada etapa do projeto.

---

# Estrutura da Documentação

## Infraestrutura Base

* 01 - Proxmox VE
* 02 - Ubuntu Server
* 03 - Docker
* 04 - Portainer
* 05 - WikiJS
* 06 - Uptime Kuma

## Redes e Segurança

* 07 - pfSense
* 10 - Tailscale
* 12 - FortiGate 50E

## Serviços Corporativos

* 08 - Active Directory
* 09 - DNS

## Operação e Suporte

* 11 - Troubleshooting

## Infraestrutura Física

* 13 - Infraestrutura Física

---

# Objetivo da Documentação

Esta área contém toda a documentação técnica do Homelab, incluindo:

* Implantação dos serviços
* Configuração dos equipamentos
* Evidências e capturas de tela
* Procedimentos de instalação
* Solução de problemas
* Diagramas de rede
* Inventário da infraestrutura
* Boas práticas adotadas

---

# Topologia Atual

```text
Internet
    │
Mercusys
192.168.0.1
    │
WAN1 FortiGate
192.168.0.101
    │
LAN FortiGate
192.168.1.1
    │
Switch HPE 1920S
192.168.1.2
    │
├── Proxmox VE
│   └── 192.168.1.101
│
├── Ubuntu Server
│   └── 192.168.1.110
│
└── Windows Server 2022
    └── 192.168.1.20
```

---

# Infraestrutura Atual

| Equipamento             | Função                 | IP            |
| ----------------------- | ---------------------- | ------------- |
| FortiGate 50E           | Firewall Principal     | 192.168.1.1   |
| HPE OfficeConnect 1920S | Switch Core            | 192.168.1.2   |
| Proxmox VE              | Host de Virtualização  | 192.168.1.101 |
| Ubuntu Server           | Serviços Docker        | 192.168.1.110 |
| Windows Server 2022     | Active Directory e DNS | 192.168.1.20  |

---

# Status da Documentação

| Componente            | Status                     |
| --------------------- | -------------------------- |
| Proxmox VE            | ✅ Operacional              |
| Ubuntu Server         | ✅ Operacional              |
| Docker                | ✅ Operacional              |
| Portainer             | ✅ Operacional              |
| WikiJS                | ✅ Operacional              |
| Uptime Kuma           | ✅ Operacional              |
| pfSense               | 🧪 Ambiente de Laboratório |
| Active Directory      | ✅ Operacional              |
| DNS                   | ✅ Operacional              |
| Tailscale             | ✅ Operacional              |
| FortiGate 50E         | ✅ Operacional              |
| Troubleshooting       | 📝 Em Documentação         |
| Infraestrutura Física | 📝 Em Documentação         |

---

# Tecnologias Documentadas

## Virtualização

* Proxmox VE

## Sistemas Operacionais

* Ubuntu Server
* Windows Server 2022

## Containers

* Docker
* Portainer

## Documentação

* WikiJS

## Monitoramento

* Uptime Kuma

## Firewall e Segurança

* FortiGate 50E
* pfSense

## Serviços de Diretório

* Active Directory Domain Services (AD DS)
* DNS

## Acesso Remoto

* Tailscale

---

# Objetivo do Projeto

O objetivo deste Homelab é consolidar conhecimentos em infraestrutura corporativa utilizando equipamentos reaproveitados e tecnologias amplamente utilizadas em ambientes empresariais.

A documentação busca registrar todas as etapas de implantação, configuração, troubleshooting e evolução do ambiente, servindo como material de estudo, portfólio técnico e base de consulta para futuras implementações.

Além do desenvolvimento técnico, o projeto incentiva o reaproveitamento de hardware e a redução do descarte eletrônico, demonstrando que é possível construir um ambiente robusto para estudos e validação de tecnologias utilizando equipamentos que seriam descartados.

---

Projeto em constante evolução para estudos de infraestrutura corporativa, virtualização, redes, segurança da informação, serviços de diretório e boas práticas operacionais.
