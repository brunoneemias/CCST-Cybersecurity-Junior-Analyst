# Módulo 9.4 - Números de Porta

Os protocolos da camada de transporte **TCP e UDP** utilizam **números de porta** para permitir que múltiplas conversas ocorram simultaneamente em um mesmo dispositivo.

Cada aplicação em execução em um host utiliza um número de porta específico para enviar e receber dados.

---

## 🔌 Pares de Sockets

As **portas de origem e destino** são colocadas no segmento da camada de transporte.  
Esse segmento é encapsulado em um **pacote IP**, que contém os endereços IP de origem e destino.

A combinação de:
- **Endereço IP + número da porta**

é chamada de **socket**.

### 📌 Exemplo de sockets

- **Socket de origem (cliente):**
192.168.1.5:1099 

- **Socket de destino (servidor web):**
192.168.1.7:80 

### 🔗 Par de sockets

Juntos, esses dois sockets formam um **par de sockets**, que identifica de forma única a comunicação:
192.168.1.5:1099 , 192.168.1.7:80 

📌 Esse par identifica:
- Quem está se comunicando
- Qual aplicação está envolvida
- Em qual direção os dados estão fluindo

---

## 📊 Grupos de Números de Portas

Os números de porta são divididos em grupos padronizados.

| Grupo de Portas | Intervalo | Descrição |
|---------------|---------|-----------|
| **Portas Bem Conhecidas (Well-Known Ports)** | 0 – 1023 | Usadas por serviços padrão e controladas pela IANA |
| **Portas Registradas (Registered Ports)** | 1024 – 49151 | Usadas por aplicações e serviços específicos |
| **Portas Dinâmicas ou Privadas** | 49152 – 65535 | Usadas temporariamente por clientes |

---

## 🌐 Portas Conhecidas Comuns e Aplicações

| Número da Porta | Protocolo | Aplicação |
|----------------|----------|-----------|
| 20 | TCP | FTP (Dados) |
| 21 | TCP | FTP (Controle) |
| 22 | TCP | SSH |
| 23 | TCP | Telnet |
| 25 | TCP | SMTP |
| 53 | TCP / UDP | DNS |
| 67 | UDP | DHCP (Servidor) |
| 68 | UDP | DHCP (Cliente) |
| 69 | UDP | TFTP |
| 80 | TCP | HTTP |
| 110 | TCP | POP3 |
| 123 | UDP | NTP |
| 143 | TCP | IMAP |
| 161 | UDP | SNMP |
| 443 | TCP | HTTPS |
| 5060 | UDP / TCP | VoIP (SIP) |

---

## 🖥️ O Comando `netstat`

Conexões TCP desconhecidas podem representar uma **ameaça de segurança**, pois podem indicar:
- Malware
- Backdoors
- Conexões não autorizadas

Por isso, muitas vezes é necessário verificar **quais conexões TCP ativas** estão abertas em um host.

### 📌 Função do `netstat`

O comando `netstat` permite:
- Visualizar conexões ativas
- Ver portas em escuta
- Identificar serviços em execução

### 🔍 Resolução de nomes

Por padrão, o `netstat`:
- Tenta resolver **endereços IP para nomes de domínio**
- Tenta resolver **números de porta para nomes de aplicações conhecidas**

### ⚙️ Opção `-n`

A opção `-n` força a exibição **numérica**, sem resolução de nomes:

```bash
netstat -n
```
📌 Útil para:
- Análise de segurança
- Resposta a incidentes
- Diagnóstico rápido de rede 

## ✅ Status do Módulo

- [x] Estudado
- [x] Documentado
- [x] Pronto para revisão e certificação
