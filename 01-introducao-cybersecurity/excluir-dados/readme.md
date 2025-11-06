# 🧹 Exclusão Segura de Dados: Como Apagar Arquivos Permanentemente

## ❓ Por que excluir dados de forma segura?

Quando você exclui um arquivo e esvazia a lixeira, o sistema operacional apenas **marca o espaço como disponível**, mas os dados ainda podem ser recuperados com ferramentas forenses. Para garantir que informações sensíveis não caiam em mãos erradas, é essencial usar métodos de **exclusão segura**.

---

## 🪟 Windows: SDelete (Secure Delete)

**SDelete** é uma ferramenta da Microsoft Sysinternals que sobrescreve os dados antes de apagá-los, tornando impossível a recuperação.

### 🔧 Como usar:
1. Baixe o SDelete em: [Microsoft Sysinternals](https://learn.microsoft.com/en-us/sysinternals/downloads/sdelete)
2. Extraia o conteúdo e abra o **Prompt de Comando** como administrador.
3. Execute o comando:
   ```bash
   sdelete -p 3 -s "C:\caminho\para\arquivo_ou_pasta"
  -p 3: sobrescreve os dados 3 vezes.
  -s: aplica de forma recursiva em subpastas.

##🐧 Linux: shred
**shred** é uma ferramenta nativa do Linux que sobrescreve arquivos com dados aleatórios antes de excluí-los.

### 🔧 Como usar:
     ```bash
     sdelete -p 3 -s "C:\caminho\para\arquivo_ou_pasta"

- -u: remove o arquivo após sobrescrever.

- -v: mostra o progresso.

- -n 3: número de sobrescritas.

📌 Nota: shred funciona melhor em sistemas de arquivos como ext3/ext4. Pode não ser eficaz em sistemas com journaling ou SSDs.

## 🍏 macOS: Secure Empty Trash
Em versões anteriores do macOS (até El Capitan), havia a opção Secure Empty Trash, que sobrescrevia os dados ao esvaziar a lixeira.

## 🧹 Como usar:
- Mova os arquivos para a Lixeira.

- Clique com o botão direito na Lixeira.

- Selecione Secure Empty Trash.

⚠️ Importante: essa função foi removida nas versões mais recentes do macOS. Alternativas incluem:

- Usar o Terminal com srm (se disponível).

- Utilizar ferramentas como Permanent Eraser.

💽 Descarte de Discos Rígidos
Se você precisa se livrar de um HD ou SSD:

- Use ferramentas de wipe como DBAN ou diskpart.

- Para máxima segurança, considere a destruição física do disco.

## ✅ Conclusão
Excluir dados de forma segura é uma prática essencial para proteger sua privacidade. Seja ao apagar arquivos, formatar discos ou descartar dispositivos, sempre utilize ferramentas confiáveis para garantir que os dados não possam ser recuperados.
