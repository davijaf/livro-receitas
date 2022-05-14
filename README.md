#COMANDO COM GIT

- INICIAR O GIT
- INICIAR O VERSIONAMENTO
- CRIAR UM COMMIT

#INICIAR O GIT

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

## Após adicionado o arquivo ao repositório crie o commit incluindo comentário:
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

# REESCREVER CONFIGURAÇÕES:

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


david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ ls
README.md  receitas/

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git status
On branch master
nothing to commit, working tree clean

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git add *
warning: LF will be replaced by CRLF in README.md.
The file will have its original line endings in your working directory

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git commit -m "Adiciona dados da aula no Readme.md"
[master f0984d9] Adiciona dados da aula no Readme.md
 1 file changed, 306 insertions(+), 4 deletions(-)
 rewrite README.md (100%)

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git status
On branch master
nothing to commit, working tree clean

## ENVIAR A VERSÃO ATUALIZADA PARA REPOSITÓRIO
david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git push origin master
To https://github.com/davijaf/livro-receitas.git
 ! [rejected]        master -> master (fetch first)
error: failed to push some refs to 'https://github.com/davijaf/livro-receitas.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.


# BAIXAR A VERSÃO ATUALIZADA PARA REPOSITÓRIO
david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git pull origin master
remote: Enumerating objects: 8, done.
remote: Counting objects: 100% (8/8), done.
remote: Compressing objects: 100% (6/6), done.
remote: Total 6 (delta 1), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (6/6), 3.17 KiB | 2.00 KiB/s, done.
From https://github.com/davijaf/livro-receitas
 * branch            master     -> FETCH_HEAD
   1546c41..5d29f70  master     -> origin/master
Auto-merging README.md
CONFLICT (content): Merge conflict in README.md
Automatic merge failed; fix conflicts and then commit the result.

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master|MERGING)
$ git status
On branch master
You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)
        both modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master|MERGING)
$ git add *

david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master|MERGING)
$ git commit -m "resolve conflitos"
[master 0f5ea40] resolve conflitos

## Faz upload de sua versão para GitHub
david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git push origin master
Enumerating objects: 10, done.
Counting objects: 100% (10/10), done.
Delta compression using up to 12 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (6/6), 720 bytes | 144.00 KiB/s, done.
Total 6 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 1 local object.
To https://github.com/davijaf/livro-receitas.git
   5d29f70..0f5ea40  master -> master

## Verificar qual repositório está apontado no GitHub
david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ git remote -v
origin  https://github.com/davijaf/livro-receitas.git (fetch)
origin  https://github.com/davijaf/livro-receitas.git (push)

## Lista diretórios ocultos
david@DAVIJOSE MINGW64 /d/GitHub/Workspace/livro-receitas (master)
$ ls -a
./  ../  .git/  README.md  receitas/
