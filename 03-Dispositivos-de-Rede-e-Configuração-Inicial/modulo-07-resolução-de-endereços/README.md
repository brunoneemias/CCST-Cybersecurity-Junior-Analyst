# Módulo 7 - Resolução de Endereços (ARP)

## Finalidade do ARP

O **ARP (Address Resolution Protocol)** tem como finalidade **associar um endereço IP (camada 3)** a um **endereço MAC (camada 2)** dentro de uma rede local (LAN).  
Sem o ARP, a comunicação Ethernet não seria possível, pois os quadros precisam de endereços MAC para serem entregues.

---

## 7.1.1 Visão Geral do ARP

- O ARP é usado **apenas em redes IPv4**.
- Atua entre a **Camada de Rede (IP)** e a **Camada de Enlace (Ethernet)**.
- Permite que um dispositivo descubra o **MAC de outro dispositivo** conhecendo apenas seu IP.

📌 IPv6 utiliza um mecanismo diferente: **ICMPv6 Neighbor Discovery (ND)**.

---

## 7.1.2 Funções do ARP

- Resolver endereços **IP → MAC**.
- Manter uma **tabela ARP** em cache para evitar requisições repetidas.
- Permitir comunicação eficiente dentro da LAN.
- Funcionar tanto para **destinos locais** quanto para **comunicações com redes remotas** (via gateway).

---

## 7.1.3 Operação ARP – Solicitação ARP

Quando um host precisa enviar dados e **não conhece o MAC de destino**:

1. O host envia uma **Solicitação ARP (ARP Request)** em **broadcast**.
2. O quadro Ethernet usa o MAC de destino: `FF:FF:FF:FF:FF:FF`.
3. A mensagem ARP pergunta:  
   *“Quem tem o IP X.X.X.X? Informe seu MAC.”*

📡 Todos os dispositivos da LAN recebem essa solicitação.

---

## 7.1.4 Operação ARP – Resposta ARP

1. O host que possui o IP solicitado responde com uma **Resposta ARP (ARP Reply)**.
2. A resposta é enviada em **unicast**, diretamente ao solicitante.
3. O MAC do host de destino é informado.
4. O host solicitante **armazena o mapeamento IP/MAC** na tabela ARP.

---

## 7.1.5 Função do ARP nas Comunicações Remotas

Quando o destino está **fora da rede local**:

- O host **não resolve o MAC do destino final**.
- Ele resolve o **MAC do gateway padrão** (roteador).
- O ARP é usado para descobrir o MAC da **interface do roteador**.
- O roteador então encaminha o pacote para a próxima rede.

📌 O ARP **nunca atravessa roteadores**.

---

## 7.1.6 Remoção de Entradas de uma Tabela ARP

- As entradas ARP são armazenadas em **cache temporário**.
- Após um período de inatividade, elas são removidas automaticamente.
- Isso evita:
  - Uso de informações desatualizadas
  - Crescimento excessivo da tabela

Também podem ser removidas **manualmente** via comandos.

---

## 7.1.7 Tabelas ARP nos Dispositivos

### 💻 PC (Windows)

Exibe a tabela ARP atual.
```bash
arp -a
```

Remove todas as entradas ARP.
```bash
arp -d *
```

###  🖧 Roteador Cisco

Exibe a tabela ARP do roteador.
```bash
show ip arp
```

Limpa o cache ARP.
```bash
clear arp-cache
```
--- 
## 7.1.8 Problemas de ARP
### 📢 Broadcast Excessivo de ARP
- Muitas solicitações ARP podem gerar tráfego desnecessário.
- Impacta desempenho em redes grandes.
- Pode indicar:
      - Configuração incorreta
      - Loops de rede
      - Falta de segmentação (VLANs)

--- 

### ⚠️ Falsificação de ARP (ARP Spoofing / ARP Poisoning) 
- Ataque onde um invasor envia respostas ARP falsas.
- Associa seu MAC ao IP de outro dispositivo (ex: gateway).
- Pode permitir:
  - Ataques Man-in-the-Middle (MITM)
  - Interceptação de tráfego
  - Roubo de credenciais
    
### 🔐 Mitigações: 
  - ARP Inspection
  - VLANs
  - Segurança em switches
  - Uso de protocolos criptografados (HTTPS, SSH)

---  
## Status
-  ✅  Estudado

