# Módulo 10 – Interface de Linha de Comando do Cisco IOS

## Visão Geral da CLI do Cisco IOS

A **CLI (Command Line Interface)** do Cisco IOS é uma interface baseada em texto que permite **configurar, monitorar e administrar** dispositivos Cisco, como roteadores e switches.

A CLI pode ser acessada de duas formas:
- **Em banda**: via rede (SSH ou Telnet)
- **Fora da banda**: via porta console

Após a inicialização do dispositivo, o prompt `Router>` indica que a CLI está disponível para uso.  
A partir dela, o administrador pode executar comandos para visualizar o status do dispositivo ou alterar sua configuração.

A CLI do Cisco IOS é **padronizada**, facilitando o gerenciamento de diferentes dispositivos Cisco, já que os comandos básicos são praticamente os mesmos.  
Além disso, a CLI possui um **sistema de ajuda integrado**, que auxilia na configuração e no monitoramento do dispositivo.

---

## Modos de Comando Primários

Como medida de segurança, o Cisco IOS separa o acesso de gerenciamento em dois modos principais.

### Tabela – Modos de Comando do Cisco IOS

| Modo | Descrição | Prompt (Roteador) | Prompt (Switch) |
|---|---|---|---|
| EXEC do usuário | Permite apenas comandos básicos de monitoramento. Não permite alterações na configuração. | `Router>` | `Switch>` |
| EXEC privilegiado | Permite acesso completo aos comandos e a outros modos de configuração. | `Router#` | `Switch#` |

---

## Principais Comandos do Cisco IOS

### `enable`
- Acessa o **modo EXEC privilegiado**
- Necessário para realizar configurações no dispositivo

Exemplo:
- Router> enable
- Router#


---

### `configure terminal`
- Acessa o **modo de configuração global**
- Permite alterar a configuração do dispositivo

Exemplo:
- Router#configure terminal
- Router(config)#


---

### `interface vlan 1`
- Entra no modo de configuração da **interface VLAN 1**
- Normalmente usada para gerenciamento em switches

Exemplo:
- Switch(config)# interface vlan 1
- Switch(config-if)#


---

### `disable`
- Retorna do modo EXEC privilegiado para o modo EXEC do usuário

Exemplo:
- Router# disable
- Router>


---

### `exit`
- Sai do modo atual e retorna ao modo imediatamente anterior

Exemplo:
- Router(config-if)# exit
- Router(config)#


---

### `end`
- Sai de qualquer modo de configuração e retorna diretamente ao modo EXEC privilegiado

Exemplo:
- Router(config)# end
- Router#


---

### `Ctrl + Z`
- Atalho para o comando `end`
- Retorna imediatamente ao modo EXEC privilegiado

---

### `line console 0`
- Entra no modo de configuração da **linha de console**
- Usado para configurar acesso local ao dispositivo

Exemplo:
- Router(config)# line console 0
- Router(config-line)#


---

### `line vty 0 15`
- Configura as **linhas virtuais (VTY)** usadas para acesso remoto (SSH ou Telnet)

Exemplo:
- Router(config)# line vty 0 15
- Router(config-line)#


---

### `interface fastethernet 0/1`
- Acessa o modo de configuração da interface física FastEthernet 0/1

Exemplo:
- Switch(config)# interface fastethernet 0/1
- Switch(config-if)#


---





