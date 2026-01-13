# 🔎 Nmap

Este repositório contém um laboratório introdutório utilizando a ferramenta **Nmap** para descoberta de hosts e enumeração de serviços em um ambiente controlado.

---

## 🎯 Objetivos
- Demonstrar comandos básicos do Nmap.
- Identificar hosts ativos em uma rede local.
- Escanear portas abertas de um alvo.
- Detectar versões de serviços.

---

## 🛠️ Cenário
- Ambiente virtualizado no **VirualBox**.
- Uma máquina Linux com Nmap instalado.
- host local como alvo de testes.

> ⚠️ **Nota ética:** Todos os testes foram realizados em ambiente controlado. Nunca execute varreduras em redes/hosts sem permissão.

---

## 🚀 Passo a passo

### 1. Descoberta de hosts ativos
    nmap -sn 192.168.0.0/24

### 2. Escaneamento de portas abertas
    nmap 192.168.0.10
Resultado esperado: portas abertas e serviços básicos no host alvo.

### 3. Detecção de versões de serviços
    nmap -sV 192.168.0.10
Resultado esperado: versão dos serviços identificados (ex.: Apache, OpenSSH).
### 3. Salvando resultados em arquivo
    nmap -sV 192.168.0.10 -oN scans/resultado.txt
Resultado esperado: saída salva em scans/resultado.txt.

### Estrutura do repositório
    lab-3-nmap/
    ├── README.md
    ├── scans/
    │   ├── discovery.txt
    │   ├── host_scan.txt
    │   └── version_scan.txt

### Conclusão
Este laboratório mostra como o Nmap pode ser usado para:
- Descobrir hosts ativos.
- Mapear portas abertas.
- Identificar serviços e versões

