# Módulo 3 - Sistemas Numéricos

Este módulo aborda os sistemas numéricos utilizados em redes e computação, incluindo binário, decimal, hexadecimal e conversões entre eles. Também foca na representação de endereços IPv4.

---

## 🔢 Sistemas Numéricos

### 1. Binário (Base 2)
- Utiliza apenas **0 e 1**.
- Base de toda computação digital.
- Exemplo: `1101` (decimal 13).

### 2. Decimal (Base 10)
- Sistema numérico padrão do dia a dia.
- Dígitos de 0 a 9.
- Exemplo: `13` (binário 1101).

### 3. Hexadecimal (Base 16)
- Utiliza dígitos de 0 a 9 e letras A a F.
- Muito usado em endereços de memória, MAC e IPv6.
- Exemplo: `0x1A` (decimal 26, binário 11010).

---

## 🌐 Endereços IPv4

- IPv4 usa **32 bits**, divididos em **4 octetos** de 8 bits.
- Representação comum: **notação decimal com pontos** (ex: 192.168.1.1).
- Cada octeto é convertido de binário para decimal para facilitar leitura.

### Exemplos:
- Binário: `11000000.10101000.00000001.00000001`
- Decimal: `192.168.1.1`

---

## 🔄 Conversões

### Binário ↔ Decimal
- Multiplicar cada bit pelo peso correspondente (2^n) para binário → decimal.
- Dividir sucessivamente por 2 para decimal → binário.

### Binário ↔ Hexadecimal
- Agrupar bits em blocos de 4.
- Converter cada bloco para o dígito hexadecimal correspondente.

### Decimal ↔ Hexadecimal
- Converter decimal → binário → hexadecimal (ou usar divisão sucessiva por 16).

---

## 💡 Dicas práticas:
1. Sempre verifique a **ordem dos bits** ao fazer conversões.
2. Use o **binário para cálculos lógicos e máscaras de rede**.
3. Use hexadecimal para **endereços MAC e memória**, decimal para **endereços IPv4**.

---

✅ **Status:** Concluído
