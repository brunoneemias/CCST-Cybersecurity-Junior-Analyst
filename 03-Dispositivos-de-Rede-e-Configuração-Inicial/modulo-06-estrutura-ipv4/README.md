# Módulo 6 - Estrutura do IPv4

## 6.1 Estrutura do Endereço IPv4

Um endereço IPv4 possui **32 bits**, dividido em **porção de rede** e **porção de host**. Cada endereço identifica unicamente um dispositivo em uma rede.

- **Porção de rede:** identifica a rede à qual o host pertence.
- **Porção de host:** identifica o dispositivo dentro da rede.

### Máscara de Sub-rede

A **máscara de sub-rede** define qual parte do endereço IP representa a rede e qual parte representa os hosts. Ela pode ser representada em:

- **Notação decimal pontuada:** `255.255.255.0`
- **Comprimento do prefixo:** `/24` (indica quantos bits são da rede)

#### Tabela de prefixos (/8 até /30)

| Prefixo | Máscara | Hosts disponíveis | Notas |
|---------|--------|-----------------|-------|
| /8      | 255.0.0.0      | 16.777.214    | Classe A |
| /9      | 255.128.0.0    | 8.388.606     | - |
| /10     | 255.192.0.0    | 4.194.302     | - |
| /11     | 255.224.0.0    | 2.097.150     | - |
| /12     | 255.240.0.0    | 1.048.574     | - |
| /13     | 255.248.0.0    | 524.286       | - |
| /14     | 255.252.0.0    | 262.142       | - |
| /15     | 255.254.0.0    | 131.070       | - |
| /16     | 255.255.0.0    | 65.534        | Classe B |
| /17     | 255.255.128.0  | 32.766        | - |
| /18     | 255.255.192.0  | 16.382        | - |
| /19     | 255.255.224.0  | 8.190         | - |
| /20     | 255.255.240.0  | 4.094         | - |
| /21     | 255.255.248.0  | 2.046         | - |
| /22     | 255.255.252.0  | 1.022         | - |
| /23     | 255.255.254.0  | 510           | - |
| /24     | 255.255.255.0  | 254           | Classe C |
| /25     | 255.255.255.128| 126           | - |
| /26     | 255.255.255.192| 62            | - |
| /27     | 255.255.255.224| 30            | - |
| /28     | 255.255.255.240| 14            | - |
| /29     | 255.255.255.248| 6             | - |
| /30     | 255.255.255.252| 2             | Usado em links ponto a ponto |

---

## 6.1.4 Determinando a Rede: Operação "AND" Lógica

Para descobrir o **endereço de rede**, aplicamos o **AND lógico** entre o endereço IP e a máscara de sub-rede.

**Exemplo:**

- IP: `192.168.5.11`
- Máscara: `255.255.255.0`

- IP: 11000000.10101000.00000101.00001011
- Máscara: 11111111.11111111.11111111.00000000
- Rede: 11000000.10101000.00000101.00000000 → 192.168.5.0


---

## 6.2 Tipos de Endereços IPv4 em uma Rede

1. **Endereço de Rede:** identifica a rede inteira. Último octeto é todo 0 (para /24).
2. **Endereço de Host:** identifica os dispositivos dentro da rede. Deve estar entre o endereço de rede e o broadcast.
3. **Endereço de Broadcast:** envia mensagens para todos os hosts da rede. Último octeto é todo 1 (para /24).

**Exemplo (/24):**

- Rede: `192.168.5.0`
- Host: `192.168.5.10`
- Broadcast: `192.168.5.255`

---

💡 **Resumo**

- Endereços IPv4 possuem **32 bits** divididos entre **rede** e **host**.
- Máscara de sub-rede define a porção de rede.
- Prefixos `/8 a /30` indicam quantidade de bits para a rede.
- Endereço de rede e broadcast são reservados; hosts ficam entre eles.
- Operação **AND lógico** é usada para determinar a rede de um IP.

