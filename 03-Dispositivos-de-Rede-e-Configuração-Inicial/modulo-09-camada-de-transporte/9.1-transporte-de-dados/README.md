# Módulo 9.1 - Camada de Transporte (Resumo Essencial)

A **camada de transporte** é responsável por **garantir a comunicação entre aplicações**, controlando como os dados são enviados, recebidos e organizados entre dispositivos na rede.

---

## 🎯 Propósito da Camada de Transporte

- Atua como um **elo entre a camada de aplicação e as camadas inferiores**
- Permite que **múltiplas aplicações** utilizem a rede ao mesmo tempo
- Garante que os dados cheguem:
  - Ao **destino correto**
  - À **aplicação correta**
  - Na **ordem adequada** (quando necessário)

---

## 🔗 Funções Principais

### 📌 Rastreamento de Conversações
- Identifica comunicações individuais entre aplicações
- Usa **números de porta** para diferenciar serviços e conexões

### 📦 Segmentação e Remontagem
- Dados grandes são **divididos em segmentos**
- No destino, os segmentos são **reorganizados e remontados**

### 🧾 Cabeçalho de Transporte
Adiciona informações como:
- Porta de origem
- Porta de destino
- Controle de sequência
- Controle de erros (dependendo do protocolo)

### 🔀 Multiplexação
- Permite várias conversas simultâneas usando o mesmo IP
- Diferencia cada aplicação pelo **número de porta**

---

## 🚚 Protocolos da Camada de Transporte

### 🔒 TCP (Transmission Control Protocol)

✔ **Confiável e orientado à conexão**

Principais características:
- Divide os dados em **segmentos**
- Numera e rastreia os segmentos
- Confirma dados recebidos (ACK)
- Reenvia dados perdidos
- Reorganiza segmentos fora de ordem
- Controla fluxo e congestionamento

📌 Ideal quando **integridade e confiabilidade** são prioridade.

Exemplos:
- HTTP / HTTPS
- FTP
- SMTP, POP3, IMAP
- Streaming de vídeo armazenado

---

### 🚀 UDP (User Datagram Protocol)

❌ **Sem conexão e não confiável**

Principais características:
- Divide dados em **datagramas**
- Não confirma recebimento
- Não reenvia pacotes perdidos
- Menor sobrecarga → mais rápido

📌 Ideal quando **velocidade é mais importante que confiabilidade**.

Exemplos:
- VoIP
- Jogos online
- Streaming ao vivo
- DNS

➡ **Nota:** O DNS utiliza UDP por ser rápido e leve, ideal para consultas curtas.

---

## 🎯 Escolhendo o Protocolo Correto

Os desenvolvedores escolhem o protocolo conforme a necessidade da aplicação:

- 📹 **Vídeo armazenado** → geralmente **TCP**
  - Permite buffer
  - Controle de congestionamento
  - Melhor experiência ao usuário

- 🎙️ **Voz e vídeo em tempo real** → geralmente **UDP**
  - Menor latência
  - Aceita pequenas perdas

⚠️ Alguns aplicativos:
- Usam **UDP por padrão**
- Mudam para **TCP** se o firewall bloquear UDP

---

## ✅ Status do Módulo

- [x] Estudado
- [x] Resumido
- [x] Documentado no GitHub
