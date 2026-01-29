# 🧪 Configurações Iniciais de um Roteador Cisco

## 🎯 Objetivo

Configurar e proteger o roteador R1, incluindo:

- Acesso via console  
- Senhas de segurança  
- Banner MOTD  
- Verificação de configurações  
- Salvamento na NVRAM e Flash  

---

## 🖧 Topologia

- PC conectado ao roteador via cabo console
- Acesso ao IOS pelo Terminal

📸 *Sugestão de print: conexão console PCA → R1 no Packet Tracer*

---

## 📌 Parte 1 – Verificando a Configuração Padrão

### 🔹 Acessar o roteador via console

1. Conectar cabo console do PC ao R1  
2. Abrir **Desktop > Terminal > OK**  
3. Pressionar ENTER  

---

### 🔹 Entrar no modo privilegiado

```bash
Router> enable
Router#
```
---
### 🔹 Visualizar configuração atual

```bash
Router# show running-config

```
📸 Print sugerido mostrando o running-config inicial
📘 Observações importantes:
- Hostname padrão: Router
- Interfaces disponíveis (FastEthernet, Gigabit, Serial)
- Linhas VTY normalmente: 0 4 ou 0 15

---

### 🔹 Verificar NVRAM

```bash
Router# show startup-config
```
📌 Resultado esperado:

```bash
startup-config is not present
```
✅ Isso ocorre porque nenhuma configuração foi salva ainda.

---
### 🔹 Entrar no modo privilegiado

```bash
Router> enable
Router#
```
---

## ⚙️ Parte 2 – Configuração Inicial do Roteador

###🔹 Entrar no modo de configuração
```bash
Router# configure terminal
```
---
### 🔹 Definir hostname

```bash
Router(config)# hostname R1
```
---
### 🔹 Configurar banner MOTD

```bash
R1(config)# banner motd #
Unauthorized access is strictly prohibited
```
📸 Print do banner aparecendo ao reconectar no console

---

### 🔹 Criptografar senhas

```bash
R1(config)# service password-encryption
```
---
### 🔹 Senha do modo privilegiado

```bash
R1(config)# enable secret itsasecret
```
---
### 🔹 Proteger acesso via console

```bash
R1(config)# line console 0
R1(config-line)# password letmein
R1(config-line)# login
R1(config-line)# exit
```
---
### 🔹 Verificar configurações

```bash
R1# show running-config
```

📸 Print mostrando senhas criptografadas e banner configurado

---

### 📚 Conceitos Importantes

🔐 Por que usar banner MOTD?
- Alerta legal contra acesso não autorizado
- Importante para auditorias e segurança

---

### 🔒 As senhas aparecem criptografadas?

Sim — após service password-encryption, senhas ficam ofuscadas no config.

---
##🔹 Parte 3 – Salvando Configurações

### 🔹 Salvar na NVRAM
```bash
R1# copy running-config startup-config
```
Forma curta:

```bash
R1# write memory
```
ou
```bash
R1# wr
```

---
### 🔹 Verificar NVRAM

```bash
R1# show startup-config
```
---
## 📂 Backup na Flash (opcional)
### 🔹 Ver arquivos da flash 
```bash
R1# show flash
```
📌 Normalmente o maior arquivo é a imagem IOS (.bin)

---

## 🔹 Salvar configuração na flash 
```bash
R1# copy startup-config flash
```

## R1# copy startup-config flash 
```bash
R1# show flash
```

--- 
✅ Aprendizados do Lab
- Acesso inicial ao IOS
- Segurança básica do roteador
- Uso de show running-config e startup-config
- Importância do backup de configuração
- Conceito de NVRAM vs Flash
---  
