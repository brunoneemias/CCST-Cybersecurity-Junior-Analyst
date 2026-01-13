# 📡 Módulo 5 – Princípios de Comunicação em Redes

Este módulo aborda os **fundamentos da comunicação em redes**, essenciais para compreender como os dispositivos trocam dados, como os protocolos funcionam e como os modelos de rede ajudam no diagnóstico de problemas e na segurança da informação.

O conteúdo é parte da trilha **CCST Cybersecurity – Junior Cybersecurity Analyst**, com foco em funções como **SOC, NOC e Analista de Segurança Júnior**.

---

## 🔁 Protocolos de Comunicação

A comunicação em redes depende de **protocolos**, que são conjuntos de regras responsáveis por garantir que os dados sejam transmitidos corretamente entre os dispositivos.

Os protocolos definem:
- Formato e tamanho das mensagens
- Temporização da comunicação
- Codificação dos dados
- Encapsulamento (adição de cabeçalhos)
- Padrões de mensagem (requisição e resposta)

Sem protocolos, não existe comunicação confiável em uma rede.

---

## 🌐 Padrões da Internet

A Internet funciona graças à padronização dos protocolos, permitindo que dispositivos de diferentes fabricantes e sistemas operacionais se comuniquem.

- Os padrões da Internet são documentados em **RFCs (Request for Comments)**
- O **IETF (Internet Engineering Task Force)** é responsável por manter e publicar esses padrões

A padronização garante interoperabilidade, escalabilidade e estabilidade da rede.

---

## 🧱 Modelo TCP/IP

O modelo **TCP/IP** é o modelo prático utilizado na Internet e organiza a comunicação em quatro camadas:

1. **Aplicação** – Interface com o usuário (ex: HTTP, DNS)
2. **Transporte** – Comunicação fim a fim (TCP, UDP)
3. **Internet** – Endereçamento e roteamento (IP)
4. **Acesso à Rede** – Hardware, mídia e enlace de dados

Este é o modelo mais utilizado no dia a dia profissional.

---

## 🧠 Modelo OSI

O modelo **OSI** é um modelo de referência conceitual utilizado para entender e analisar o funcionamento das redes.

### Camadas do Modelo OSI:
1. Física  
2. Enlace de Dados  
3. Rede  
4. Transporte  
5. Sessão  
6. Apresentação  
7. Aplicação  

O modelo OSI é amplamente usado em **troubleshooting** e estudos de redes.

---

## 🔄 Comparação entre OSI e TCP/IP

### Semelhanças
- A camada de Rede do OSI corresponde à camada de Internet do TCP/IP
- A camada de Transporte é equivalente em ambos os modelos

### Diferenças
- O TCP/IP é focado em implementação prática
- O OSI é mais detalhado e didático
- O TCP/IP agrupa funções que o OSI separa em múltiplas camadas

📌 **Resumo prático:**
- TCP/IP → uso operacional
- OSI → análise e entendimento

---

## 🛡️ Importância para SOC e NOC

O entendimento da comunicação em redes é fundamental para:
- Monitorar tráfego de rede
- Identificar comportamentos anômalos
- Analisar incidentes de segurança
- Diagnosticar falhas de conectividade
- Compreender ataques em nível de rede

---

## 📌 Conclusão

Protocolos, padrões e modelos de comunicação são a **base da segurança cibernética**.  
Eles permitem entender como os dados trafegam, onde ocorrem falhas e como proteger a infraestrutura de rede.

> 💡 *Sem entender redes, não existe segurança eficiente.*
