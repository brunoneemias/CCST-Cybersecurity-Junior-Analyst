# 🔗 Módulo 7 – Camada de Acesso à Rede

Este módulo aborda os conceitos fundamentais da **camada de acesso à rede**, com foco na tecnologia Ethernet, no encapsulamento de dados e no papel dos switches em redes locais (LANs).

Conteúdo alinhado à trilha **CCST Cybersecurity – Junior Cybersecurity Analyst**, essencial para entendimento de tráfego local e segurança de rede.

---

## 🧱 Camada de Acesso à Rede

A camada de acesso à rede é responsável por:
- A entrega de dados na rede local
- O acesso ao meio físico
- A comunicação entre dispositivos dentro do mesmo segmento de rede

Ela envolve tanto aspectos **físicos** quanto **lógicos** da comunicação.

---

## 🧩 Quadros Ethernet

A tecnologia **Ethernet** é amplamente utilizada em redes locais (LANs) e depende das **placas de interface de rede (NICs)** para comunicação.

Cada NIC possui um:
- **Endereço MAC único e permanente**

### Campos importantes do quadro Ethernet:
- Endereço MAC de origem
- Endereço MAC de destino
- Dados encapsulados
- Informações de controle

Esses campos permitem que os dados sejam entregues corretamente dentro da rede local.

---

## 📦 Encapsulamento

O **encapsulamento** é o processo de organizar os dados para transmissão pela rede.

Funciona de forma semelhante ao envio de uma carta:
- Os dados são colocados dentro de um “envelope”
- Informações de origem e destino são adicionadas
- Cada camada adiciona suas próprias informações

A formatação correta garante que:
- A mensagem chegue ao destino
- O dispositivo receptor consiga interpretar os dados

---

## 🔀 Switches Ethernet

Os **switches Ethernet** são dispositivos intermediários que:
- Conectam dispositivos em uma LAN
- Encaminham quadros com base no endereço MAC
- Segmentam o tráfego de rede, reduzindo colisões

Eles operam principalmente na **Camada 2 (Enlace de Dados)** do modelo OSI.

---

## 🛡️ Importância para Segurança da Informação

O entendimento da camada de acesso é essencial para:
- Analisar tráfego local
- Identificar dispositivos na rede
- Detectar comportamentos anômalos
- Compreender ataques como spoofing e sniffing

Em ambientes SOC e NOC, esse conhecimento auxilia na:
- Investigação de incidentes
- Monitoramento de rede
- Controle de acesso físico e lógico

---

## 📌 Status do Módulo

✅ **Concluído**

---

> 💡 *Entender a camada de acesso é o primeiro passo para compreender o tráfego dentro da rede.*
