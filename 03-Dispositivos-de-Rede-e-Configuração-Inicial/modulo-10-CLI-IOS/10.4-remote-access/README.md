# 🔐 10.4 – Secure Remote Access (VTY, Telnet e SSH)

Quando um dispositivo Cisco é acessado pela rede (remotamente), essa conexão ocorre através das **linhas VTY** (Virtual Terminal Lines).

Os dois métodos mais comuns são:

- ❌ Telnet — inseguro (envia dados em texto puro)
- ✅ SSH — seguro (conexão criptografada)

👉 SSH é o método recomendado.

---

## 📌 Linhas VTY (Acesso remoto)

- Switches normalmente usam: `vty 0 15` (16 linhas)
- Roteadores geralmente usam: `vty 0 4` (5 linhas)

Cada linha VTY precisa de autenticação configurada.

### Exemplo básico (somente SSH):

```bash
Switch(config)# line vty 0 15
Switch(config-line)# password password
Switch(config-line)# transport input ssh
Switch(config-line)# login
``` 
---

## 🔒 Criptografia das senhas

Por padrão, senhas aparecem em texto simples no running-config.
Para criptografar:
```bash
Switch(config)# service password-encryption
``` 
📌 Protege todas as senhas armazenadas no dispositivo.

--- 

## 🚀 Configuração Completa do SSH

Antes de ativar o SSH, o switch precisa:

✔ Hostname configurado
✔ Conectividade de rede
✔ Domínio IP definido

--- 

### ✅ Etapa 1 – Verificar suporte a SSH 
```bash
S1# show ip ssh
```

--- 

### ✅ Etapa 2 – Configurar domínio IP
```bash
S1(config)# ip domain-name cisco.com

```

--- 
### ✅ Etapa 3 – Gerar chaves RSA
```bash
S1(config)# crypto key generate rsa
```
Quando solicitado:
```bash
How many bits in the modulus [512]: 1024
```

📌 Quanto maior o valor, maior a segurança (e mais tempo de processamento).

---

### ✅ Etapa 4 – Criar usuário local
```bash
S1(config)# username admin secret ccna
```

--- 
### ✅ Etapa 5 – Configurar VTY para SSH
```bash
S1(config)# line vty 0 15
S1(config-line)# transport input ssh
S1(config-line)# login local
S1(config-line)# exit
```
📌 Agora o switch aceita somente SSH (Telnet bloqueado).

--- 
### ✅ Etapa 6 – Forçar SSH versão 2
```bash
S1(config)# ip ssh version 2
```
📌 SSH v1 tem falhas de segurança conhecidas.

--- 
## 📊 Exemplo de verificação
```bash
S1# show ip ssh
```

Saída comum antes de gerar chaves:

```bash
SSH Disabled - version 1.99
%Please create RSA keys...
```

Após configuração completa → SSH ativo.

--- 
### 📚 Conceitos importantes

| Item                | Explicação                         |
| ------------------- | ---------------------------------- |
| VTY                 | Linhas virtuais para acesso remoto |
| Telnet              | Sem criptografia (inseguro)        |
| SSH                 | Comunicação criptografada          |
| RSA Keys            | Habilitam o servidor SSH           |
| login local         | Usa usuários locais                |
| transport input ssh | Bloqueia Telnet                    |


--- 
### ✅ Boas práticas de segurança

✔ Sempre usar SSH

✔ Criptografar senhas

✔ Desabilitar Telnet

✔ Usar usuários locais ou servidor AAA

✔ Forçar SSH v2

--- 
