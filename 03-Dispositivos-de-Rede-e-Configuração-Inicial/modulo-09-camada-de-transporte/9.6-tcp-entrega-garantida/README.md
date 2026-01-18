# Módulo 9.6 - Confiabilidade TCP: Entrega Garantida e Ordenada

O TCP garante **entrega confiável, ordenada e sem perdas** dos dados entre duas aplicações, mesmo que os segmentos percorram rotas diferentes na rede.

---

## 🔢 Número de Sequência Inicial (ISN)

- Cada sessão TCP define um **ISN (Initial Sequence Number)** aleatório.
- Permite identificar o **primeiro byte de dados** transmitido e ajuda a prevenir ataques maliciosos.
- Analogia: é como começar a numerar cartas de uma correspondência com um número secreto para evitar fraudes.

---

## 📦 Segmentos fora de ordem

- Segmentos podem chegar fora da ordem devido a diferentes rotas.
- O receptor coloca os segmentos em **um buffer** e remonta os dados na ordem correta.
- Segmentos fora de ordem são retidos até que os bytes faltantes cheguem.

---

## 🔄 Perda e Retransmissão de Dados

- Cada segmento tem um **tamanho máximo (MSS)**, normalmente 1460 bytes no IPv4.
- O TCP usa **SEQ** e **ACK** para confirmar recebimento:
  - SEQ = primeiro byte do segmento
  - ACK = próximo byte esperado pelo receptor
- **Confirmação antecipatória (ACK)**: indica ao emissor que ele pode enviar o próximo segmento.

### 🎯 Reconhecimento Seletivo (SACK)

- Permite ao receptor informar exatamente quais segmentos chegaram.
- Apenas os segmentos faltantes são retransmitidos, evitando duplicação e congestionamento.
- Analogia: é como marcar quais capítulos de um livro já foram entregues, e só reenviar os capítulos faltantes.

---

## 📏 Janela de envio (Sliding Window)

- Determina quantos bytes podem ser enviados antes de receber ACK.
- **Janela deslizante**: o receptor confirma partes recebidas, permitindo que o emissor continue enviando sem esperar toda a transmissão.
- Tamanho da Janela ajustável de acordo com a **capacidade do buffer do receptor**.

### 💡 Exemplo simplificado

- MSS = 1460 bytes
- PC A envia 10.000 bytes, PC B confirma recebimento parcial.
- A janela de envio de A "desliza" e permite enviar mais dados conforme ACKs chegam.

---

## ⚠️ Prevenção de Congestionamento

- Redes congestionadas podem descartar pacotes.
- Retransmissões não controladas podem **agravar o congestionamento**.
- O TCP ajusta:
  - Quantidade de bytes enviados antes da confirmação
  - Temporizadores de retransmissão
  - Algoritmos para controlar congestionamento

📌 Analogia: é como reduzir a velocidade de envio de cartas se o correio estiver sobrecarregado, para evitar perder correspondências.

---

## ✅ Resumo de Conceitos-Chave

| Conceito | Função/Descrição |
| --- | --- |
| ISN | Número de sequência inicial, garante identificação de bytes e segurança |
| MSS | Tamanho máximo de segmento, padrão 1460 bytes em IPv4 |
| SEQ / ACK | Sequência e confirmação de bytes para entrega confiável |
| SACK | Reconhecimento seletivo: retransmitir apenas dados faltantes |
| Janela deslizante | Permite transmissão contínua enquanto receptor confirma segmentos |
| Controle de congestionamento | Ajusta envio de bytes para evitar sobrecarga na rede |

---

## ✅ Status do Módulo

- [x] Estudado
- [x] Documentado
- [x] Revisado
