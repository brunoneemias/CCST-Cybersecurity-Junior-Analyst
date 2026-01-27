# Packet Tracer – Navegação no Cisco IOS (CLI)

## 🎯 Objetivo

Praticar o uso da CLI do Cisco IOS, explorando:

- Conexão via cabo console
- Modos EXEC (usuário e privilegiado)
- Ajuda sensível ao contexto (?)
- Auto-completar com TAB
- Configuração de data e hora com o comando `clock`

---

## 🧪 Topologia

PC conectado ao Switch via cabo console para acesso direto à CLI.

📸 *Inserir imagem da conexão console aqui*  
![Console Connection](images/console-connection.png)

---

## 🔌 Acesso à CLI via Terminal

- Conexão RS-232 do PC ao console do switch
- Configurações padrão do terminal
- Acesso ao prompt inicial:

S1>


📸 *Inserir print do primeiro prompt da CLI*  
![First Prompt](images/first-prompt.png)

---

## ❓ Ajuda Sensível ao Contexto

Uso do caractere `?` para:

- Listar comandos disponíveis
- Completar comandos parcialmente
- Entender parâmetros exigidos

### Exemplos:

```bash
S1> ?
S1> t?
``` 
📸 Inserir print mostrando ajuda contextual

---

### 🔐 Modos EXEC

| Modo            | Prompt | Função                            |
| --------------- | ------ | --------------------------------- |
| User EXEC       | `S1>`  | Monitoramento básico              |
| Privileged EXEC | `S1#`  | Configuração e comandos avançados |


Entrada no modo privilegiado:
```bash
enable
``` 

E acesso ao modo de configuração: 
```bash
configure terminal
``` 

---

### ⏰ Configuração do Relógio
Verificação do horário:
```bash
show clock
```

Configuração completa:
```bash
clock set 15:00:00 31 Jan 2035
```

Confirmação:
```bash
show clock

```

📸 Inserir print da hora configurada corretamente


---

### ⚠️ Mensagens do IOS

O IOS fornece feedback para comandos incorretos:
  - % Incomplete command
  - % Invalid input detected
  - % Bad value
  - Essas mensagens ajudam a aprender a sintaxe correta.

  ---
  
###📚 Conceitos praticados

  - Navegação na CLI Cisco
  - Ajuda sensível ao contexto
  - Autocompletar de comandos
  - Modos de operação do IOS
  - Validação de sintaxe
  - Configuração básica de sistema

  ---

### ✅ Conclusão

Este laboratório reforçou o uso prático da CLI do Cisco IOS, essencial para administração de redes Cisc e troubleshooting
