# HomeLab Enterprise Infrastructure

## Sobre o Projeto

Laboratório de infraestrutura corporativa desenvolvido para estudos práticos, validação de tecnologias e documentação de ambientes semelhantes aos encontrados em empresas de médio e grande porte.

O projeto tem como objetivo consolidar conhecimentos em virtualização, sistemas operacionais, redes, monitoramento, segurança da informação, Active Directory, containers e firewall.

---

## Tecnologias Implementadas

### Virtualização

* Proxmox VE

### Sistemas Operacionais

* Ubuntu Server
* Windows Server 2022

### Containers

* Docker
* Portainer

### Documentação

* WikiJS

### Monitoramento

* Uptime Kuma

### Firewall e Redes

* pfSense
* Roteamento entre sub-redes

### Serviços de Diretório

* Active Directory Domain Services (AD DS)
* DNS Integrado

### Acesso Remoto

* Tailscale
* Subnet Router

---

## Infraestrutura Atual

### Proxmox

* IP: 192.168.1.101

### Ubuntu Server

* IP: 192.168.1.110

Serviços:

* Docker
* Portainer
* WikiJS
* Uptime Kuma
* Nginx Proxy Manager
* Tailscale

### pfSense

WAN:

* 192.168.1.111

LAN:

* 192.168.10.1

### Windows Server 2022

Hostname:

* SRV-DC01

IP:

* 192.168.10.100

Domínio:

* homelab.local

Serviços:

* Active Directory
* DNS

---

## Implementações Concluídas

* [x] Proxmox VE
* [x] Ubuntu Server
* [x] Docker
* [x] Portainer
* [x] WikiJS
* [x] Uptime Kuma
* [x] pfSense
* [x] Active Directory
* [x] DNS
* [x] Tailscale
* [x] Monitoramento

---

## Próximas Etapas

* [ ] FortiGate 50E
* [ ] VLANs
* [ ] SSL VPN
* [ ] Políticas de Grupo (GPO)
* [ ] File Server
* [ ] Wazuh SIEM
* [ ] Kubernetes
* [ ] Integração AWS
* [ ] Integração Azure

---

## Principais Desafios Resolvidos

### Monitoramento entre Redes

Problema:

* Windows Server não respondia ao monitoramento.

Causa:

* Regra WAN do pfSense configurada incorretamente.

Solução:

* Ajuste das regras de firewall e roteamento.

---

### Acesso Remoto sob CGNAT

Problema:

* Operadora utiliza CGNAT.

Solução:

* Implementação do Tailscale como Subnet Router.

Resultado:

* Acesso remoto ao Proxmox, pfSense e servidores sem necessidade de AnyDesk.
