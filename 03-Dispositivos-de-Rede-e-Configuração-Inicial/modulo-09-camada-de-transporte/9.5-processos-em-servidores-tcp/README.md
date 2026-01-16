# Módulo 9.5 - Processos em Servidores TCP

Os servidores TCP são capazes de atender **múltiplos clientes simultaneamente**, mantendo sessões independentes para cada conexão, mesmo quando os serviços estão no mesmo servidor físico.

---

## 🖥️ Exemplo de Processos em Servidores TCP

### 📌 Cenário

- **Cliente 1** solicita serviços **Web (HTTP – porta 80)**
- **Cliente 2** solicita serviços de **Correio Eletrônico (SMTP – porta 25)**
- Ambos acessam o **mesmo servidor**

📌 O servidor diferencia as conexões utilizando:
- Endereço IP de origem
- Porta de origem
- Endereço IP de destino
- Porta de destino  

Cada comunicação é identificada por um **par de sockets**, permitindo que múltiplas sessões ocorram ao mesmo tempo sem conflito.

---

## 🔁 Estabelecimento de Conexão TCP (Three-Way Handshake)

O **handshake de três vias** é usado para estabelecer uma sessão TCP confiável entre dois hosts.

### ▶️ Etapa 1 – SYN
O cliente inicia a comunicação enviando um segmento com o flag **SYN** ativado.
SEQ=100 CTL=SYN

📌 Função:
- Solicitar o início da conexão
- Informar o número de sequência inicial

---

### ▶️ Etapa 2 – SYN + ACK
O servidor responde confirmando o recebimento do SYN e solicitando a sincronização.
SEQ=300 ACK=101 CTL=SYN, ACK 


📌 Função:
- Confirmar o SYN do cliente
- Informar seu próprio número de sequência
- Indicar que aceita a conexão

---

### ▶️ Etapa 3 – ACK
O cliente confirma o SYN do servidor.
SEQ=101 ACK=301 CTL=ACK 


📌 Resultado:
- A conexão TCP é **estabelecida**
- Os dados podem ser transmitidos

---

📌 O handshake de três vias valida que:
- O host de destino está disponível
- O serviço solicitado está ativo
- Ambos concordam com os números de sequência

---

## 🔒 Encerramento da Sessão TCP

Para encerrar uma conexão TCP de forma controlada, utiliza-se o flag **FIN**.

### ▶️ Etapa 1 – FIN
O cliente envia um segmento indicando que não há mais dados a transmitir.

CTL=FIN 


---

### ▶️ Etapa 2 – ACK
O servidor confirma o recebimento do FIN.

CTL=ACK 

---

### ▶️ Etapa 3 – FIN
O servidor também envia um FIN para encerrar sua parte da comunicação.

CTL=FIN 


---

### ▶️ Etapa 4 – ACK
O cliente confirma o FIN do servidor.

CTL=ACK


📌 Após isso, a sessão TCP é **finalizada corretamente**.

---

## 🔍 Análise do Handshake Triplo do TCP

- O TCP é um protocolo **orientado à conexão**
- Os hosts **mantêm estado** da sessão
- Cada segmento é rastreado por números de sequência
- Confirmações (ACK) garantem a confiabilidade

📌 O TCP é **full-duplex**, permitindo:
- Envio e recebimento simultâneo de dados

---

## 🎯 Funções do Handshake de Três Vias

O handshake de três vias:

- Estabelece que o dispositivo de destino está presente na rede
- Verifica se o serviço está ativo e aceitando conexões na porta solicitada
- Informa ao servidor que o cliente deseja estabelecer uma sessão naquele serviço

---

## 🚩 Campo de Bits de Controle (Flags TCP)

Os **bits de controle**, também chamados de **flags**, indicam o estado da comunicação TCP.

| Flag | Descrição |
|----|----------|
| **URG** | Indica que o campo de ponteiro urgente é válido |
| **ACK** | Confirmação de recebimento de dados |
| **PSH** | Solicita envio imediato dos dados ao aplicativo |
| **RST** | Redefine a conexão em caso de erro |
| **SYN** | Sincroniza números de sequência (início da conexão) |
| **FIN** | Indica que não há mais dados a enviar (encerramento) |

---

## 🔎 PSH e URG (Resumo)

- **PSH (Push)**:  
  Solicita que os dados sejam entregues imediatamente à aplicação, sem esperar o buffer encher.

- **URG (Urgent)**:  
  Indica que há dados urgentes no segmento, que devem ser processados com prioridade.

---

## ✅ Status do Módulo

- [x] Estudado
- [x] Documentado
- [x] Revisado

 
