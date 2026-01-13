# 🔁 Módulo 13 – O Processo de ARP (Address Resolution Protocol)

Este módulo explica como um dispositivo em uma rede local (LAN) associa **endereços IP (camada 3)** a **endereços MAC (camada 2)**, permitindo a entrega correta dos quadros Ethernet.

---

## 🧩 Endereços em uma LAN Ethernet

Em uma rede Ethernet, cada dispositivo possui dois tipos principais de endereços:

- **Endereço físico (MAC)**  
  Utilizado para comunicação **NIC para NIC** dentro da mesma rede local.

- **Endereço lógico (IP)**  
  Utilizado para identificar a origem e o destino dos pacotes IP, podendo estar:
  - Na mesma rede
  - Em uma rede remota

📌 O IP identifica *para onde ir*.  
📌 O MAC identifica *quem entrega localmente*.

---

## 🏠 Destino na Mesma Rede

Quando o dispositivo de destino está na **mesma rede IP**, ocorre o seguinte:

### 📦 Camada 2 – Quadro Ethernet
- **MAC de destino:** MAC do host final (ex: PC2 – 55-55-55)
- **MAC de origem:** MAC do host emissor (ex: PC1 – aa-aa-aa)

### 🌐 Camada 3 – Pacote IP
- **IP de origem:** IP do host emissor (ex: 192.168.10.10)
- **IP de destino:** IP do host destino (ex: 192.168.10.11)

➡️ Comunicação direta entre os hosts, sem envolver o roteador.

---

## 🌍 Destino em uma Rede Remota

Quando o endereço IP de destino está em **outra rede**:

- O **endereço IP de destino permanece o do host final**
- O **endereço MAC de destino passa a ser o do gateway padrão**
  - Ou seja, a interface do roteador conectada à LAN

📌 O quadro vai para o roteador, mas o pacote IP continua apontando para o destino final.

---

## 🔄 O que é o ARP?

O **ARP (Address Resolution Protocol)** é responsável por descobrir o **endereço MAC** correspondente a um **endereço IPv4 conhecido**, dentro da rede local.

📌 Para IPv6, esse processo é feito pelo **ICMPv6 Neighbor Discovery (ND)**.

---

## 🧠 Funcionamento do ARP (3 Etapas)

### 1️⃣ ARP Request (Broadcast)
- O host emissor envia um quadro para o **MAC de broadcast**
- A mensagem contém o **IP do host de destino**

### 2️⃣ ARP Reply (Unicast)
- O host que reconhece seu IP responde informando seu **endereço MAC**
- A resposta é enviada diretamente ao host solicitante

### 3️⃣ Tabela ARP
- O host emissor armazena a associação **IP ↔ MAC**
- Essa informação fica salva na **tabela ARP**

📌 Enquanto a entrada existir na tabela ARP, não é necessário repetir o broadcast.

---

## 📋 Tabela ARP

- Armazena associações entre:
  - Endereço IPv4
  - Endereço MAC
- Evita tráfego desnecessário de broadcast
- Possui tempo de expiração (aging)

---

## ⚠️ Dicas Importantes (Prova + Prática)

- 🔹 **ARP só funciona na rede local**
- 🔹 ARP **não atravessa roteadores**
- 🔹 Se não há MAC → não há comunicação Ethernet
- 🔹 Problemas de ARP causam falhas mesmo com IP correto
- 🔹 ARP spoofing é um ataque comum em redes locais

💡 Comando clássico de verificação:
- `arp -a`

---

## 🛡️ Importância para Cibersegurança

O ARP é fundamental para:
- Análise de tráfego em LAN
- Detecção de ataques MITM
- Monitoramento de redes internas
- Atuação em SOC / Blue Team
- Entendimento de ataques como ARP Poisoning

---

## 📌 Status do Módulo

✅ **Concluído**

---

> 💡 *Sem IP não há roteamento.  
Sem MAC não há entrega local.*
