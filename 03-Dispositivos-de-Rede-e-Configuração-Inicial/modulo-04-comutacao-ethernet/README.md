# Módulo 4 - Comutação Ethernet (Visual)

Este módulo apresenta conceitos de Ethernet, endereçamento MAC, encapsulamento, operação de switches e notações Ethernet de forma visual.

---

## 🌐 Ethernet e Notação

### Notação Ethernet (Ex: 100Base-T)
| Notação | Significado |
| --- | --- |
| **10** | Velocidade em Mbps |
| **100** | Velocidade em Mbps |
| **1000** | Velocidade em Mbps (1 Gbps) |
| **10G** | Velocidade em Gbps |
| **Base** | Baseband – apenas um sinal por cabo |
| **T** | Par trançado (Twisted Pair) |
| **LX** | Fibra longa (Long wavelength) |
| **SR** | Fibra curta (Short range) |

> Exemplos:
> - `10Base-T` → 10 Mbps, baseband, par trançado  
> - `100Base-T` → 100 Mbps, baseband, par trançado  
> - `1000Base-LX` → 1 Gbps, baseband, fibra longa  
> - `10GBase-SR` → 10 Gbps, baseband, fibra curta

---

## 🔄 Encapsulamento Ethernet

### **Quadro 802.3 (Ethernet)**

    | Preamble | SFD | Dest MAC | Source MAC | Length/Type | Data/Payload | CRC (FCS) |
    | 7 bytes  |1 byte| 6 bytes | 6 bytes   | 2 bytes     | 46-1500 B   | 4 bytes   |

1. Preamble: sincroniza a recepção
2. SFD: indica início do quadro
3. Dest MAC / Source MAC: endereços do destino e origem
4. Length/Type: comprimento ou tipo do protocolo
5. Data/Payload: dados encapsulados
6. CRC: verificação de erros

---

### Quadro 802.2 (LLC) 
    | DSAP | SSAP | Control Field | Data/Payload |
    | 1 B  | 1 B  | 1-2 B         | Variável     |
- DSAP: protocolo de destino
- SSAP: protocolo de origem
- Control Field: tipo de quadro (informação, supervisão, etc.)
- Data/Payload: dados da camada superior
⚠️ Quadro Runt: quadro menor que 64 bytes. Indica erro de transmissão ou colisão.

---

### 🖥️ Endereços MAC
| Tipo          | Descrição                                            |
| ------------- | ---------------------------------------------------- |
| **Unicast**   | Um MAC para um dispositivo específico                |
| **Broadcast** | MAC especial para todos na LAN (`FF:FF:FF:FF:FF:FF`) |
| **Multicast** | MAC que alcança um grupo específico                  |

---

### ⚡ Switches Ethernet 
1. Aprendizado de MAC: switch registra endereços MAC das portas
2. Encaminhamento: envia quadros apenas para a porta correta
3. Filtragem: evita flood desnecessário
4. Gateway padrão: se o destino estiver fora da LAN, envia para o MAC do roteador

---

### 🎨 Visualização dos Quadros 
### Quadro 802.3 (Ethernet)

    ┌────────────┬────┬────────────┬────────────┬─────────────┬─────────────┬───────────┐
    │ Preamble   │SFD │ Dest MAC   │ Source MAC │ Length/Type │ Data/Payload│ CRC       │
    │ 7 bytes    │1B  │ 6 bytes    │ 6 bytes    │ 2 bytes     │ 46-1500 B   │ 4 bytes   │
    └────────────┴────┴────────────┴────────────┴─────────────┴─────────────┴───────────┘

### Quadro 802.2 (LLC) 

    ┌───────┬───────┬──────────────┬─────────────┐
    │ DSAP  │ SSAP  │ Control Field │ Data/Payload│
    │ 1 B   │ 1 B   │ 1-2 B        │ Variável    │
    └───────┴───────┴──────────────┴─────────────┘


## 💡 Dicas rápidas 
- Cada host precisa de MAC único
- Switch aprende MAC dinamicamente
- Broadcast e multicast impactam toda a rede
- Quadro runt indica erro de transmissão
- Notação Ethernet ajuda a identificar velocidade, tipo de transmissão e meio físico

---

✅ **Status:** Concluído

