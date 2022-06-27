# INÍCIO ⭐
 
 ### COMANDOS:
 
 ls: lista o que contém no diretório;
 
 cd (diretóro): Migra de diretório;
 
 cat: Lê o que contém no arquivo;
 
 dir: Lista todos os diretórios que contém;
 
 cd /: Volta para a base C/;
 
 cd ..: Volta um diretório;
 
 cls: Limpa o terminal;
 
 tecla "Tab": Completa a esscrita;
 
 mkdir: Cria diretório;
 
 echo: Escreva;
 
 > : Direciona para um arquivo;

 Del: Apaga o coneúdo da pasta;
 
 rmdir (pasta) /s: Apaga a pasta e os arquivos.
 
 
### - SSH O QUE É ?
É uma forma de estabelecer uma conexão segura e encriptada entre duas máquinas. Neste caso se conectando com o servidor do GitHub e a nossa máquina local, assim sendo confiável a conexão. Utilizando sempre 2 chaves, uma pública e uma privada. A pública será colocada no GitHub, isto é, todos os repositórios que tiverem na máquina local por esse processo SSH, o GitHub ja vai conhcer a máquina local, irá ter uma conexao prévia e estabelecida, sendo assim capaz de enviar código sem nem mesmo precisar colocar a senha.
  
### COMO FAZER?

  1- Faça o Download e instale o Git pelo sie: https://git-scm.com/download/

  2 - Clique no ícone da sua imagem após ter criado sua conta no GitHub e realizado o login, depois em "Settings" e depois em "SSH and GPG keys".
  
  3- Clique em "New SSH key".
  
  4- Abra o terminal do Git Bash, e digite o seguinte comando:

$ ssh-keygen -t ed25519 -C (aqui digite seu email que usou no GitHub)
 
  5- Tecle enter uma vez e depois digite uma senha, tecle enter, e digite novamente a senha confirmando; digite:

$ cd /c/Users/(seu usuário)/.ssh/

$ ls 

id_ed25519 id_ed25519.pub
 
$ cat id_ed25519.pub

(chave pública)

  6- Aparecerá uma linha de código (usamos cat para ler o arquivo) no caso a chave pública, termina com o final .pub. Copiamos a chave pública e colamos na site do GitHub a onde está "key" e em "Tittle" escolhemos algo para identificar a chave, exemplo, "Priemira chave máquina windows". Podemos usar o comando " pwd " para saber a onde estamos e qual o caminho do diretório.

  7- Agora faremos o agente para pode identificar a nosa chave privada. Digite o comando:

$ eval $(ssh-agent -s)

Agent pid (número)

$ ls

id_ed25519  id_ed25519.pub

  8-Adicionamos o agente a nossa chave privada:
  
$ ssh-add id_ed25519

### SALVAR REPOSITÓRIOS NO LOCAL

  1-Agora criaremos nossa pasta de trabalho a onde armazenamos nossos repositóros; vamos voltar a ter chegar a pasta C/:

$ cd ..

$ cd ..

$ cd ..

$ mkdir Workspace

$ ls

   2-Usando o comando "mkdir" para criar a pasta "Workspace" e depois um "ls" para vê-la. Agora iremos para "Workspace" e criaremos uma nova pasta com nome de "Livro-receitas": 

$ cd Workspace/

$ mkdir livro-receitas

$ ls

livro-receitas/
  
$ cd livro-receitas/

  3-Damos um "git init" criando um novo repositório do Git. Ele pode ser usado para converter um projeto existente e não versionado em um repositório do Git ou inicializar um novo repositório vazio.

$ git init

Initialized empty Git repository in C:/Workspace/livro-receitas/.git/

$ ls

$ ls -a

./  ../  .git/

  4-Utilizamos a flag "-a" com "ls" para assim conseguir ver pastas ocultas e agora iremos entrarpara conhecer um pouco mais;

$ cd .git/

$ ls

HEAD  config  description  hooks/  info/  objects/  refs/

  5-Podemos ver que temos dentro do diretóro do Git/ as configurações de estrutura e até mesmo os objetos que contém, isso foi para mostrar que mesmo aparetemente não havendo nada, mas por baixos dos panos, contêm dados no diretório, agora voltaremos para livro-receitas/:

$ cd ..

  6-Digitaremos o comando para criar pela primeira vez, o email e o nome para o objeto commit seja criado por um autor:

$ git config --global user.email "seu email"

$ git config --global user.name "seu nome"

### CRIAR UM ARQUIVO MARKDOWN

  1-Faça o download do software Typora para criar um arquivo com extensão markdown. Abra o software e crie um texto, seguinte esse exemplo de receita, usarei o bolo de cenoura:
  
  # Bolo de Cenoura :birthday:

**INGREDIENTES**

- 1/2 xícara (chá) de óleo
- 3 cenouras médias raladas
- 4 ovos
- 2 xícaras (chá) de açúcar
- 2 e 1/2 xícaras (chá) de farinha de trigo
- 1 colher (sopa) de fermento em pó
- COBERTURA
- 1 colher (sopa) de manteiga
- 3 colheres (sopa) de chocolate em pó
- 1 xícara (chá) de açúcar
- 1 xícara (chá) de leite

**MODO DE PREPARO DA MASSA**

​	1. Em um liquidificador, adicione a cenoura, os ovos e o óleo, depois misture.

​	2. Acrescente o açúcar e bata novamente por 5 minutos.

​	3. Em uma tigela ou na batedeira, adicione a farinha de trigo e depois misture novamente.

​	4. Acrescente o fermento e misture lentamente com uma colher.

​	5. Asse em um forno preaquecido a 180° C por aproximadamente 40 minutos.

**COBERTURA**
	6.Despeje em uma tigela a manteiga, o chocolate em pó, o açúcar e o leite, depois misture.

 7. Leve a mistura ao fogo e continue misturando até obter uma consistência cremosa, depois despeje a calda por cima do bolo.

    ​	Agora só servir :D

  2-Feito, clique em arquivo e salvar como no lado esquerdo superior do Typora e escolha o nome para o arquivo, nesse caso será "Bolo.md".
  
  3- Digitaremos o comando a seguir para pegar tudo que conter na pasta para ele gerar um commit:
  
$ git add *
  
$ git commit -m "commit inicial"

[master (root-commit) (início do sha1)] commit inicial

1 file changed, 34 insertions(+)
 
create mode 100644 Bolo.md

  4-Para saber como está o commit, basta digitar:
  
 $ git status
  
  5-Como resposta ao comando de cima, deverá aparecer logo abaixo:
  
On branch master

nothing to commit, working tree clean

$ls

Bolo.md

$ mkdir receitas

$ ls

Bolo.md receitas/

$ mv Bolo.md ./receitas/

$ ls
receitas/

  6-Criamos uma nova pasta dentro de livro-rceitas uma chamda receitas e movemos com "mv" o arquivo do Bolo.md para dentro dela. Podemos vê-la migrando para a pasta:
  
$ cd receitas/
  
$ls
  
Bolo.md
  
$ cd ..
  
  7-Voltamos, e agora veremos novamnte ver o status, deverá ser respondido asssim:
  
$ git status

On branch master

Changes not staged for commit:

  (use "git add/rm <file>..." to update what will be committed)
  
  (use "git restore <file>..." to discard changes in working directory)
  
        deleted:    Bolo.md

Untracked files:
  
  (use "git add <file>..." to include in what will be committed)

  8-O Git nos responde que não esta no estado "staged" e o arquvi foi deletado, isso porque, não conhece a pasta criada a onde o arquvi foi movido, então devemos adicona-lo ao Git. Usamos os comando:
  
$ git add Bolo.md Receitas/

  9-Feito isso, vamos ver o status, aparecerá:
  
$ git status
  
On branch master
  
Changes to be committed:
  
  (use "git restore --staged <file>..." to unstage)
  
        renamed:    Bolo.md -> Receitas/Bolo.md

  10-Isso significa que adicionamos a nova pasta "receitas/" no Git, pois ele não conhecia, agora ele diz que devemos fazer um commit sobre:
  
$ git commit -m "pasta Receitas sobremesa"
  
[master 671ed4f] pasta Receitas sobremesa
  
1 file changed, 0 insertions(+), 0 deletions(-)
  
rename Bolo.md => Receitas/Bolo.md (100%)

$ git status
  
On branch master
  
nothing to commit, working tree clean

$ ls

receitas/
  
  11-Agora criaremos uma "capa" para nosso livro utilizando o seguinte comando:

$ echo > README.md
  
$ ls

README.md  Receitas/

$ git status
  
On branch master
  
Untracked files:
  
(use "git add <file>..." to include in what will be committed)
  
 README.md
  
 nothing added to commit but untracked files present (use "git add" to track)
  
  12-Utilizamos o comando que junta tudo que o que há de novo para adicionar ao Git:
  
$ git add *
  
warning: LF will be replaced by CRLF in README.md.
  
The file will have its original line endings in your working directory
  
$ git status
  
On branch master
  
Changes to be committed:
  
  (use "git restore --staged <file>..." to unstage)
  
        new file:   README.md
  
  13-Novamente fazemos um commit sobre:
  
  $ git commit -m "adicona index"
  
[master b04ed4f] adicona index
  
 1 file changed, 5 insertions(+)
  
 create mode 100644 README.md
  
## COMO EMPURRAR NOSSO REPOSITÓRIO PARA O GITHUB
  
  1-No site do GitHub, vamos clicar no ícone da nossa imagem e clicar em "your repositories" e clicar em "New".Escolhemos o nome, nesse caso será "Livro_Receitas", podemos decidir será deixaremos público ou privado, nesse exemplo será público. Se caso não tivessemos feitos o arquivo README.md, poderiamos selecionar a opção que o GitHub, cria para ele mesmo, como não é esse o caso, no exemplo apresentado, não iremos seleciona-lo e clicamos em "Create repository".

  Feito isso iremos selecionar e copiar o link onde está localizado em baixo da frase "...or push an existing repository from the command line"
  
  2-Agora voltamos para o terminal no Git. Temos que criar uma origem, para isso faremos uma variável chamado "origin" para não precisar colocar todas vezes o link, segue o comando:
  
$ git remote add origin (link copiado)
  
$ git remote -v
  
origin  (link) (fetch)
  
origin  (link) (push)
  
  3-Veremos como está o status para saber se está tudo ok e se podemos enviar o GitHub:
  
$ git status
  
On branch master
  
nothing to commit, working tree clean
  
  4-Finalmente concluiremos empurrando no repositório para o GitHub com o seguinte comando:
  
$ git push origin master
  
Enumerating objects: 8, done.
  
Counting objects: 100% (8/8), done.
  
Delta compression using up to 4 threads
  
Compressing objects: 100% (6/6), done.
  
Writing objects: 100% (8/8), 1.26 KiB | 431.00 KiB/s, done.
  
Total 8 (delta 0), reused 0 (delta 0), pack-reused 0
  
To (link)
  
 * [new branch]      master -> master
  
  
  
  ## 🔥 ATENÇÃO 🔥
  
  Se suas crendencias do GitHub não forem as mesma do Git, terá futuro problema quando você fazer commits ou a plataforma, para verificar isso, veja como está sua credencias no Git no seguinte comando:
  
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
  
user.email= (seu email)
  
user.name= (Seu nome)
  
core.repositoryformatversion=0
  
core.filemode=false
  
core.bare=false
  
core.logallrefupdates=true
  
core.symlinks=false
  
core.ignorecase=true
  
