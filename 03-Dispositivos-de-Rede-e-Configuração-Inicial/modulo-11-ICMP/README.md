# 📡 Mensagens ICMPv4 e ICMPv6 + Ping e Traceroute

O ICMP (Internet Control Message Protocol) é usado para:

- Diagnóstico de rede
- Notificação de erros
- Testes de conectividade

---

# 📶 Acessibilidade do Host (Echo)

Funcionamento básico do `ping`:

| Mensagem | Função |
|---------|-------|
| Echo Request | Solicitação enviada ao destino |
| Echo Reply | Resposta confirmando acessibilidade |

Se houver resposta → o host está ativo na rede.

---

# 🚫 Destino ou Serviço Inalcançável

### ICMPv4

| Código | Significado |
|------|------------|
| 0 | Rede inalcançável |
| 1 | Host inalcançável |
| 2 | Protocolo inalcançável |
| 3 | Porta inalcançável |

### ICMPv6

| Código | Significado |
|------|------------|
| 0 | Nenhuma rota para o destino |
| 1 | Comunicação bloqueada |
| 2 | Fora do escopo |
| 3 | Endereço inacessível |
| 4 | Porta inalcançável |

---

# ⏳ Tempo Excedido

### IPv4
Usa o campo **TTL (Time To Live)**

### IPv6
Usa o campo **Hop Limit**

Quando chega a 0 → pacote é descartado e o roteador envia ICMP Time Exceeded.

📌 Base do funcionamento do `traceroute`.

---

# 🌐 ICMPv6 e Neighbor Discovery Protocol (NDP)

## 📊 Mensagens ICMPv6

| Mensagem | Sigla | Quem envia | Função |
|---------|------|-----------|-------|
| Router Solicitation | RS | Host | Solicita dados do roteador |
| Router Advertisement | RA | Roteador | Envia info de rede |
| Neighbor Solicitation | NS | Host | Descobrir MAC |
| Neighbor Advertisement | NA | Host | Responder MAC |

---

## 📢 Router Advertisement (RA)

Enviadas pelos roteadores IPv6 (~200s):

Podem conter:

- Prefixo de rede
- Gateway padrão
- DNS
- Nome de domínio

📌 Hosts com SLAAC configuram IP automaticamente.

---

# 🧪 Utilitário Ping

O `ping` é uma ferramenta IPv4 e IPv6 que usa:

- ICMP Echo Request
- ICMP Echo Reply

### 📌 Observação importante

O primeiro ping pode falhar devido a:

- ARP (IPv4)
- Neighbor Discovery (IPv6)

Antes da comunicação ocorrer.

Após os testes, o ping mostra:

- Taxa de sucesso
- Tempo médio de ida e volta (RTT)

---

## ✅ Tipos de teste com ping

### 🔁 Ping Loopback (local)

IPv4:
```bash
ping 127.0.0.1
```

IPv6: 
```bash
ping ::1
```

✔ Verifica se o TCP/IP está funcionando no host
❌ Não testa rede nem gateway

--- 

### 🌉 Ping no Gateway Padrão

Testa se:

- Host está conectado corretamente
- Interface do roteador funciona

✔ Confirma comunicação na rede local

--- 

### 🌍 Ping em Host Remoto

Verifica:

- Rede local
- Gateway padrão
- Roteadores no caminho
- Host remoto

📌 Um ping bem-sucedido confirma a conectividade ponta a ponta.

⚠ Pode falhar por bloqueio ICMP em firewalls.

--- 

### 🧭 Traceroute (tracert)

Ferramenta que mostra:
➡ Cada salto (roteador) até o destino

Serve para:
- Diagnóstico de falhas
- Localizar onde a comunicação para

--- 

### ⏱ RTT – Round Trip Time

Tempo que o pacote leva para:

➡ Ir até o destino e voltar

Usado por ping e traceroute.

--- 

### 📦 TTL (IPv4) e Hop Limit (IPv6)

O traceroute funciona aumentando:

TTL = 1, 2, 3, 4...

Cada expiração gera uma mensagem:

ICMP Time Exceeded

Assim ele descobre cada roteador do caminho.

---  

### ✅ Resumo Final

- ICMP é base de diagnóstico de redes
- Ping testa conectividade
- Traceroute mapeia o caminho
- ICMPv6 é mais avançado que ICMPv4
- TTL/Hop Limit controlam a vida do pacote
