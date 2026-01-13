# 🌐 Módulo 8 – Protocolo de Internet (IPv4)

Este módulo apresenta os fundamentos do **protocolo IPv4**, responsável pelo endereçamento lógico e roteamento de dados na Internet e em redes locais.

O entendimento do IPv4 é essencial para comunicação entre dispositivos, diagnóstico de problemas de rede e análise de tráfego em ambientes de **SOC, NOC e Segurança da Informação**.

---

## 📍 Endereçamento IPv4

Para acessar a Internet ou se comunicar em uma rede, um host precisa de um **endereço IPv4**, que é um identificador lógico e único.

- O endereço IPv4 é atribuído à **interface de rede (NIC)** do dispositivo
- Hosts, servidores e roteadores utilizam endereços IPv4
- Cada pacote IP contém:
  - Endereço IPv4 de origem
  - Endereço IPv4 de destino

Esses endereços são fundamentais para o **roteamento correto dos dados**.

---

## 🔢 Estrutura do Endereço IPv4

- Um endereço IPv4 possui **32 bits**
- Esses bits são divididos em **quatro grupos de 8 bits**, chamados de **octetos**

### Notação Decimal com Ponto
Para facilitar a leitura e configuração:
- Cada octeto é convertido para decimal
- Os valores são separados por ponto

📌 Exemplo:
- Binário: `11010001.10100101.11001000.00000001`
- Decimal: `209.165.200.1`

---

## 🧩 Redes e Hosts

O endereço IPv4 é **hierárquico**, composto por:
- **Parte de rede**
- **Parte de host**

A **máscara de sub-rede** define qual parte do endereço identifica a rede.

📌 Exemplo:
- Endereço: `192.168.5.11`
- Máscara: `255.255.255.0`

Resultado:
- Rede: `192.168.5`
- Host: `11`

---

## 🔀 Comunicação entre Redes

- Hosts com a **mesma parte de rede** comunicam-se diretamente
- Para se comunicar com **outras redes**, é necessário um **roteador**
- Roteadores precisam conhecer apenas as **rotas das redes**, não de cada host individual

Esse modelo torna a Internet **escalável e eficiente**.

---

## 📞 Analogia com Sistema Telefônico

O endereçamento IPv4 pode ser comparado a um número de telefone:
- Código do país / área → identifica a rede
- Número local → identifica o host

Essa hierarquia facilita o encaminhamento das comunicações.

---

## 🛡️ Importância para Segurança da Informação

O entendimento do IPv4 é fundamental para:
- Análise de tráfego de rede
- Identificação de origem e destino de pacotes
- Detecção de atividades suspeitas
- Configuração de firewalls e regras de acesso
- Investigação de incidentes em SOC/NOC

---

## 📌 Status do Módulo

✅ **Concluído**

---

> 💡 *Sem entender endereçamento IP, não é possível entender redes nem segurança.*
