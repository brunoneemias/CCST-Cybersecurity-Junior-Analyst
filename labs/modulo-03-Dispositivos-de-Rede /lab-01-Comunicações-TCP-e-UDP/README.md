# Laboratório: Comunicações TCP e UDP - Packet Tracer

## Objetivos

- **Parte 1:** Gerar tráfego de rede no modo de simulação.
- **Parte 2:** Examinar a funcionalidade dos protocolos TCP e UDP.
- Visualizar multiplexação e função de números de porta.
- Entender confiabilidade do TCP e comportamento não confiável do UDP.

---

## Materiais / Recursos

- Cisco Packet Tracer
- Topologia de rede.
- PCs clientes: HTTP Client, FTP Client, DNS Client, E-Mail Client
- Servidor MultiServer
- ![Topologia da rede](capturas/02%20-%20Topologia%20da%20rede.png)


---

## Parte 1: Gerar Tráfego no Modo de Simulação

### Etapa 1: Preencher tabelas ARP
1. No **MultiServer**, abra **Desktop → Prompt de Comando**.
2. Execute:  
   ```bash
   ping -n 1 192.168.1.255
    ```
Este ping no endereço de broadcast da LAN cria entradas ARP nos dispositivos.

---

### Etapa 2: Tráfego HTTP

1. No packet tracer mudar para o modo simulação. 
2. No Cliente HTTP, abra o navegador.
3. Acesse: http://192.168.1.254.
4. Observe as PDUs no modo de simulação.

---

### Etapa 3: Tráfego FTP
1. No Cliente FTP, abra o Prompt de Comando.
2. Digite:
     ```bash
     ftp 192.168.1.254
     ```
3. Observe as PDUs no modo de simulação.

---

### Etapa 4: Tráfego DNS
1. No Cliente DNS, abra o Prompt de Comando.
2. Digite:
     ```bash
     nslookup multiserver.pt.ptu
     ```
3. Observe a PDU no painel de simulação. 

---

### Etapa 5: Tráfego de e-mail
1. No E-Mail Client, abra Compose.
2. Digite:
     ```bash
     nslookup multiserver.pt.ptu
     ```
3. Observe a PDU no painel de simulação. 

---

### Etapa 6: Preparação para Simulação
- Certifique-se de que todas as PDUs estão no painel de simulação.
- imagem das PDUs aqui 
---

### Etapa 7: Multiplexação de conversações
- Use o botão Capturar/Avançar (>|) para observar PDUs atravessando a rede.
- Observe que apenas uma PDU pode passar por um fio em cada direção simultaneamente.
- Isso acontece por conta da multiplexação de conversações, abaixo temos alguns modos de comunicação:
### 📡 Modos de Comunicação
| Modo          | Definição                                                                 | Exemplo prático                  | Vantagens                         | Limitações                        |
|---------------|---------------------------------------------------------------------------|----------------------------------|-----------------------------------|-----------------------------------|
| **Simplex**   | Comunicação em **uma única direção**. O receptor não consegue responder.   | Televisão, rádio FM              | Simples e barato                  | Sem interação; apenas recepção     |
| **Half Duplex** | Comunicação em **ambas as direções**, mas **não simultânea**. Apenas um transmite por vez. | Walkie-talkie, rede Ethernet antiga (hub) | Permite troca de mensagens        | Mais lento; pode haver colisões    |
| **Full Duplex** | Comunicação em **ambas as direções simultaneamente**.                   | Telefone, switches Ethernet modernos | Alta eficiência; sem colisões     | Requer tecnologia mais avançada    |

> 🔎 Resumindo:  
> - **Simplex** → só envia.  
> - **Half Duplex** → envia e recebe, mas alternado.  
> - **Full Duplex** → envia e recebe ao mesmo tempo.

### 🎨 Cores das PDUs no Painel de Simulação

| Cor      | Significado                                      | Exemplo de PDU              |
|----------|--------------------------------------------------|-----------------------------|
| 🟩 Verde | Camada de Rede (Network Layer)                   | Pacotes IP                  |
| 🟦 Azul  | Camada de Transporte (Transport Layer)           | Segmentos TCP/UDP           |
| 🟪 Roxo  | Camada de Aplicação (Application Layer)          | HTTP, DNS, SMTP             |
| ⬛ Preto | Camada de Enlace/Dados (Data Link Layer)          | Quadros Ethernet            |
| 🟥 Vermelho | Camada Física ou Erro/Falha na transmissão    | Problemas de entrega física |

> Cada cor ajuda a identificar rapidamente em qual **camada do modelo OSI** a PDU está atuando durante a simulação.
    
---

## Parte 2: Funcionalidade TCP e UDP
### Tráfego HTTP (TCP) 
1. Filtre para HTTP e TCP. (imagem no filtro aqui) 
2. Abra o navegador no Cliente HTTP e acesse 192.168.1.254.
3. Observe:
   - Cor das PDUs
   - SRC PORT, DEST PORT, SEQUENCE NUM, ACK NUM
   - Sinalizadores TCP: URG, ACK, PSH, RST, SYN, FIN
4. Observe diferenças entre PDU de saída e entrada.
5. Imagem aqui da PDU e sinalizadores marcados 

### 🚩 Campo Flags no TCP

O campo **Flags** (ou **Sinalizadores**) no cabeçalho TCP é composto por bits que controlam o estado da conexão.  
Cada bit pode estar **ativo (1)** ou **inativo (0)**, e mais de uma flag pode ser definida ao mesmo tempo.

### 📑 Mapeamento das Flags TCP

| Bit (binário) | Flag | Nome completo   | Função |
|---------------|------|-----------------|--------|
| `000001`      | FIN  | Finish          | Finaliza a conexão TCP de forma ordenada |
| `000010`      | SYN  | Synchronize     | Inicia a conexão (sincronização de números de sequência) |
| `000100`      | RST  | Reset           | Reinicia/aborta a conexão TCP |
| `001000`      | PSH  | Push            | Solicita entrega imediata dos dados à aplicação |
| `010000`      | ACK  | Acknowledgment  | Confirma recebimento de dados |
| `100000`      | URG  | Urgent          | Indica dados urgentes que devem ser priorizados |

### 🔎 Exemplo de Decodificação

**FLAGS: `0b00011000`**

- `001000` → **PSH** (Push: entrega imediata dos dados à aplicação)  
- `010000` → **ACK** (Acknowledgment: confirma recebimento dos dados anteriores)  

👉 Isso significa que o segmento TCP está **confirmando recebimento (ACK)** e ao mesmo tempo pedindo para que os dados sejam **entregues imediatamente à aplicação (PSH)**.

### 📌 Resumo

- As **flags TCP** são fundamentais para o controle da conexão.  
- Elas permitem iniciar, manter e encerrar comunicações de forma confiável.  
- O uso combinado de flags define o comportamento de cada segmento TCP.

---

### Tráfego FTP (TCP) 
1. Filtre para FTP e TCP. inserir imagem aqui 
2. Abra Prompt de Comando → ftp 192.168.1.254.
3. Registre:
   - Números de porta, sequência e ACK
   - Sinalizadores TCP
   - Diferença entre PDU de saída e entrada
   - inserir imagem do dados, e mensagem do FTP 
4. Observe cores diferentes para cada PDU.

--- 

### Tráfego DNS (UDP)
1. Filtre para DNS e UDP.. inserir imagem aqui 
2. Execute nslookup multiserver.pt.ptu.
3. Registre:
   - Protocolo da camada 4: UDP
   - SRC PORT e DEST PORT
   - Não há números de sequência nem de ACK
   - inserir imagem do dados, e mensagem do FTP 
4. Observe PDU de retorno e compare endereços e portas.

---  

### Tráfego de E-mail (TCP)
1. Filtre para POP3, SMTP e TCP. inserir imagem aqui 
2. Envie e-mail para user@multiserver.pt.ptu
3. Registre:
   - Protocolo de transporte: TCP
   - Confiabilidade: sim, entrega garantida
   - Não há números de sequência nem de ACK
   - SRC PORT, DEST PORT, SEQUENCE NUM e ACK NUM
   - Bandeiras TCP definidas: SYN, ACK, FIN conforme etapa
4. Compare PDU de saída e entrada para entender o fluxo.

---   

### Observações / Conceitos Importantes 
- TCP: confiável, entrega ordenada, controle de fluxo e retransmissão de segmentos perdidos.
- UDP: não confiável, entrega "best effort", sem reordenação ou retransmissão.
- Multiplexação: permite que múltiplas aplicações usem a mesma rede simultaneamente usando portas diferentes.
- Números de porta: SRC PORT e DEST PORT definem qual aplicação enviou e qual recebeu.
- Sinalizadores TCP: URG, ACK, PSH, RST, SYN, FIN controlam o fluxo e estabelecimento/encerramento da sessão.

---   

### ✅ Check de aprendizado
 -  Gerar tráfego TCP e UDP
 -  Visualizar multiplexação
 - Examinar SRC/DEST PORT, SEQ e ACK
 - Diferenciar confiabilidade TCP x UDP
 - Interpretar sinalizadores TCP e comportamento de UDP




