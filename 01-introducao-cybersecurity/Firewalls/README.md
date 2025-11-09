# 🔥 Firewalls

Este módulo apresenta os diversos tipos de **firewalls**, dispositivos ou softwares que atuam como barreiras de proteção entre redes confiáveis e redes externas. Eles monitoram, filtram e controlam o tráfego de rede com base em regras de segurança.

---

## 🧱 Tipos de Firewalls por Camada

### 🌐 Firewall de Camada de Rede
- **Atuação:** Filtra pacotes com base em IP, protocolo e porta.
- **Vantagem:** Rápido e eficiente para bloquear tráfego indesejado.
- **Limitação:** Não analisa o conteúdo dos pacotes.

### 🚚 Firewall de Camada de Transporte
- **Atuação:** Analisa conexões TCP/UDP e pode bloquear sessões específicas.
- **Vantagem:** Mais controle sobre fluxos de comunicação.
- **Limitação:** Menos eficaz contra ataques baseados em conteúdo.

### 🧠 Firewall de Camada de Aplicação
- **Atuação:** Inspeciona o conteúdo das mensagens (HTTP, FTP, DNS etc.).
- **Vantagem:** Detecta ataques específicos como SQL Injection ou XSS.
- **Limitação:** Pode impactar o desempenho da rede.

---

## 🧠 Firewall Sensível ao Contexto

- **Atuação:** Analisa o estado da conexão e o contexto da comunicação.
- **Vantagem:** Permite decisões mais inteligentes e dinâmicas.
- **Exemplo:** Permitir respostas apenas para conexões iniciadas internamente.

---

## 🧭 Servidor Proxy

- **Função:** Intermedia a comunicação entre o usuário e a Internet.
- **Vantagem:** Oculta o IP real do cliente e pode aplicar políticas de acesso.
- **Uso comum:** Controle de navegação e filtragem de conteúdo.

---

## 🔁 Proxy Reverso

- **Função:** Intermedia o acesso externo a servidores internos.
- **Vantagem:** Protege servidores web, distribui carga e aplica segurança.
- **Uso comum:** Hospedagem segura de sites e APIs.

---

## 🔄 NAT (Network Address Translation)

- **Função:** Traduz endereços IP privados em públicos e vice-versa.
- **Vantagem:** Oculta a estrutura interna da rede e economiza IPs públicos.
- **Uso comum:** Roteadores domésticos e corporativos.

---

## 🖥️ Firewall Baseado em Host

- **Função:** Instalado diretamente em dispositivos (PCs, servidores).
- **Vantagem:** Protege o sistema contra acessos locais e remotos.
- **Uso comum:** Segurança individual de endpoints.

---

> 💡 *Este conteúdo faz parte do módulo 4.1.3 da trilha CCST Cybersecurity – Junior Analyst, oferecida pela Cisco Networking Academy.*
