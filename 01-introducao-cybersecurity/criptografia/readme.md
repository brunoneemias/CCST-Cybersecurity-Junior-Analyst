# 🔐 Criptografia e Proteção de Dados com EFS no Windows

## 📘 O que é Criptografia?

Criptografia é o processo de transformar informações legíveis (texto simples) em um formato codificado (texto cifrado), de modo que apenas pessoas autorizadas possam acessá-las. Ela é uma das principais ferramentas para garantir a **confidencialidade**, **integridade** e **autenticidade** dos dados.

Existem dois tipos principais de criptografia:
- **Simétrica**: usa a mesma chave para criptografar e descriptografar.
- **Assimétrica**: usa um par de chaves — uma pública e uma privada.

A criptografia é essencial para proteger dados sensíveis contra acessos não autorizados, especialmente em dispositivos como laptops, que podem ser perdidos ou roubados.

---

## 🔧Como você criptografa seus dados?

No Windows, uma das formas mais práticas de criptografar arquivos e pastas é utilizando o **EFS (Encrypting File System)**, um recurso nativo do sistema operacional.

### ✅ Etapas para criptografar arquivos com EFS no Windows

1. **Localize o arquivo ou pasta**
   - Navegue até o arquivo ou pasta que deseja criptografar.

2. **Clique com o botão direito**
   - Selecione **"Propriedades"** no menu de contexto.

3. **Acesse a aba "Geral"**
   - Clique no botão **"Avançados..."**.

4. **Ative a criptografia**
   - Marque a opção **"Criptografar o conteúdo para proteger os dados"**.
   - Clique em **"OK"** e depois em **"Aplicar"**.

5. **Escolha o escopo da criptografia**
   - O Windows perguntará se você deseja criptografar apenas o arquivo ou a pasta inteira com todos os arquivos e subpastas.
   - Escolha a opção desejada e clique em **"OK"**.

6. **Backup da chave de criptografia**
   - Após a criptografia, o Windows pode solicitar que você **faça backup do certificado de criptografia**.
   - **Importante**: Faça esse backup e guarde-o em um local seguro. Sem ele, você poderá perder o acesso aos arquivos criptografados caso o sistema seja reinstalado ou o perfil de usuário seja perdido.

---

## 🛡️ Considerações Finais

- O EFS é uma solução eficaz para proteger dados em dispositivos pessoais e corporativos.
- Ele é transparente para o usuário: os arquivos criptografados são acessados normalmente por quem tem a chave correta.
- No entanto, **não substitui o uso de senhas fortes, backups regulares e antivírus atualizados**.

---

📎 *Este conteúdo foi inspirado na seção 3.2.2 do curso "Introdução à Cibersegurança" da Cisco Networking Academy.*
