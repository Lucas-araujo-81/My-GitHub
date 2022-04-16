# **Principais Códigos e Dicas**.

## **Instalação**

https://msysgit.github.com

## **git config**

git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
(_Definir usuário e Email_)

## **git init**

(_Cria um diretório chamado .git, que contém todos os arquivos necessários_)

## **git clone**

git clone git://github.com/schacon/grit.git
(_clona um diretório direto da web_)

## **git add**

git add README
(_Adciona os itens ao monitoramento do git, e torna parte do commit_)

## **git status**

_A principal ferramenta utilizada para determinar quais arquivos estão em
quais estados é o comando:_

**git status**

 "On branch master
 Untracked files:
 (use "git add {file}..." to include in what will be committed)

 README
nothing added to commit but untracked files present (use "git add" to track)" 

(_erros caso execute comando antes do **git add**_)

## **git diff**

(_Se o comando git status for muito vago — você quer saber exatamente o que você alterou_)

## git commit

(_Armazena o conteúdo atual do índice em um novo commit, juntamente com uma mensagem 
de registro do usuário que descreve as mudanças_.)

 - Se usa o commit depois de já ter feito o git add, para fazer o commit:

**git commit -m "Mensagem"**

 - Para commitar também os arquivos versionados mesmo não estando no Stage basta adicionar o parâmetro -a

**git commit -a -m "Mensagem"**

 - Refazendo commit quando esquecer de adicionar um arquivo no Stage:

**git commit -m "Mensagem" --amend**

## **git reset**

(_Desfazer modificações_)

 - Para voltar ao último commit:

**git reset --hard HEAD~1**

 - Para voltar ao último commit e mantém os últimos arquivos no Stage:

**git reset --soft HEAD~1**

 - Volta para o commit com a hash XXXXXXXXXXX:

**git reset --hard XXXXXXXXXXX**

 - Para visualizar os hashs

**git reflog**

 - E para aplicar:

**git merge {hash}**

## **git rm**

(_Para remover um arquivo do Git_)

 - remove o arquivo do seu diretório para você não ver ele como arquivo não monitorado 
(untracked file) na próxima vez.

**git rm -f {arquivo}**

## **git mv**

(_Diferente de muitos sistemas VCS, o Git não monitora explicitamente arquivos movidos.
É um pouco confuso que o Git tenha um comando mv_.) 

 - Se você quiser renomear um arquivo no Git, você pode fazer isso com

**git mv arquivo_origem arquivo_destino**

(_e funciona. De fato, se você fizer algo desse tipo e consultar o status,
 você verá que o Git considera que o arquivo foi renomeado_.)

 - No entanto, isso é equivalente a rodar algo como:

**mv README.txt README
git rm README.txt
git add README**