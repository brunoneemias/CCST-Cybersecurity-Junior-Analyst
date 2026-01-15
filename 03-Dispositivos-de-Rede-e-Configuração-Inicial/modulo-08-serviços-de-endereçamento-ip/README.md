# Módulo 8 - Serviços de Endereçamento IP

Os serviços de endereçamento IP são fundamentais para o funcionamento das redes, pois permitem que dispositivos **se localizem, se identifiquem e se comuniquem** de forma automática e eficiente. Os principais serviços são **DNS** e **DHCP**.

---

## 🔎 Sistema de Nomes de Domínio (DNS)

### Como funciona o DNS

O **DNS (Domain Name System)** é responsável por **traduzir nomes de domínio** (ex: www.google.com) em **endereços IP**, que são utilizados pelos dispositivos de rede.

Fluxo básico:
1. O usuário digita uma URL no navegador.
2. O dispositivo consulta um servidor DNS.
3. O DNS responde com o endereço IP correspondente.
4. O dispositivo se conecta ao servidor usando o IP retornado.

📌 Sem o DNS, seria necessário memorizar endereços IP em vez de nomes.

---

## 📄 Formato das Mensagens DNS

O DNS utiliza diferentes **tipos de registros**, cada um com uma finalidade específica:

| Tipo | Descrição |
|-----|-----------|
| **A** | Associa um nome de domínio a um endereço **IPv4** |
| **AAAA** | Associa um nome de domínio a um endereço **IPv6** |
| **NS** | Indica os **servidores de nomes** autoritativos de um domínio |
| **MX** | Define os **servidores de e-mail** responsáveis pelo domínio |

Exemplo:
- `google.com A` → retorna um IPv4
- `google.com AAAA` → retorna um IPv6
- `empresa.com MX` → aponta para o servidor de e-mail

---

## 🌐 Hierarquia do DNS

O DNS é organizado de forma **hierárquica e distribuída**, garantindo escalabilidade e desempenho.

Estrutura básica:
1. **Servidor raiz (Root DNS)**
2. **Domínios de Topo (TLDs)**
3. **Domínios de segundo nível**
4. **Subdomínios**

### Exemplos de TLDs:

- **.com** → comercial
- **.org** → organizações
- **.net** → redes
- **.br** → Brasil
- **.au** → Austrália
- **.au.com** → domínio comercial australiano

📌 Cada nível da hierarquia é responsável por encaminhar a consulta para o próximo nível correto.

---

## 🧪 O Comando `nslookup`

O comando **nslookup** permite consultar servidores DNS diretamente.

### Exemplo básico:

```bash
nslookup www.google.com
``` 
Consultando tipos específicos de registros:
```bash
nslookup -type=MX google.com
nslookup -type=NS google.com
``` 
🔎 Muito usado para:
- Diagnóstico de problemas de DNS
- Verificação de registros
- Testes de resolução de nomes

---

## ⚙️ Protocolo de Configuração Dinâmica de Host (DHCP) 
O que é o DHCP?
O DHCP (Dynamic Host Configuration Protocol) automatiza a configuração de rede, fornecendo:
- Endereço IP
- Máscara de sub-rede
- Gateway padrão
- Servidores DNS

📌 Evita configuração manual e reduz erros.

--- 

### 🏠 Operação do DHCP em um Roteador Doméstico 
Em redes domésticas: 
- O roteador atua como servidor DHCP
- Dispositivos (PCs, celulares, TVs) atuam como clientes
- Cada dispositivo recebe um IP automaticamente ao se conectar à rede

 ---  

### 🔄 Mensagens DHCP (Processo DORA) 
O DHCP opera em quatro etapas principais: 
1. Discover – O cliente procura por um servidor DHCP (broadcast)
2. Offer – O servidor oferece um endereço IP
3. Request – O cliente solicita o IP oferecido
4. Acknowledge – O servidor confirma a concessão
concessão

📌 Esse processo é conhecido como DORA.

 ---   

 ### 🌍 DHCPv6 
O DHCPv6 é a versão do DHCP para redes IPv6.

Características:
- Fornece endereços IPv6 e parâmetros de rede
- Pode operar junto com o SLAAC
- Utiliza mensagens semelhantes ao DHCPv4, adaptadas ao IPv6

📌 Em IPv6, o gateway padrão normalmente é aprendido via Router Advertisement (RA).

 ---   

 ### Status 
✅  Estudado 
