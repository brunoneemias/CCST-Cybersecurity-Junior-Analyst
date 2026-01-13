# 🌐 Módulo 16 – Serviços da Camada de Aplicação

Este módulo aborda os principais **protocolos e serviços da camada de aplicação**, responsáveis por fornecer recursos aos usuários finais, como web, e-mail e transferência de arquivos.

---

## 🖥️ Servidores Web

- Computadores ou programas que **armazenam sites e arquivos** e respondem a requisições de clientes.
- Protocolos: **HTTP (porta 80)** e **HTTPS (porta 443)**.
- Exemplos: **Apache, Nginx, IIS**.
- Funcionamento resumido:
  1. Cliente envia requisição HTTP/HTTPS.
  2. DNS resolve o nome para IP do servidor.
  3. Servidor processa e envia resposta.
  4. Navegador exibe conteúdo.

---

## 📍 URI, URL e URN

| Termo | Função | Exemplo |
| --- | --- | --- |
| **URI** | Identifica recurso genericamente | `urn:isbn:0451450523` |
| **URL** | Localiza recurso na web | `https://site.com/imagem.png` |
| **URN** | Nomeia recurso sem localização | `urn:isbn:9788578270696` |

---

## 📂 FTP – Transferência de Arquivos

- Protocolo para **upload e download de arquivos**.
- Porta de comando: **21**, porta de dados: **20**.
- Cliente FTP conecta ao servidor, autentica e transfere arquivos.

---

## 🔑 Acesso Remoto – Telnet e SSH

**Telnet**
- Conexão remota via TCP/IP (porta 23)
- Sem criptografia (não seguro)
- Uso: teste rápido e sistemas legados

**SSH**
- Substituto seguro do Telnet
- Criptografia, autenticidade e integridade

---

## 📧 E-mail – SMTP, POP3 e IMAP4

### SMTP – Envio de e-mails
- Porta: **25 / 465 / 587**
- Envia mensagens entre cliente e servidor
- Comandos principais: `HELO`, `MAIL FROM`, `RCPT TO`, `DATA`, `QUIT`
- Segurança: **SSL/TLS**, SPF, DKIM, DMARC

### POP3 – Recebimento local
- Porta: **110 / 995**
- Baixa e-mails do servidor e normalmente remove do servidor
- Vantagens: acesso offline, simples
- Desvantagens: não sincroniza múltiplos dispositivos

### IMAP4 – Recebimento online
- Porta: **143 / 993**
- Mensagens permanecem no servidor
- Sincroniza ações entre todos os dispositivos
- Ideal para múltiplos dispositivos e acesso remoto

---

## 🧠 Resumo Prático

- **Web:** HTTP/HTTPS → Servidores e navegação  
- **FTP:** Transferência de arquivos → Portas 20/21  
- **E-mail:** SMTP (envio), POP3 (recebe local), IMAP4 (recebe sincronizado)  
- **Acesso remoto:** Telnet (inseguro) → SSH (seguro)

---

## 📌 Status do Módulo

✅ **Concluído**
