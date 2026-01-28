# 🔧 Configuração Básica de um Switch Cisco

Nesta etapa foi realizada a configuração inicial de um switch Cisco, incluindo:

- Nome do dispositivo (hostname)
- Segurança de acesso local e remoto
- Proteção do modo privilegiado
- Criptografia de senhas
- Banner de aviso legal
- Endereço IP de gerenciamento (SVI)
- Salvamento da configuração

---

## 📌 Elementos comuns configurados em um switch LAN

| Item | Finalidade |
|-----|-----------|
| Hostname | Identificação do dispositivo na rede |
| IP de gerenciamento | Acesso remoto via SSH/Telnet |
| Senhas | Proteção de console, VTY e modo privilegiado |
| Banner MOTD | Aviso legal de acesso |
| SVI (VLAN 1) | Interface virtual para gerenciamento |
| Salvamento | Preservar configuração após reboot |

---

## 🖥️ Comandos de Configuração

### 🔹 Definir nome do switch

```bash
hostname S1
```

---

### 🔐 Proteger acesso pelo console

```bash
line console 0
password cisco
login
```
📖 line console 0 → controla o acesso físico direto ao switch via cabo console.

---

### 🌐 Proteger acesso remoto (Telnet/SSH)

```bash
line vty 0 15
password cisco
login
```
📖 line vty 0 15 → controla conexões remotas simultâneas (virtual terminal). 
⚠️ Telnet não é seguro — o ideal é usar SSH.

---

### 🔑 Proteger modo privilegiado

```bash
enable secret class
```

---


### 🔒 Criptografar senhas no arquivo de configuração

```bash
service password-encryption
```

---


### ⚠️ Configurar banner legal

```bash
banner motd #Nenhum acesso não autorizado permitido!#
```

---


### 🌐 Configurar IP de gerenciamento (SVI)


```bash
interface vlan 1
ip address 192.168.1.20 255.255.255.0
no shutdown
```

📖 Permite acesso remoto ao switch via rede.

---


### 💾 Salvar configuração

```bash
copy running-config startup-config
```

---

### 📑 Exemplo completo de configuração

```bash
Switch> enable
Switch# configure terminal
Switch(config)# hostname S1
S1(config)# enable secret class

S1(config)# line console 0
S1(config-line)# password cisco
S1(config-line)# login

S1(config-line)# line vty 0 15
S1(config-line)# password cisco
S1(config-line)# login
S1(config-line)# exit

S1(config)# service password-encryption
S1(config)# banner motd #Nenhum acesso não autorizado permitido!#

S1(config)# interface vlan 1
S1(config-if)# ip address 192.168.1.20 255.255.255.0
S1(config-if)# no shutdown
S1(config-if)# end

S1# copy running-config startup-config

```

---


### ✅ Conceitos importantes

- 🔐 enable secret é mais seguro que enable password
- 🌐 VTY controla acesso remoto
- 🖥️ Console controla acesso físico
- 📄 startup-config salva após reinicialização
- ⚠️ Banner é exigido em ambientes corporativos

---


