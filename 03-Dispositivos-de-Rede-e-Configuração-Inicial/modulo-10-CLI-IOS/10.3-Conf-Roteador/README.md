# 🧪 Configuração Básica de um Roteador Cisco (IOS)

## 📌 Objetivo

Realizar a configuração inicial de segurança e identificação de um roteador Cisco, incluindo:

- Definição de hostname  
- Proteção de acessos (EXEC, console e VTY)  
- Criptografia de senhas  
- Banner legal de aviso  
- Salvamento da configuração  

---

## ⚙️ Etapas da Configuração Básica

### 🔹 Etapa 1 – Configurar o nome do dispositivo (hostname)

```bash
Router(config)# hostname R1
``` 
Define o nome do roteador para facilitar a identificação na rede. 

---

### 🔹 Etapa 2 – Proteger o modo EXEC privilegiado

```bash
R1(config)# enable secret class
``` 
Cria uma senha criptografada para acessar o modo privilegiado (enable).

---

### 🔹 Etapa 3 – Proteger o acesso via console

```bash
R1(config)# line console 0
R1(config-line)# password cisco
R1(config-line)# login
``` 
Exige autenticação ao acessar o roteador fisicamente pelo console.

---
### 🔹 Etapa 4 – Proteger o acesso remoto (VTY – Telnet/SSH)

```bash
R1(config)# line vty 0 4
R1(config-line)# password cisco
R1(config-line)# login
R1(config-line)# transport input ssh telnet
``` 
Controla quais protocolos são permitidos para acesso remoto.

---
### 📘 Função do transport input

| Opção    | Descrição                       |
| -------- | ------------------------------- |
| `ssh`    | Permite apenas acesso seguro    |
| `telnet` | Permite acesso sem criptografia |
| `all`    | Permite todos os protocolos     |
| `none`   | Bloqueia acesso remoto          |

Recomendado usar somente ssh por segurança.

---
### 🔹 Etapa 5 – Criptografar todas as senhas

```bash
R1(config)# service password-encryption

``` 
Oculta senhas no arquivo de configuração.

---
### 🔹 Etapa 6 – Configurar banner de aviso legal

```bash
R1(config)# banner motd #
***********************************************
WARNING: Unauthorized access is prohibited!
***********************************************
#

``` 
Exibe uma mensagem de alerta antes do login.

---
### 🔹 Etapa 7 – Salvar a configuração

```bash
R1# copy running-config startup-config
``` 
Salva as configurações na memória permanente (NVRAM).

---

### 📑 Exemplo Completo de Configuração
```bash
Router> enable
Router# configure terminal

Router(config)# hostname R1

R1(config)# enable secret class

R1(config)# line console 0
R1(config-line)# password cisco
R1(config-line)# login
R1(config-line)# exit

R1(config)# line vty 0 4
R1(config-line)# password cisco
R1(config-line)# login
R1(config-line)# transport input ssh telnet
R1(config-line)# exit

R1(config)# service password-encryption

R1(config)# banner motd #
***********************************************
WARNING: Unauthorized access is prohibited!
***********************************************
#

R1# copy running-config startup-config

```
 
---
✅ Conceitos Aprendidos

- Configuração inicial de roteadores Cisco
- Segurança básica de acessos
- Boas práticas de proteção de senhas
- Organização de dispositivos de rede
---
