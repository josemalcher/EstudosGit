Estudos Git
==========

Meus estudos e aprendizados sobre o Git. 

###Referências:
[Documentação Oficial](http://git-scm.com/)
[Vídeo aulas: RB Tech - Curso de Git](http://dev.rbtech.info/curso-controle-versao-git-aula-1)

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
10. Git libera o resumo. e Verificar o __status__.

####Ignorar Arquivos .gitignore
1. Criar um novo arquivo: .gitignore.
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