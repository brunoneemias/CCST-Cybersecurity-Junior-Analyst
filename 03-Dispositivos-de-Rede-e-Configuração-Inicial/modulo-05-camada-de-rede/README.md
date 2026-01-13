# Módulo 5 - Camada de Rede

Este módulo aborda a **Camada de Rede** do modelo OSI, focando em IPv4, IPv6, encapsulamento e características principais da camada de rede.

---

## 🌐 5.1 Características da Camada de Rede

A camada de rede é responsável por **rotear pacotes de dados** do host de origem até o destino final, atravessando uma ou mais redes físicas.

### Principais características:

- **Sem Conexão:** não há necessidade de estabelecer conexão antes do envio.  
  - **Analogia:** enviar uma carta sem avisar o destinatário.  
  - **Rede:** cada pacote é roteado independentemente.  

- **Melhor esforço (Best Effort):** a rede tenta entregar pacotes, mas não garante entrega ou ordem.  

- **Independente de mídia:** funciona sobre qualquer tipo de mídia de rede (cabo, fibra, wireless).  

---

## 🔗 5.1.3 Encapsulamento IP

O processo de **encapsulamento** envolve **envolver os dados da camada superior** (como TCP/UDP) em um pacote de camada de rede, que é depois colocado em um quadro da camada de enlace.

```mermaid
flowchart LR
A[Dados da Camada de Transporte] --> B[Encapsulados em Pacote IP]
B --> C[Encapsulados em Quadro Ethernet]
C --> D[Transmitido pela mídia física]
``` 

---

### 5.1.2 Protocolos IP

- **IPv4:**  
  - Endereçamento de 32 bits  
  - Hierárquico (rede + host)  
  - Amplamente usado  

- **IPv6:**  
  - Endereçamento de 128 bits  
  - Criado para expandir o número de endereços  
  - Simplifica roteamento e elimina fragmentação obrigatória  

---

### 5.1.3 Encapsulamento IP

O **pacote IP** contém:

- Endereço IP de **origem** e **destino**
- Informações de roteamento
- Dados da **camada de transporte** encapsulados
- Campos de controle para fragmentação e TTL

---

### 5.1.4 Características do IP

- **Sem conexão:** Cada pacote é independente  
  - Analogia: como enviar cartas sem saber se a pessoa vai receber  
- **Melhor esforço:** IP **não garante entrega, ordem ou integridade**  
- **Independente de mídia:** Funciona sobre Ethernet, Wi-Fi, fibra óptica, etc.

---

## 5.2 Cabeçalho do Pacote IPv4

### 5.2.1 Campos do Cabeçalho IPv4

| Campo | Descrição |
| --- | --- |
| Versão | Versão do protocolo (IPv4 = 4) |
| IHL | Tamanho do cabeçalho |
| Tipo de Serviço (ToS) | Prioridade e QoS |
| Comprimento Total | Comprimento do pacote inteiro |
| Identificação | Para fragmentação |
| Flags | Controle de fragmentação |
| Fragment Offset | Posição do fragmento |
| TTL | Tempo de vida do pacote |
| Protocolo | Indica TCP, UDP ou outro |
| Checksum | Verificação de integridade do cabeçalho |
| Endereço IP de Origem | IP do remetente |
| Endereço IP de Destino | IP do destinatário |
| Opções | Campos opcionais, se houver |

---

## 5.3 Pacote IPv6

- Cabeçalho simplificado em relação ao IPv4
- Campos principais:

| Campo | Descrição |
| --- | --- |
| Versão | IPv6 = 6 |
| Classe de Tráfego | Prioridade e QoS |
| Label de Fluxo | Identificação de fluxo de pacotes |
| Comprimento do Payload | Tamanho dos dados |
| Próximo Cabeçalho | Indica protocolo da camada superior |
| Hop Limit | Semelhante ao TTL |
| Endereço de Origem | IP do remetente |
| Endereço de Destino | IP do destinatário |

### 5.3.3 Comparação IPv4 x IPv6

- IPv6 elimina campos opcionais e fragmentação no cabeçalho principal  
- IPv6 **melhora roteamento** e simplifica processamento de pacotes  
- Ambos utilizam encapsulamento para transmitir dados da camada de transporte

---

✅ **Resumo prático**

- **Encapsulamento:** Transporte → Rede → Enlace → Física  
- **IPv4:** Mais usado, menor espaço de endereçamento  
- **IPv6:** Expansão de endereços, cabeçalho simplificado  
- **Características IP:** Sem conexão, melhor esforço, independente de mídia
