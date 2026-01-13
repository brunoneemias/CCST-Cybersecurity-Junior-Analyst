# 🌍 Módulo 12 – Gateways para Outras Redes

Este módulo aborda como os dispositivos se comunicam com **outras redes**, destacando o papel do **gateway padrão**, do **roteador sem fio**, do **DHCP** e do **NAT** na comunicação com a Internet.

---

## 🚧 Limites de Rede e Gateway Padrão

Em uma rede, todo host que deseja se comunicar com **outras redes** precisa utilizar um **gateway padrão**.

- O gateway padrão é o **endereço IPv4 da interface do roteador** conectada à rede local
- Cada host deve conhecer esse endereço para enviar pacotes para fora da sua rede
- O gateway pode ser configurado:
  - **Estáticamente**
  - **Dinamicamente via DHCP**

Sem um gateway padrão configurado, o host só consegue se comunicar **dentro da rede local**.

---

## 📡 Roteador Sem Fio e DHCP

O roteador sem fio desempenha dois papéis importantes:

### 🔹 Na rede interna (LAN)
- Atua como **servidor DHCP**
- Distribui automaticamente:
  - Endereço IPv4
  - Máscara de sub-rede
  - Gateway padrão
  - DNS
- Atende hosts conectados via:
  - Cabo Ethernet
  - Wi-Fi

### 🔹 Na rede externa (WAN)
- Atua como **cliente DHCP**
- Recebe do ISP um **endereço IPv4 público**
- Esse endereço permite comunicação com a Internet

O roteador sem fio funciona como o **limite entre a rede interna local e a Internet externa**.

---

## 🔄 Operação NAT (Network Address Translation)

O **NAT** é o processo que permite que múltiplos dispositivos de uma rede privada acessem a Internet usando **um único endereço IPv4 público**.

### Funcionamento do NAT:
- Hosts internos usam **endereços IPv4 privados**
- O roteador possui um **endereço IPv4 público**
- Ao sair para a Internet:
  - O endereço privado de origem é substituído pelo endereço público do roteador
- Ao receber respostas:
  - O processo é invertido

📌 Apenas pacotes destinados a **outras redes** passam pelo NAT, pois precisam atravessar o gateway.

---

## 🔐 Benefícios do NAT

- Conserva endereços IPv4 públicos
- Permite múltiplos hosts acessarem a Internet
- Oculta endereços internos da rede local
- Aumenta a segurança básica da rede

---

## 🛡️ Importância para Redes e Segurança

O entendimento de gateway e NAT é essencial para:
- Diagnóstico de falhas de conectividade
- Análise de tráfego de rede
- Configuração de roteadores e firewalls
- Atuação em ambientes SOC e NOC
- Compreensão de logs e conexões externas

---

## 📌 Status do Módulo

✅ **Concluído**

---

> 💡 *Se o pacote sai da rede, ele passa pelo gateway.  
Se sai para a Internet, ele passa pelo NAT.*
