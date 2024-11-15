# Documentação de comandos Git

**Esta documentação foca em:**

- Documentar e explicar comandos;
- Documentar tutorias.

**Cursos de Git e Github que recomendo:**

- [Git e Github para iniciantes por Willian Justen](https://www.youtube.com/playlist?list=PLlAbYrWSYTiPA2iEiQ2PF_A9j__C4hi0A);
- [Git e Github na vida real por Willian Justen](https://www.youtube.com/playlist?list=PLlAbYrWSYTiNqugqFFWWsgONJsmc3eMpg).

# Sumário

- [Gerando chaves ssh](#gerando-chaves-ssh);
- [Adicionando uma chave ssh pública no Github](#adicionando-uma-chave-ssh-pública-no-github);
- [Comandos](#comandos).

# Gerando chaves ssh

Execute os comandos abaixo em ordem:

```bash
# Cria uma nova chave ssh usando o e-mail fornecido como label
ssh-keygen -t ed25519 -C "[your_email@example.com]"

# Inicia o ssh-agent em segundo plano
eval "$(ssh-agent -s)"

# Adiciona uma chave privada no ssh-agent
ssh-add ~/.ssh/id_ed25519
```

[Documentação oficial](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent).

# Adicionando uma chave ssh pública no Github

Execeute o comando abaixo:

```bash
# Exibe a chave pública
# Após executar o comando, copie o conteúdo para a área de transferência
cat ~/.ssh/id_ed25519.pub
```

Após copiar a chave, acesse sua conta do Github e acesse a página: Configurações > Chaves ssh e gpc > Nova chave ssh.

Nessa página será solicitado o título e a chave.

[Documentação oficial](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account).

# Comandos

```bash
# Define o nome do usuário globalmente
git config --global user.name "[NOME]"

# Define o email do usuário globalmente
git config --global user.email "[EMAIL]"

# Define um editor de texto como padrão
git config --global core.editor "[EDITOR] --wait"

# Cria um alias para um comando
git config --global alias.s status

# Exibe todas as configurações
git config --list

# Exibe uma configuração
git config user.name

# Remove uma configuração
git config --unset [CONFIGURACAO]

# Inicializa um repositório local
git init

# Define uma origem
git remote add [ORIGEM] [URL]

# Exibe o nome das origens cadastradas
git remote

# Exibe o nome e URL das origens cadastradas
git remote -v

# Remove uma origem
git remote remove [ORIGEM]

# Clona um repositório remoto localmente
git clone [URL]

# Clona um repositório remoto localmente no diretório atual
git clone [URL] .

# Exibe o estado atual dos arquivos
git status

# Adiciona um arquivo na staged
git add [ARQUIVO]

# Adiciona todos os arquivos na staged
git add .

# Faz um commit simples dos arquivos que estão na staged
git commit -m "[MENSAGEM]"

# Faz um commit simples dos arquivos modificados e que estão na staged
git commit -am "[MENSAGEM]"

# Faz um commit completo com cabeçalho, corpo e rodapé
git commit

# Edita o commit mais recente
git commit --amend

# Atualiza o repositório local
git pull -u [ORIGEM] [BRANCH]

# Atualiza o repositório remoto
git push -u [ORIGEM] [BRANCH]

# Força atualização do repositório remoto
git push -f

# Exibe a branch atual e as disponíveis
git branch

# Cria uma nova branch
git branch [BRANCH]

# Remove uma branch
git branch -D [BRANCH]

# Remove uma branch do repositório remoto
git push --delete [BRANCH]

# Troca de branch
git checkout [BRANCH]

# Troca para a branch antes da atual
git checkout -

# Cria e troca para uma nova branch
git checkout -b [BRANCH]

# Restaura um arquivo
git checkout [ARQUIVO]

# Junta duas branches
git merge [BRANCH]

# Replica os commits de uma branch em outra
git rebase [BRANCH]

# Exibe um histórico detalhado de commits
git log

# Filtra o histórico por autor
git log --author="[AUTOR]"

# Exibe o histórico graficamente
git log --graph

# Exibe um resumo do histórico de commits
git shortlog

# Filtra o resumo por autor
git shortlog --author="[AUTOR]"

# Exibe a quantidade de commits por autor
git shortlog -sn

# Exibe o que foi feito em um commit
git show [HASH]

# Exibe o que foi feito até o momento
git diff

# Exibe apenas os nomes dos arquivos modificados
git diff --name-only

# Tira um arquivo da staged
git reset HEAD [ARQUIVO]

# Desfaz um commit e coloca os arquivos na staged
git reset --soft [HASH]

# Desfaz um commit e coloca os arquivos fora da staged
git reset --mixed [HASH]

# Desfaz um commit e descarta todas as alterações
git reset --hard [HASH]

# Reverte um commit
git revert [HASH]

# Armazena as alterações temporariamente
git stash push -m "[MENSAGEM]"

# Lista todas as stashes
git stash list

# Aplica uma stash
git stash pop [INDICE]

# Remove uma stash
git stash drop stash@{[INDICE]}

# Remove todas as stashes
git stash clear

# Cria um "ponto" no histórico de commits
git tag -a [TAG] -m "[MENSAGEM]"

# Lista todas as tags
git tag

# Remove uma tag
git tag -d [TAG]

# Envia uma tag para o repositório remoto
git push [ORIGEM] [TAG]

# Envia todas as tags para o repositório remoto
git push [ORIGEM] [BRANCH] --tags

# Remove uma tag do repositório remoto
git push --delete [ORIGEM] [TAG]
```
