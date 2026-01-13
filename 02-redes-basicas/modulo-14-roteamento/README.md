# 🌐 Módulo 14 – Roteamento entre Redes e NAT

Este módulo aborda conceitos essenciais de **roteamento**, **gateway padrão** e **Network Address Translation (NAT)** em redes IPv4.

---

## 🏠 Gateway padrão

Todo host em uma rede local precisa conhecer **o endereço do roteador (gateway padrão)** para se comunicar com outras redes, incluindo a Internet.

- O **gateway padrão** é o "portão de saída" da LAN.
- Pode ser configurado:
  - **Estático:** definido manualmente no host
  - **Dinâmico:** fornecido pelo DHCP do roteador

📌 Dispositivos locais como impressoras normalmente não precisam de gateway, a menos que precisem se comunicar com redes externas.

---

## 📍 Descobrindo o gateway padrão

### Windows
    ipconfig

### Linux
    ip route
    # ou
    ip r
### macOS 
    netstat -nr | grep default
    # ou
    route get default
O IP listado é o gateway padrão.

---

## 💡 Por que endereços IP podem ser diferentes, mas máscara e gateway iguais?

1. IP diferente: Cada dispositivo precisa de um IP único dentro da rede (como números de apartamento).

2. Máscara de sub-rede igual: Define a porção de rede e a porção de host. Todos com a mesma máscara estão na mesma rede lógica.

- Exemplo: IPs 192.168.1.10, 192.168.1.20, 192.168.1.30

- Máscara: 255.255.255.0 → rede: 192.168.1.0

3. Gateway igual: Todos usam o mesmo roteador para acessar redes externas.

---

## 🔄 NAT (Network Address Translation)

O NAT permite que vários dispositivos usem um único IP público para acessar a Internet.

Como funciona:

- O roteador recebe um IP público do ISP.

- Dispositivos internos recebem IPs privados.

- Quando um host envia um pacote para a Internet:

1. O roteador substitui o IP de origem privado pelo IP público.

2. Roteia o pacote para a Internet.

- Quando a resposta retorna, o roteador reverte a tradução para o IP privado original.

📌 NAT só afeta pacotes destinados a outras redes.

---

## 🛠️ Exemplo prático

LAN de escritório:

- IPs diferentes para cada host (192.168.1.x)

- Máscara: 255.255.255.0

- Gateway: 192.168.1.1 (roteador)

- NAT ativado no roteador → todos compartilham o mesmo IP público

 📌 Desafio real: planejamento físico da infraestrutura e topologia correta da rede.
---

##  📌 Status do Módulo

✅ Concluído

--- 

> 💡 *O roteamento correto e o NAT garantem que sua rede local se comunique com outras redes e a Internet de forma eficiente e segura.*
