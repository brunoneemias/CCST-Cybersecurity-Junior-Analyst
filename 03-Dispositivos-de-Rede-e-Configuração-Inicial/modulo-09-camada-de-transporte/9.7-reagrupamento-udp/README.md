# Módulo 9.7 – Reagrupamento de Datagramas UDP

O UDP é **sem conexão e não confiável**, diferente do TCP.  

---

## 📦 Como funciona o reagrupamento de datagramas

- Assim como no TCP, múltiplos datagramas UDP podem **seguir caminhos diferentes** na rede.
- Porém, o UDP **não rastreia números de sequência**.
- **Não há reordenação automática**: os datagramas são entregues à aplicação na **ordem em que chegam**.
- Se a sequência for importante, a aplicação deve **controlar a ordem** dos dados.

### 🔹 Exemplo resumido

1. Dados são divididos em datagramas UDP.
2. Cada datagrama pode seguir uma rota diferente.
3. Alguns podem chegar fora de ordem ou até se perder.
4. UDP **não retransmite** datagramas perdidos.

---

## ⚙️ Processos e solicitações do servidor UDP

- Servidores UDP usam **números de portas bem conhecidas ou registradas** para identificar processos/aplicações.
- Ao receber um datagrama, o UDP **encaminha os dados à aplicação apropriada** com base na porta de destino.

### 🔹 Exemplos de portas UDP comuns

| Aplicação | Porta |
| --- | --- |
| DNS | 53 |
| RADIUS | 1812 |

---

## ✅ Status do Módulo

- [x] Estudado
- [x] Documentado
- [x] Revisado
