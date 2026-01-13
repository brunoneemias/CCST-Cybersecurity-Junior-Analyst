# 🌐 Módulo 17 – Comandos para Solução de Problemas

Este módulo apresenta os **principais comandos para diagnosticar e resolver problemas de rede** em Windows e Linux.

---

## 🖥️ ipconfig (Windows)

Exibe informações da configuração IP e permite renovar endereços DHCP.

| Comando | Função |
| --- | --- |
| `ipconfig` | Mostra IP, máscara de sub-rede e gateway |
| `ipconfig /all` | Exibe informações detalhadas, incluindo MAC, DNS e status do DHCP |
| `ipconfig /release` | Libera o IP atual |
| `ipconfig /renew` | Solicita novo IP ao servidor DHCP |

💡 Útil para problemas como “rede não identificada” ou “sem acesso à internet”.

---

## 📡 ping

Testa conectividade entre dispositivos usando **ICMP**.

| Comando | Função |
| --- | --- |
| `ping www.google.com` | Envia 4 pacotes padrão |
| `ping -t www.google.com` | Ping contínuo até Ctrl+C |
| `ping -n 5 www.google.com` | Envia 5 pacotes |
| `ping -l 1000 www.google.com` | Define tamanho do pacote (bytes) |
| `ping -4` / `ping -6` | Força IPv4 ou IPv6 |

📊 Interpretação:
- Tempo baixo (ms) → conexão rápida
- Perda de pacotes → instabilidade
- “Esgotado o tempo limite” → destino inacessível

⚠️ Limitações: firewalls podem bloquear; não mede largura de banda.

---

## 📊 netstat

- Exibe **conexões de rede ativas** e portas em uso.
- Com opções avançadas, mostra **PID** e processos associados.

---

## 🛣️ tracert

- Mostra a **rota percorrida** até um destino.
- Útil para identificar **pontos de falha ou latência** em múltiplos saltos.

---

## 🌐 nslookup

- Consulta **servidores DNS** para obter IPs ou nomes de domínio.
- Ideal para testar resolução de nomes e diagnosticar problemas de DNS.

---

## 🧠 Dica prática

Combine comandos para diagnóstico completo:

                  ipconfig /all
                  ping www.google.com
                  tracert www.google.com
                  nslookup www.google.com
                  netstat -an

## 📌 Status do Módulo

✅ **Concluído**
