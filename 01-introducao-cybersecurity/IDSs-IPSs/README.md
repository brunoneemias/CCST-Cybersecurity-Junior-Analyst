# 🛡️ Sistemas de Detecção e Prevenção de Intrusão (IDS & IPS)

Este repositório apresenta uma introdução aos **IDSs (Intrusion Detection Systems)** e **IPSs (Intrusion Prevention Systems)**, destacando seus conceitos, diferenças e exemplos práticos de uso em ambientes de segurança da informação.

---

## 🎯 Objetivos
- Explicar o que são IDSs e IPSs.
- Mostrar as principais diferenças entre eles.
- Apresentar exemplos de ferramentas populares.
- Demonstrar cenários práticos de aplicação.

---

## 📖 Conceitos

### 🔍 IDS (Intrusion Detection System)
- **Função:** Monitorar tráfego de rede e sistemas para identificar atividades suspeitas ou maliciosas.
- **Ação:** Apenas alerta o administrador quando detecta algo anormal.
- **Tipos:**
  - **NIDS (Network IDS):** Monitora pacotes na rede.
  - **HIDS (Host IDS):** Monitora atividades em um host específico.

### 🛡️ IPS (Intrusion Prevention System)
- **Função:** Além de detectar, atua bloqueando ou prevenindo ataques em tempo real.
- **Ação:** Pode descartar pacotes, bloquear conexões ou reconfigurar firewalls automaticamente.
- **Tipos:**
  - **NIPS (Network IPS):** Atua diretamente no tráfego da rede.
  - **HIPS (Host IPS):** Protege um host específico contra ataques.

---

## ⚖️ Diferenças principais

| Característica | IDS | IPS |
|----------------|-----|-----|
| Ação           | Detecta e alerta | Detecta e bloqueia |
| Posição        | Fora da linha de tráfego | Inline (entre origem e destino) |
| Reação         | Passiva | Ativa |
| Exemplo        | Snort (modo IDS) | Suricata, Snort (modo IPS) |

---

## 🛠️ Ferramentas populares
- **Snort:** Pode atuar como IDS ou IPS.
- **Suricata:** IDS/IPS moderno com suporte a multi-thread.
- **OSSEC:** Focado em HIDS (Host-based IDS).
- **Zeek (antigo Bro):** IDS voltado para análise de tráfego e logs.

---

## 🚀 Cenário prático (exemplo simples)
1. **Instalar Snort em modo IDS:**
   ```bash
   sudo apt install snort
Configurar para monitorar interface de rede e gerar alertas

2. 	Configurar Snort em modo IPS:
    ```bash
    snort -A console -Q -c /etc/snort/snort.conf -i eth0
Agora o Snort atua inline, bloqueando tráfego malicioso.

## 📌 Conclusão
- IDS: Ideal para monitoramento e auditoria, sem interferir diretamente no tráfego.
- IPS: Mais proativo, capaz de bloquear ataques em tempo real.
- Ambos são complementares e frequentemente usados juntos em arquiteturas de segurança modernas.

