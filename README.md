# Infraestrutura Empresarial HomeLab

## Sobre o Projeto

Este laboratório nasceu da proposta de transformação de hardware reaproveitado em uma plataforma de estudos avançados para virtualização, infraestrutura, redes, sistemas operacionais, monitoramento e segurança da informação.

O ambiente foi construído utilizando um servidor baseado em uma placa-mãe Positivo POS-PIQ77CL, processador Intel Core i7-2600 e 24 GB de memória RAM, demonstrando que equipamentos considerados obsoletos ainda podem entregar excelente desempenho quando utilizados de forma estratégica.

O objetivo do projeto é consolidar conhecimentos em virtualização, Linux, Windows Server, Active Directory, DNS, containers, monitoramento, VPN, firewall corporativo e boas práticas de infraestrutura empresarial, documentando cada etapa de implantação, configuração e resolução de problemas encontrados durante a evolução do ambiente.

Além do desenvolvimento técnico, o projeto busca incentivar o reaproveitamento de equipamentos e a redução do descarte eletrônico, mostrando que é possível construir um laboratório robusto para estudos e validação de tecnologias sem a necessidade de investimentos elevados em hardware.

Este projeto também reflete a importância da colaboração entre profissionais de tecnologia. Além do esforço individual de planejamento e implementação, o laboratório recebeu apoio de amigos que contribuíram com equipamentos corporativos para testes, como um switch gerenciável HPE OfficeConnect 1920S e um firewall FortiGate 50E, permitindo a construção de cenários mais próximos dos ambientes empresariais reais.

---

# Objetivos

- Consolidar conhecimentos em infraestrutura corporativa
- Simular ambientes encontrados em empresas de médio e grande porte
- Documentar processos de implantação e solução de problemas
- Validar tecnologias de virtualização, redes e segurança
- Compartilhar conhecimento através do GitHub e LinkedIn
- Incentivar o reaproveitamento de hardware

---

# Tecnologias Implementadas

## Virtualização

- Proxmox VE 9

## Sistemas Operacionais

- Ubuntu Server
- Windows Server 2022

## Containers

- Docker
- Portainer
- Nginx Proxy Manager

## Documentação

- WikiJS
- GitHub

## Monitoramento

- Uptime Kuma

## Firewall e Redes

- FortiGate 50E
- HPE OfficeConnect 1920S
- pfSense (Laboratório)
- NAT
- DHCP
- Firewall IPv4

## Serviços de Diretório

- Active Directory Domain Services (AD DS)
- DNS Integrado

## Acesso Remoto

- Tailscale

---

# Infraestrutura Atual

## Equipamentos Físicos

### Servidor Principal

Hardware:

- Placa-mãe Positivo POS-PIQ77CL
- Intel Core i7-2600
- 24 GB DDR3
- SSD 1 TB
- HDD Western Digital Blue 1 TB
- HDD Western Digital Blue 1 TB

Função:

- Host Proxmox VE

---

### Firewall Corporativo

Equipamento:

- FortiGate 50E

Configuração:

- WAN: 192.168.0.101
- LAN: 192.168.1.1

Funções:

- Gateway Principal
- NAT
- DHCP
- Firewall
- Controle de Acesso

---

### Switch Core

Equipamento:

- HPE OfficeConnect 1920S 48G 4SFP PoE+ (JL386A)

Configuração:

- Hostname: SW-CORE-HOMELAB
- IP: 192.168.1.2

Função:

- Backbone da rede interna

---

# Máquinas Virtuais

## Proxmox VE

IP:

192.168.1.101

---

## Ubuntu Server

IP:

192.168.1.110

Serviços:

- Docker
- Portainer
- WikiJS
- Uptime Kuma
- Nginx Proxy Manager
- Tailscale

---

## Windows Server 2022

Hostname:

SRV-DC01

IP:

192.168.1.20

Domínio:

homelab.local

Serviços:

- Active Directory
- DNS

---

## pfSense (Laboratório)

IP Planejado:

192.168.1.40

Finalidade:

- Estudos de firewall
- Comparação entre plataformas
- Testes de roteamento e VLANs

---

# Topologia Atual

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

# Plano de Endereçamento

## Infraestrutura

| Equipamento | IP |
|------------|------------|
| FortiGate 50E | 192.168.1.1 |
| Switch HPE 1920S | 192.168.1.2 |
| Proxmox VE | 192.168.1.101 |
| Ubuntu Server | 192.168.1.110 |
| Windows Server | 192.168.1.20 |
| pfSense Lab | 192.168.1.40 |

## DHCP

Faixa:

192.168.1.100 - 192.168.1.200

---

# Implementações Concluídas

- Proxmox VE
- Ubuntu Server
- Docker
- Portainer
- WikiJS
- Uptime Kuma
- Nginx Proxy Manager
- Active Directory
- DNS
- Tailscale
- FortiGate 50E
- HPE OfficeConnect 1920S
- Monitoramento de Infraestrutura
- Backup das Configurações do Firewall

---

# Em Documentação

- Evidências e screenshots
- Diagramas de rede
- Inventário completo
- Configuração do FortiGate
- Configuração do Switch HPE

---

# Próximas Etapas

- Organização física do rack
- Integração do Access Point UniFi
- Implementação de VLANs
- VPN SSL no FortiGate
- Servidor de Arquivos
- Wazuh SIEM
- Kubernetes
- Integração AWS
- Integração Azure

---

# Principais Desafios Resolvidos

## Acesso Remoto sob CGNAT

Problema:

Operadora utilizando CGNAT, impossibilitando acesso remoto tradicional.

Solução:

Implementação do Tailscale utilizando o Ubuntu Server como Subnet Router.

Resultado:

Acesso remoto seguro aos serviços internos sem necessidade de abertura de portas.

---

## Reestruturação da Infraestrutura de Rede

Problema:

Necessidade de substituir o ambiente baseado em pfSense por um firewall corporativo.

Solução:

Implantação do FortiGate 50E como firewall principal e reorganização completa do endereçamento IP.

Resultado:

Ambiente corporativo funcional com NAT, DHCP, DNS e políticas de firewall operacionais.

---

# Estrutura da Documentação

01-proxmox

02-servidor-ubuntu

03-docker

04-portainer

05-wikijs

06-uptime-kuma

07-pfsense

08-active-directory

09-dns

10-tailscale

11-troubleshooting

12-fortigate

13-switch-hpe

---

# Status do Projeto

🟢 Ambiente operacional e em constante evolução.

Atualmente o laboratório possui virtualização, containers, monitoramento, firewall corporativo, Active Directory, DNS, acesso remoto seguro e documentação técnica em desenvolvimento, servindo como plataforma para estudos, validação de tecnologias e demonstração prática de conhecimentos em infraestrutura corporativa.
