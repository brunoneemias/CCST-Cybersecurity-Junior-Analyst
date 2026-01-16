# Módulo 9.3 - Visão Geral do UDP

O **UDP (User Datagram Protocol)** é um protocolo da camada de transporte que fornece comunicação **rápida e de melhor esforço**, sem garantia de entrega, ordem ou controle de sessão.

---

## ⚡ Recursos do UDP

O UDP possui as seguintes características:

- **Os dados são reagrupados na ordem em que são recebidos**
  - Não há controle de sequência
- **Segmentos perdidos não são reenviados**
  - Não existe confirmação de recebimento (ACK)
- **Não estabelece sessão**
  - Não há handshake antes da comunicação
- **O envio não é informado sobre a disponibilidade do recurso**
  - Não há controle de fluxo ou congestionamento

📌 O foco do UDP é **baixa latência e simplicidade**, não confiabilidade.

---

## 📦 Cabeçalho UDP

O UDP é um **protocolo sem estado**, o que significa que **nem o cliente nem o servidor mantêm informações sobre a sessão de comunicação**.

- Os blocos de comunicação no UDP são chamados de **datagramas** (ou segmentos)
- Os datagramas são enviados como **melhor esforço** pelo protocolo da camada de transporte

O **cabeçalho UDP é muito mais simples que o TCP**, pois:

- Possui apenas **4 campos**
- Usa apenas **8 bytes (64 bits)** de sobrecarga

---

## 🧾 Campos do Cabeçalho UDP

| Campo | Função |
|------|------|
| **Porta de origem** | Identifica a aplicação que envia os dados |
| **Porta de destino** | Identifica a aplicação que recebe os dados |
| **Comprimento** | Indica o tamanho total do datagrama UDP (cabeçalho + dados) |
| **Checksum** | Verifica erros no datagrama (opcional no IPv4 e obrigatório no IPv6) |

---

## 🌐 Aplicações que Usam UDP

UDP é utilizado quando **velocidade é mais importante que confiabilidade**:

- **DNS** (resolução de nomes)
- **DHCP** (configuração automática de IP)
- **TFTP** (transferência simples de arquivos)
- **VoIP** (voz sobre IP)
- **Streaming de áudio e vídeo**
- **Jogos online**

---

## 🔄 UDP e TCP no DNS e SNMP

Embora **DNS e SNMP usem UDP por padrão**, ambos **podem usar TCP** em situações específicas:

- **DNS usa TCP quando:**
  - A solicitação ou resposta é **maior que 512 bytes**
  - Transferência de zonas DNS (AXFR)
- **SNMP pode usar TCP:**
  - Quando o administrador precisa de **mais confiabilidade**
  - Em ambientes críticos ou de gerenciamento centralizado

---

## ⚖️ UDP x TCP (Resumo)

- **UDP** → rápido, simples, sem garantia
- **TCP** → confiável, controlado, orientado à conexão

---

## ✅ Status do Módulo

- [x] Estudado
- [x] Documentado
- [x] Pronto para revisão e certificação
