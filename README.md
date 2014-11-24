Estudos Git
==========

Meus estudos e aprendizados sobre o Git. 

###Referências:
[Documentação Oficial](http://git-scm.com/)
[Vídeo aulas: RB Tech - Curso de Git](http://dev.rbtech.info/curso-controle-versao-git-aula-1)

------

###Aula vídeo 1
O que é, e para que serve?
Sobre os estágios do Git: 
Working Directory -> **git add** -> Staging Area -> __git commit__ ->Git Diretctory
Instalalção.
Configurações Iniciais, após a instalação:
```
git config --global user.name "José"
git config --global user.email "malcher@josemalcher.net"
```
[Link do Vídeo 1](http://dev.rbtech.info/curso-controle-versao-git-aula-1/)

------    
###Aula vídeo 2
Início, desenvilvimento Local.
1. Criar um Repositório para controlar as versões. Determinar a pasta(ex.: /www/projeto1).
2. Básico de terminal. Entrar e sair da pasta, listar pasta, limpar tela.
3. Comando para iniciar o projeto no git:

```
    git init
```
4. Pasta Oculta **.git** é criada para armazenar dados do projeto pro git.
5. Verificar o status do git, comando:
```
    git status
```
6. Adicionar e editar arquivos. E vericar o Status.
7. Adicionar os arquivos no controle de versão
```
    git add nomeDoarquivo.txt
    git add *.txt
    git add . //Adiciona todos os arquivos
```
8. Verificar o git status.
9. Confirmar as alterações __commit__
```
    git commit -m "Mensagem inicial"
```
10. Git libera o resumo. Verificar o __status__.

####Ignorar Arquivos .gitignore
1. Criar um novo arquivo: **.gitignore**.
```
    .gitignore
    nomeDoarquivo.txt
    //Para pastas:
    temp/
```
####Atalho
```
    git commit -a -m "Mensagem"
```
[Link do Vídeo 2](http://dev.rbtech.info/curso-controle-versao-git-aula-2/)

------

###Aula vídeo 3

Visualização detalhada das alterações, no diretorio de trabalho.
```
    git diff
```
Pra saber o que há na Stage Area, comendo:
```
    git diff --staged
```
####Histórico de todos os Commites
```
    git log
    // mostra o diff, o que foi feito em cada commit(git log+ diff).
    git log -p
    //Exibir o ultimo commite
    git log -p -1
    //resumido: cod + mensagem do commit
    git log --pretty=oneline
    
    //recomendação: visualizar pelo gui
    gitk
```
[Link do Vídeo 3](http://dev.rbtech.info/curso-controle-versao-git-aula-3)

------

###Aula vídeo 4
Desfazer alterações, "editar o ultimo commit"
Ex.: __commit__ antes da hora, editar o comite mais recente
```
    git commit --amend -m "novas funcionalidades (edicao)"
    //adicionou mais dados ao antigo commit
```
Tirar o arquivo do StageArea.
```
    git reset HEAD nomeDoArquivo.txt
```

Reverter alterações do arquivo, descartar mudanças no WorkDirectory, volta ao estado inicial
```
    git checkout -- nomeDoArquivo.txt
```
Ao deletar um arquivo, remoção de arquivo.
```
    git rm nomeDoarquivo.txt
```

------

###Aula vídeo 5
Tags, marcar versões, serve como atalho. Criada no Commit atual.
```
    //Listar Tags
    git tag
    
    //adicionar tag, -a -> tag anotada
    git tag -a NomeDaTag -m "mensagem"
```
Criar no commit Antigos
```
    git tag -a NomeDaTag CODEChaveDoCommit -m "detalhes da tag"
```
Mais detalhes sobre a tag
```
    git show NomeDaTag
```
Usando Tag(Ponteiro): Visualizar os arquivos de Tags, exemplo antigos commit. Faz a troca dos arquivos
```
    git checkout NomeDaTag
    //voltar ao original
    git checkout master
```
Deletar uma tag
```
    git tag -d NomeDaTag
```

####Branch
Principal: master
Cria-se, por exemplo, um "ambiente" de teste
```
    //Cria um novo branch
    git branch teste
    //muda o workdirector para teste
    git checkout teste
    
    //Atalho para criar e mudar par ao novo branch
    git checkout -b teste
```
Ao final da conclusão do ambiente de "teste", levar as alteração para o __branch Master__
```
    //Tem que estar no Princial(master), o destino!
    git merge teste
```
Para listar todo os __branch__ existentes
```
    git branch
```
Deletar o branch
```
    git branch -d NomeDoBransh
```

------
###Aula vídeo 6
Git e Rede Local, usar uma maquina com repositório.
- Compartilhar uma pasta de projeto em Rede.
1 - Acessar a compartilhada pelo terminal
```
    git init --bare
```
2 - Primeiro acesso é preciso Clonar o repositorio, para iniciar, depois enviar para servidor.
```
    git clone file:////vmserver/projetos/cliente1 NomeProjetoRede
```
3 - Adiciona os arquivos... esctrutura, etc.
```
    git add .
    git commit -m "projeto pronto tal tal tal"
```
4 - Enviar os arquis para o Servidor, é preciso saber o nome do servidor remoto
```
    //nome do servidor remoto
    git remote
    //"git, envie os arquivos que estão no servidor 'origin' do bransh master"
    git push origin master
```
5 - para testar, fazer um clone do projeto com outro nome!
6 - Para __recuperar__ ou pegar atualizações do __servidor__
```
    git pull origin master
    //faz a busca dos dados e merge dos dados.
```
7 - O comendo __fech__ não faz o merge automático, ele alocar em um branch
```
    git fetch origin NomeDoBranch
    //
```
