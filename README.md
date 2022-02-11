# Primeiro PR
Repositório destinado a ensinar o básico de Git/GitHub aos integrantes do PET-SI

## Introdução

Nosso objetivo é criar um PR (Pull Request) contendo uma alteração/atualização para este projeto. Para isto, precisaremos aprender alguns termos e alguns comandos.

Primeiramente, vamos instalar o Git e criar uma conta no GitHub.

> Atenção! Git e GitHub não são a mesma coisa!
> - *GitHub* é um site de hospedagem de códigos. Ele ajuda desenvolvedores a compartilhar seus códigos facilmente através do *Git*;
> - O *Git* por sua vez é um programa de versionamento de código. Ele ajuda a gerenciar várias versões de um projeto, cada uma contendo alterações em diversos arquivos, realizadas por quaisquer número de usuários. Git não é usado somente no GitHub, mas também no GitLab, BitBucket e diversas outras plataformas. É um programa essencial para qualquer desenvolvedor, e muito simples de se usar.

Para instalar o Git é bem tranquilo:
- Nas distribuições Linux, simplesmente digite `sudo apt-get install git` ou comando equivalente da sua distro
- Para Windows, use o instalador disponível no [site do Git](https://git-scm.com/download/win) ou, caso tenha o winget: `winget install --id Git.Git -e --source winget`
- E para Mac, basta instalar o Xcode ou usar o homebrew: `brew install git`

E para criar uma conta no GitHub basta ()

## Clonando um repositório

Para trabalharmos em um projeto, o primeiro passo é baixar o código dele. Para isto, usamos o comando *clone*:
- `git clone repositorio`

> Repositório é onde guardamos o código de um projeto, e geralmente é um link

Por exemplo, para clonar este projeto, vamos clonar o repositório PET-SI-UFU/PrimeiroPR:
- `git clone https://github.com/PET-SI-UFU/PrimeiroPR.git`

## Criando um novo branch!

Geralmente, você não vai alterar um projeto direto em sua versão principal. Ao invés disso, você criará uma nova versão (ou *branch*) do projeto para realizar suas alterações. A versão principal de um projeto geralmente é chamada de *main* ou *master*

> Você pode dar o nome que quiser aos branches, como por exemplo ter uma versão principal *main*, um branch de desenvolvimento *dev*, uma versão *beta*, etc. Essas versões podem ser usadas por diversos motivos, dos quais posso destacar boa organização e prevenir que acidentes (erros possivelmente críticos) cheguem na versão final de um programa.
>
> *branch*, do inglês ramo ou galho, é como se fosse um galho de árvore, que pode crescer e gerar novos galhos

Para mudarmos de branch, usaremos o comando *checkout*, e para criar um novo branch usaremos a opção *-b*:

- `git checkout -b nome-do-novo-branch`

Por exemplo, para você criar a sua versão deste projeto para realizar suas alterações, você pode utilizar:

- `git checkout -b corrigindo-portugues-errado`

Mas cuidado! Não é possível criar dois branches com o mesmo nome, então neste projeto em específico que pode por exemplo ter vários erros de português, coloque seu nome (ou usuário) no nome do branch, para garantir que todos consigam participar sem erros desnecessários.

Dito isto, é importante dizer que temos dois tipos de branch:
- Um branch *local* significa que ele está armazenado na sua máquina e ainda não subiu para o servidor/repositório do projeto,
- Já um branch *remoto* significa que ele está armazenado em outra máquina, geralmente um servidor como o GitHub, sendo o repositório oficial do projeto.

> Caso você queira deletar um branch local, usa-se o comando `git branch -D nome-do-branch`

## Faça suas alterações!

a

## Enviando sua nova versão para o servidor

a

## Seu primeiro Pull Request!



## Resumo

- `git clone repoitorio`
- `git checkout -b nome-do-novo-branch`
- fazer alterações
- `git status`
- `git add .`
- `git commit -m "resumo das alteracoes"`
- `git push origin nome-do-novo-branch`
- ir no github e fazer o pull request
- Prontinho!
