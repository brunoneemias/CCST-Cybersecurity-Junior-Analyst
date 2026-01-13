# 🔁 Módulo 15 – TCP e UDP

Este módulo aborda os **protocolos da Camada de Transporte**, responsáveis por garantir (ou não) a entrega dos dados entre origem e destino.

---

## 📦 Protocolos de Transporte

TCP e UDP operam de formas diferentes, sendo escolhidos conforme a necessidade da aplicação.

---

## ✅ TCP (Transmission Control Protocol)

✔ **Confiável e orientado à conexão**

- Estabelece conexão com **handshake de 3 vias**
- Garante **entrega completa e na ordem correta**
- Possui **controle de fluxo e congestionamento**
- Reenvia pacotes perdidos

📌 **Quando usar:**  
Quando a **integridade dos dados é crítica**

📦 **Exemplos:**
- HTTP / HTTPS (web)
- SMTP, POP3, IMAP (e-mail)
- FTP
- SSH

---

## 🚀 UDP (User Datagram Protocol)

❌ **Não confiável e sem conexão**

- Não realiza handshake
- Não confirma entrega
- Mais rápido e leve
- Pode haver perda de pacotes

📌 **Quando usar:**  
Quando **velocidade é mais importante que confiabilidade**

📦 **Exemplos:**
- Streaming de vídeo e áudio
- Jogos online
- VoIP
- DNS (consultas)

---

## 🚪 Números de Porta

As **portas** identificam **qual aplicação ou serviço** está sendo usado em um dispositivo.

- Permitem múltiplos serviços em um único IP
- Cada conexão possui:
  - **Porta de origem**
  - **Porta de destino**

---

## 🔢 Classificação das Portas

| Faixa | Tipo | Uso |
|-----|-----|-----|
| **0 – 1023** | Bem conhecidas | Serviços padrão |
| **1024 – 49151** | Registradas | Aplicações |
| **49152 – 65535** | Dinâmicas | Conexões temporárias |

### 📌 Portas importantes para lembrar

- **80** → HTTP  
- **443** → HTTPS  
- **22** → SSH  
- **21** → FTP  
- **25** → SMTP  
- **53** → DNS  

🔗 Registro oficial: IANA – Service Name and Transport Protocol Port Number Registry

---

## 🔄 TCP e UDP no DNS

- **Cliente → Servidor DNS:** UDP
- **Servidor DNS → Servidor DNS:** TCP

---

## 🧠 Como funciona na prática

Ao acessar um site HTTPS:

- Seu computador usa uma **porta de origem aleatória** (ex: 50923)
- O servidor usa a **porta de destino 443**
- Isso permite várias conexões simultâneas

---

## 🔌 Sockets

Um **socket** identifica uma conexão usando **IP + porta**.

Exemplo:
- Cliente: `192.168.1.5:1099`
- Servidor Web: `192.168.1.7:80`

Par de sockets:
192.168.1.5:1099 ↔ 192.168.1.7:80

---

## 🛠️ Comandos para visualizar portas

### 🖥️ Windows
    netstat -an
    netstat -ano
    tasklist | findstr <PID>

### 🐧 Linux / Kali 
    ss -tuln
    sudo netstat -tulnp

### 🌍 Escaneando portas com Nmap 
    nmap -sS <IP ou domínio>
    nmap -sU <IP ou domínio>
    
⚠️ Escaneio UDP é mais lento.
    
## 📌 Status do Módulo 

✅ **Concluído**

---

> 💡 *TCP garante confiabilidade. UDP garante velocidade. Saber quando usar cada um é essencial para redes e segurança.*
