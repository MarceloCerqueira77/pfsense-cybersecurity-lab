# 🛡️ Laboratório de Cibersegurança & Defesa em Profundidade com pfSense

Este projeto documenta a implementação e validação de um ambiente de rede seguro utilizando o **pfSense CE**, focado em prevenção contra ameaças, controlo de acessos, VPN segura e monitorização de tráfego com IDS/IPS em tempo real.

---

## 📐 Topologia do Ambiente

- **Firewall/Gateway:** pfSense CE (Interfaces WAN e LAN)
- **Rede Interna (LAN):** `192.168.1.0/24`
- **Cliente de Testes/Ataques Simulados:** VM Ubuntu Linux (`192.168.1.50`)
- **Hipervisor:** Oracle VirtualBox / Ambiente Virtualizado

---

## 🛠️ Módulos Implementados

### 🟢 Módulo 1: Firewall & Regras de Filtragem
- Configuração de regras de entrada e saída por segmento de rede.
- Filtragem de tráfego baseada em portas, IPs e protocolos.
- Políticas de NAT e segurança no perímetro.

### 🟡 Módulo 2: Bloqueio de Ameaças com pfBlockerNG
- Implementação de listas de reputação de IP/DNS (*Feeds* de Cibersegurança).
- Filtragem de domínios maliciosos e *ad-blocking* (DNSBL).
- Controlo geográfico de tráfego via **GeoIP**.

### 🔵 Módulo 3: Acesso Remoto Seguro com OpenVPN
- Configuração de servidor OpenVPN para acesso de utilizadores remotos.
- Gestão de infraestrutura de chaves públicas (PKI) e certificados digitais.
- Encaminhamento seguro de tráfego e políticas de túnel.

### 🔴 Módulo 4: Deteção de Intrusões com Suricata (IDS/IPS)
- Implementação do **Suricata** na interface LAN para inspeção profunda de pacotes (*Deep Packet Inspection*).
- Carregamento de assinaturas e conjuntos de regras do **ET Open (Emerging Threats)**.
- Validação prática de captura de eventos, alertas de tráfego suspicious/APT e testes de conformidade utilizando a VM Ubuntu.

---

## 📊 Evidências de Validação

| Serviço | Estado | Descrição da Validação |
| :--- | :---: | :--- |
| **pfSense Firewall** |  Ativo | Tráfego filtrado de acordo com as regras de LAN/WAN |
| **pfBlockerNG** |  Ativo | Bloqueio preventivo de domínios/IPs maliciosos |
| **OpenVPN** |  Ativo | Conexão remota autenticada via certificado |
| **Suricata IDS** |  Ativo | Alertas e inspeção de tráfego HTTP/APT registados na LAN |

---

## 🛠️ Tecnologias Utilizadas

- **OS/Security Platform:** pfSense CE
- **IDS/IPS Engine:** Suricata
- **VPN:** OpenVPN
- **DNS/IP Filtering:** pfBlockerNG
- **Sistemas Operativos:** Ubuntu Linux, Windows
- **Redes & Ferramentas:** TCP/IP, `wget`, `curl`, VirtualBox, PKI/SSL

---
*Desenvolvido para fins de estudo, portfólio e validação técnica em Cibersegurança.*
