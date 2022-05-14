#COMANDO COM GIT

- INICIAR O GIT
- INICIAR O VERSIONAMENTO
- CRIAR UM COMMIT

-INICIAR O GIT

git init 

git add (Envia arquivos Modified para staged)

git commit (Envia arquivos Staged para Unmodified)


Criando um repositório:

## Crie o diretório do repositório e acesse o mesmo, logo em seguida digite o comando 

$ git init
## logo após o repositório se tornará master

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ ls -a
./  ../  .git/

## Configure o COMMIT adicionando o e-mail e nome do usuario:

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git config --global user.email "davijose@gmail.com"

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git config --global user.name davijaf

## Adicionando um arquivo:

MARKDOWN:

# Título 1
## Título 2
### Título 3
#### Título 4
#####… Título ……


david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ ls
strogonoff.md

# Após criado o arquivo utilize o comando git add * para adicionar o arquivo:
david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git add *

# Após adicionado o arquivo ao repositório crie o commit incluindo comentário:
david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git commit -m "commit inicial"

[master (root-commit) 8ed4b06] commit inicial
 1 file changed, 25 insertions(+)
 create mode 100644 strogonoff.md


## Verificar status do repositório: $ git status

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git status
On branch master
nothing to commit, working tree clean

## Movemos um arquivo para um novo diretório:

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git status
On branch master
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    strogonoff.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        receitas/

no changes added to commit (use "git add" and/or "git commit -a")

## Checando status do repositorio 

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git status
On branch master
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    strogonoff.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        receitas/

no changes added to commit (use "git add" and/or "git commit -a")

## Adicionar mudanças verificadas pelo GIT (Passando arquivos para Staged)
david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git add strogonoff.md receitas/

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        renamed:    strogonoff.md -> receitas/strogonoff.md


## Cria commit para segunda versão:

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git commit -m "Cria pasta receitas e move arquivos para diretorio criado"
[master faa7c04] Cria pasta receitas e move arquivos para diretorio criado
 1 file changed, 0 insertions(+), 0 deletions(-)
 rename strogonoff.md => receitas/strogonoff.md (100%)

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git status
On branch master
nothing to commit, working tree clean

## Criando um terceiro arquivo (index):

$ echo > README.md

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ ls
README.md  receitas/

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README.md

nothing added to commit but untracked files present (use "git add" to track)

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README.md

nothing added to commit but untracked files present (use "git add" to track)

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git add *
warning: LF will be replaced by CRLF in README.md.
The file will have its original line endings in your working directory

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   README.md


david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git commit -m "Cria index Readme.md"                                          
[master 1546c41] Cria index Redme.md
 1 file changed, 4 insertions(+)
 create mode 100644 README.md

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git status
On branch master
nothing to commit, working tree clean


# UTILIZANDO O GITHUB

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git config --list
diff.astextplain.textconv=astextplain
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
http.sslbackend=openssl
http.sslcainfo=C:/Program Files/Git/mingw64/ssl/certs/ca-bundle.crt
core.autocrlf=true
core.fscache=true
core.symlinks=true
pull.rebase=false
credential.helper=manager-core
credential.https://dev.azure.com.usehttppath=true
init.defaultbranch=master
user.email=davijose@gmail.com
user.name=davijaf
core.repositoryformatversion=0
core.filemode=false
core.bare=false
core.logallrefupdates=true
core.ignorecase=true

## REESCREVER CONFIGURAÇÕES:

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git config --global --unset user.email

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git config --global --unset user.name

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git config --list
diff.astextplain.textconv=astextplain
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
http.sslbackend=openssl
http.sslcainfo=C:/Program Files/Git/mingw64/ssl/certs/ca-bundle.crt
core.autocrlf=true
core.fscache=true
core.symlinks=true
pull.rebase=false
credential.helper=manager-core
credential.https://dev.azure.com.usehttppath=true
init.defaultbranch=master
core.repositoryformatversion=0
core.filemode=false
core.bare=false
core.logallrefupdates=true
core.ignorecase=true


david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git config --global user.email "davijose@gmail.com"

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git config --global user.name davijaf

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git config --list
diff.astextplain.textconv=astextplain
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
http.sslbackend=openssl
http.sslcainfo=C:/Program Files/Git/mingw64/ssl/certs/ca-bundle.crt
core.autocrlf=true
core.fscache=true
core.symlinks=true
pull.rebase=false
credential.helper=manager-core
credential.https://dev.azure.com.usehttppath=true
init.defaultbranch=master
user.email=davijose@gmail.com
user.name=davijaf
core.repositoryformatversion=0
core.filemode=false
core.bare=false
core.logallrefupdates=true
core.ignorecase=true

# CRIANDO REPOSITÓRIO NO GITHUB

https://github.com/davijaf/livro-receitas.git


david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git remote add origin https://github.com/davijaf/livro-receitas.git

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git remote add origin https://github.com/davijaf/livro-receitas.git

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git status
On branch master
nothing to commit, working tree clean


david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git push origin master
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 12 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (8/8), 1.10 KiB | 161.00 KiB/s, done.
Total 8 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/davijaf/livro-receitas.git
* [new branch]      master -> master

#Resolvendo Conflitos:

david@DAVIJOSE MINGW64 /d/GitHub/Workspace
$ cd livro-receitas/

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git status
On branch master
nothing to commit, working tree clean

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git remote add origin https://github.com/davijaf/livro-receitas.git
error: remote origin already exists.

