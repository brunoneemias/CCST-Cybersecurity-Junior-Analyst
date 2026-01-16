# Módulo 9.2 - Visão Geral do TCP

O **TCP (Transmission Control Protocol)** é um protocolo da camada de transporte que fornece **comunicação confiável, ordenada e controlada** entre aplicações em rede.

---

## 🔐 Características do TCP

O TCP:

- **Estabelece uma sessão**
  - Usa o **handshake de três vias** para iniciar a comunicação
- **Garante entrega confiável**
  - Confirma o recebimento dos dados (ACK)
  - Reenvia segmentos perdidos
- **Fornece entrega na ordem correta**
  - Numera os segmentos para remontagem adequada
- **Suporta controle de fluxo**
  - Ajusta a taxa de envio conforme a capacidade do receptor

📌 Para detalhes completos, consulte o **RFC 793**, documento oficial que define o funcionamento do TCP.

---

## 📦 Cabeçalho TCP

Cada **segmento TCP** adiciona **20 bytes (160 bits)** de sobrecarga ao encapsular os dados da camada de aplicação.

---

## 🧾 Campos do Cabeçalho TCP (Resumo)

| Campo | Função |
|------|------|
| **Porta de origem** | Identifica a aplicação que envia os dados |
| **Porta de destino** | Identifica a aplicação que recebe os dados |
| **Número de sequência** | Garante a ordem correta dos segmentos |
| **Número de confirmação (ACK)** | Confirma o recebimento dos dados |
| **Comprimento do cabeçalho** | Indica o tamanho do cabeçalho TCP |
| **Flags (bits de controle)** | Controlam a conexão (SYN, ACK, FIN, RST, etc.) |
| **Tamanho da janela** | Define quanto dado pode ser enviado sem confirmação |
| **Checksum** | Verifica erros no segmento |
| **Ponteiro urgente** | Indica dados urgentes (uso raro atualmente) |

---

## 🚦 Controle de Fluxo no TCP

- Evita que o remetente envie dados mais rápido do que o receptor consegue processar
- Usa o **tamanho da janela** para ajustar dinamicamente a taxa de envio
- Ajuda a prevenir **congestionamento e perda de dados**

---

## 🌐 Aplicações que Usam TCP

TCP é usado quando **confiabilidade e integridade dos dados são essenciais**:

- **HTTP / HTTPS** (web)
- **FTP** (transferência de arquivos)
- **SMTP, POP3, IMAP** (e-mail)
- **SSH** (acesso remoto seguro)
- **Banco de dados** (MySQL, PostgreSQL, etc.)

---

## ✅ Status do Módulo

- [x] Estudado
- [x] Documentado
- [x] Pronto para revisão e certificação
