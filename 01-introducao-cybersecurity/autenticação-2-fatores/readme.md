# 🔐 Módulo: Autenticação de Dois Fatores e Autorização Aberta

## 📘 Visão Geral

Este módulo aborda dois pilares fundamentais da segurança digital moderna:  
- **Autenticação de Dois Fatores (2FA)**  
- **Autorização Aberta (OAuth)**

Ambos os mecanismos ajudam a proteger contas, dados e acessos em ambientes online, reduzindo riscos de invasão, roubo de identidade e uso indevido de informações.

---

## 🔑 Autenticação de Dois Fatores (2FA)

A autenticação de dois fatores exige **duas formas de verificação** para garantir que o usuário é realmente quem diz ser.

### ✅ Tipos de fatores:
- **Algo que você sabe**: senha, PIN.
- **Algo que você tem**: smartphone, token físico, app autenticador.
- **Algo que você é**: biometria (impressão digital, reconhecimento facial).

### 🔧 Exemplos de 2FA:
- Código enviado por SMS ou e-mail.
- Aplicativos como Google Authenticator, Authy, Microsoft Authenticator.
- Chaves físicas como YubiKey.

### 🛡️ Benefícios:
- Protege contra ataques de phishing e vazamento de senhas.
- Adiciona uma camada extra de segurança.
- É fácil de implementar e amplamente suportado.

---

## 🔓 Autorização Aberta (OAuth)

**OAuth** é um protocolo que permite que aplicativos acessem informações de um usuário **sem precisar da senha**. Ele é usado para **delegar acesso** de forma segura e controlada.

### 🧠 Como funciona:
1. O usuário tenta acessar um serviço via aplicativo.
2. O app redireciona o usuário para o provedor (ex: Google).
3. O usuário autoriza o acesso.
4. O app recebe um **token de acesso** com permissões específicas.

### 📌 Exemplos:
- Login com Google, Facebook ou Apple.
- Conectar Spotify ao Discord ou Instagram.

### 🔐 Vantagens:
- O usuário não compartilha a senha com o app.
- O acesso pode ser limitado (ex: apenas leitura).
- O usuário pode revogar o acesso a qualquer momento.

---

## 🧠 Conclusão

- **2FA** protege sua conta com uma segunda camada de verificação.
- **OAuth** permite que serviços acessem seus dados de forma segura e controlada.
- Juntos, esses mecanismos fortalecem a **privacidade**, **autonomia** e **segurança digital** do usuário.

