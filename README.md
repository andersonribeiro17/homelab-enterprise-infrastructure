# HomeLab Enterprise Infrastructure

## Sobre o Projeto

Este laboratório nasceu da proposta de transformar hardware reaproveitado em uma plataforma de estudos voltada para virtualização, infraestrutura, redes, sistemas operacionais e segurança da informação.

O ambiente foi construído utilizando um servidor baseado em uma placa-mãe Positivo POS-PIQ77CL, processador Intel Core i7-2600 e 24 GB de memória RAM, demonstrando que equipamentos considerados obsoletos ainda podem entregar excelente desempenho quando utilizados de forma estratégica.

O objetivo do projeto é consolidar conhecimentos em virtualização, Linux, Windows Server, Active Directory, DNS, containers, monitoramento, VPN, firewall e boas práticas de infraestrutura corporativa, documentando cada etapa de implantação, configuração e resolução de problemas encontrados durante a evolução do ambiente.

Além do desenvolvimento técnico, o projeto busca incentivar o reaproveitamento de equipamentos e a redução do descarte eletrônico, mostrando que é possível criar um laboratório robusto para estudos e validação de tecnologias sem a necessidade de investimentos elevados em hardware.

Este projeto também reflete a importância da colaboração entre profissionais de tecnologia. Além do esforço individual de planejamento e implementação, o laboratório recebeu apoio de amigos que contribuíram com equipamentos para testes, como switches corporativos e um FortiGate 50E. Essa colaboração tornou possível expandir a infraestrutura e criar cenários mais próximos dos ambientes corporativos reais, enriquecendo o processo de aprendizado e validação das soluções implementadas.

---

## Objetivos

* Consolidar conhecimentos em infraestrutura corporativa
* Simular ambientes encontrados em empresas de médio e grande porte
* Documentar processos de implantação e troubleshooting
* Validar tecnologias de virtualização, redes e segurança
* Compartilhar conhecimento através do GitHub e LinkedIn

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
* Nginx Proxy Manager

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

### Servidor Principal

Hardware:

* Placa-mãe Positivo POS-PIQ77CL
* Intel Core i7-2600
* 24 GB DDR3
* SSD 1 TB
* HDD Western Digital Blue 1 TB
* HDD Western Digital Blue 1 TB

Função:

* Host principal Proxmox VE

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
* [x] Nginx Proxy Manager
* [x] pfSense
* [x] Active Directory
* [x] DNS
* [x] Tailscale
* [x] Monitoramento

---

## Em Documentação

* [ ] Evidências e screenshots
* [ ] Diagramas de rede
* [ ] Procedimentos detalhados
* [ ] Inventário completo da infraestrutura

---

## Próximas Etapas

* [ ] FortiGate 50E
* [ ] Integração do Access Point UniFi U6-Lite
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

**Problema:**

* Windows Server não respondia ao monitoramento realizado pelo Uptime Kuma.

**Causa:**

* Regra WAN do pfSense configurada incorretamente.

**Solução:**

* Ajuste das regras de firewall e roteamento entre as redes.

**Resultado:**

* Comunicação restabelecida e monitoramento funcional.

---

### Acesso Remoto sob CGNAT

**Problema:**

* Operadora utiliza CGNAT, impossibilitando acesso remoto tradicional por redirecionamento de portas.

**Solução:**

* Implementação do Tailscale utilizando o Ubuntu Server como Subnet Router.

**Resultado:**

* Acesso remoto ao Proxmox, pfSense e servidores internos sem necessidade de AnyDesk ou abertura de portas na internet.

---

## Estrutura da Documentação

A documentação detalhada de cada etapa do laboratório encontra-se na pasta `docs`.

* 01-proxmox
* 02-ubuntu-server
* 03-docker
* 04-portainer
* 05-wikijs
* 06-uptime-kuma
* 07-pfsense
* 08-active-directory
* 09-dns
* 10-tailscale
* 11-troubleshooting

---

## Status do Projeto

🟢 Ambiente operacional e em constante evolução.

Atualmente o laboratório possui virtualização, containers, monitoramento, firewall, Active Directory, DNS e acesso remoto seguro em funcionamento, servindo como plataforma para estudos, validação de tecnologias e documentação de boas práticas de infraestrutura corporativa.
