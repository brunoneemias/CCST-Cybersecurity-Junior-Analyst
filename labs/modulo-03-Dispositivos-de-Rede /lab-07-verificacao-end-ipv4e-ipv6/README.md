# 🌐 Packet Tracer – Verificação de Endereçamento IPv4 e IPv6 (Dual Stack)

---

## Topologia 

Imagem aqui.... 

## 📋 Tabela de Endereçamento

| Dispositivo | Interface | Endereço IP / Prefixo | Máscara | Gateway |
|------------|----------|----------------------|--------|--------|
| R1 | G0/0 | 10.10.1.97 | 255.255.255.224 | N/D |
| R1 | G0/0 | 2001:db8:1:1::1/64 | — | N/D |
| R1 | S0/0/1 | 10.10.1.6 | 255.255.255.252 | N/D |
| R1 | S0/0/1 | 2001:db8:1:1::1/64 | — | N/D |
| R1 | S0/0/1 | fe80::1 | Link-local | N/D |
| R2 | S0/0/0 | 10.10.1.5 | 255.255.255.252 | N/D |
| R2 | S0/0/0 | 2001:db8:1:2::1/64 | — | N/D |
| R2 | S0/0/1 | 10.10.1.9 | 255.255.255.252 | N/D |
| R2 | S0/0/1 | 2001:db8:1:3::1/64 | — | N/D |
| R2 | S0/0/1 | fe80::2 | Link-local | N/D |
| R3 | G0/0 | 10.10.1.17 | 255.255.255.240 | N/D |
| R3 | G0/0 | 2001:db8:1:4::1/64 | — | N/D |
| R3 | S0/0/1 | 10.10.1.10 | 255.255.255.252 | N/D |
| R3 | S0/0/1 | 2001:db8:1:3::2/64 | — | N/D |
| R3 | S0/0/1 | fe80::3 | Link-local | N/D |
| PC1 | NIC | ________ | ________ | ________ |
| PC1 | NIC (IPv6) | ________ | /64 | ________ |
| PC2 | NIC | ________ | ________ | ________ |
| PC2 | NIC (IPv6) | ________ | /64 | ________ |

---

## 🎯 Objetivos

- Completar a documentação IPv4 e IPv6
- Testar conectividade com ping
- Descobrir caminhos com tracert

---

# 📌 Parte 1 – Documentação dos Endereços

## 🔹 IPv4

Em cada PC:

```bash
ipconfig /all
``` 

--- 

