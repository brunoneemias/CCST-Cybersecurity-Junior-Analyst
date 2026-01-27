# Cisco IOS – Ajuda Sensível ao Contexto e Atalhos da CLI

A CLI do Cisco IOS possui recursos que facilitam o uso dos comandos, evitam erros de sintaxe e aumentam muito a produtividade do administrador de rede.

Esses recursos são muito usados no dia a dia e cobrados em certificações como **CCST e CCNA**.

---

## Ajuda Sensível ao Contexto (`?`)

O caractere `?` mostra os comandos disponíveis de acordo com o **modo atual da CLI**.

### No modo EXEC do usuário ou privilegiado

```bash
Router> ?
Router# ?
```
Exibe:
- Lista de comandos disponíveis naquele modo
  
---

No modo de configuração global
```bash
Router(config)# ?
```
Exibe:
- Opções de configuração possíveis (interfaces, linhas, roteamento, segurança etc.)

---

Para completar partes de comandos
```bash
Router(config)# interface ?
```

Mostra:
- Tipos de interfaces disponíveis (FastEthernet, GigabitEthernet, VLAN, etc.)

---

Para verificar a sintaxe de um comando
```bash
Router# show ?
```
Mostra todas as variações possíveis do comando show.

---

Autocompletar com TAB

A tecla TAB completa automaticamente comandos parcialmente digitados.

Exemplo:
```bash
Router# conf<TAB>
```
Resultado:
```bash
Router# configure
```
Se houver mais de uma possibilidade, o sistema não completa e aguarda mais letras. 

--- 

### Principais Atalhos da CLI
| Atalho               | Função                                             |
| -------------------- | -------------------------------------------------- |
| `Tab`                | Completa automaticamente comandos                  |
| `↑` (seta para cima) | Repete comandos anteriores                         |
| `Ctrl + A`           | Vai para o início da linha                         |
| `Ctrl + E`           | Vai para o final da linha                          |
| `Ctrl + U`           | Apaga toda a linha                                 |
| `Ctrl + W`           | Apaga uma palavra                                  |
| `Ctrl + Z`           | Sai do modo de configuração para EXEC privilegiado |
| `Ctrl + Shift + 6`   | Interrompe processos (ping, traceroute, etc.)      |

--- 

### Repetir Comandos Anteriores

Use a seta para cima (↑) para navegar pelos últimos comandos digitados.

Isso evita redigitar comandos longos.

--- 

Uso do ? Dentro de um Comando
Você pode usar o ? no meio do comando para validar sintaxe.

Exemplo:
```bash
Router(config)# ip ?
```
Mostra todas as opções que podem vir após ip.

--- 

Quando um Comando Está Errado

Se você digitar algo inválido: 
```bash
Router# shwo ip
```
O IOS retorna algo como:
```bash
% Invalid input detected at '^' marker.
```

O símbolo ^ mostra exatamente onde o erro ocorreu.
Isso ajuda a corrigir rapidamente a sintaxe.

--- 

Resumo Rápido

- ? → mostra comandos disponíveis e sintaxe
- TAB → completa comandos
- ↑ → repete comandos anteriores
- Ctrl+Z → sai da configuração
- Ctrl+Shift+6 → interrompe processos
- ^ → indica erro de sintaxe

---  


