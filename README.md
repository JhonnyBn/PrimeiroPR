# Primeiro PR
Repositório destinado a ensinar o básico de Git/GitHub aos integrantes do PET-SI

## Introdução

Nosso objetivo é criar um PR (Pull Request) contendo uma alteração/atualização para este projeto. Para isto, precisaremos aprender alguns termos e alguns comandos.

Primeiramente, vamos instalar o Git e criar/entrar em uma conta do GitHub.

> Atenção! Git e GitHub não são a mesma coisa!
> - *GitHub* é um site de hospedagem de códigos. Ele ajuda desenvolvedores a compartilhar seus códigos facilmente através do *Git*;
> - O *Git* por sua vez é um programa de versionamento de código. Ele ajuda a gerenciar várias versões de um projeto, cada uma contendo alterações em diversos arquivos, realizadas por quaisquer número de usuários. Git não é usado somente no GitHub, mas também no GitLab, BitBucket e diversas outras plataformas. É um programa essencial para qualquer desenvolvedor, e muito simples de se usar.

Para instalar o Git é bem tranquilo:
- Nas distribuições Linux, simplesmente digite `sudo apt-get install git` ou comando equivalente da sua distro
- Para Windows, use o instalador disponível no [site do Git](https://git-scm.com/download/win) ou, caso tenha o winget: `winget install --id Git.Git -e --source winget`
- E para Mac, basta instalar o Xcode ou usar o homebrew: `brew install git`

Caso você ainda não tenha uma conta no GitHub, basta entrar no [site do GitHub](github.com), clicar em Sign Up e seguir os passos.

## Criando um Fork do repositório

Este passo não é necessário caso você tenha permissões de contribuidor no projeto, mas ao trabalhar em projetos de código aberto geralmente não teremos, então criaremos um Fork.

> Um Fork, em poucas palavras, é outra versão do projeto, mantida por outro usuário. No nosso caso, será uma versão temporária somente para sugerir melhorias no código.

Vá para a página do projeto no GitHub e clique em Fork, no canto superior direito da tela, como indicado no print:

![Criando um Fork no GitHub](https://user-images.githubusercontent.com/29382833/153613051-fa321c84-c536-4006-aeb0-afcfa24c76f7.png)

Agora temos nossa própria versão do repositório em nosso usuário.

## Clonando um repositório

Para trabalharmos em um projeto, o primeiro passo é baixar o código dele. Para isto, usamos o comando *clone*:
- `git clone repositorio`

> Repositório é onde guardamos o código de um projeto, e geralmente é um link

Por exemplo, para clonar este projeto, vamos clonar o repositório Usuário/PrimeiroPR:
- `git clone https://github.com/PET-SI-UFU/PrimeiroPR.git`
> Lembre-se que caso você tenha feito Fork, você deve clonar o repositório do seu usuário

A pasta do projeto foi baixada no diretório atual. Não se esqueça de entrar na pasta do projeto antes de ir para o próximo passo!
- `cd PrimeiroPR`

## Criando um novo branch!

Geralmente, você não vai alterar um projeto direto em sua versão principal. Ao invés disso, você criará uma nova versão (ou *branch*) do projeto para realizar suas alterações. 

> *branch*, do inglês ramo ou galho, é como se fosse um galho de árvore, que pode crescer e gerar novos galhos

Essas versões podem ser criadas/usadas por diversos motivos, dos quais posso destacar boa organização de projeto e prevenir que acidentes (erros possivelmente críticos) cheguem na versão final de um programa.

Para mudarmos de branch, usaremos o comando *checkout*, e para criar um novo branch usaremos a opção *-b*:

- `git checkout -b nome-do-novo-branch`

> Você pode dar o nome que quiser aos branches, como por exemplo ter uma versão principal *main*, um branch de desenvolvimento *dev*, uma versão *beta*, etc.
>
> A versão principal de um projeto geralmente é chamada de *main* ou *master*

Ao contribuir em projetos de código aberto, é padrão criar um novo branch e fazer um PR para o branch de desenvolvimento

> Ao fazer isso, evite colocar nomes genéricos como "alteracao" ou "fix", tente descrever suas alteracoes em poucas palavras no nome do branch

Por exemplo, para você criar a sua versão deste projeto e realizar suas alterações, você pode utilizar:

- `git checkout -b corrigindo-portugues-errado`

Mas cuidado! Não é possível criar dois branches com o mesmo nome, então neste projeto em específico que pode por exemplo ter vários erros de português, coloque seu nome (ou usuário) no nome do branch, para garantir que todos consigam participar sem erros desnecessários.

> Caso você queira deletar um branch local, usa-se o comando `git branch -D nome-do-branch`

Dito isto, é importante dizer que temos dois tipos de branch:
- Um branch *local* significa que ele está armazenado na sua máquina e ainda não subiu para o servidor/repositório do projeto,
- Já um branch *remoto* significa que ele está armazenado em outra máquina, geralmente um servidor como o GitHub, sendo o repositório oficial do projeto.

## Faça suas alterações!

Agora que você já tem sua própria versão do projeto em sua máquina, mãos à obra!

Altere algum arquivo do projeto, como por exemplo adicione seu nome na [Lista de Presença/Contribuidores](Contribuidores.md)!

Podemos ver quais arquivos foram alterados localmente ao usar o comando *status*:
- `git status`

Para dizer ao Git que queremos enviar nossas alterações, primeiramente vamos adicionar os arquivos para o próximo *commit* usando o comando *add*.
- `git add nome-do-arquivo`
- Ou simplesmente `git add .` para adicionar todas as modificações

> Um commit é, em palavras simples, uma versão específica do projeto, ou uma referência para o projeto em um determinado momento

Feito isto, vamos realizar o commit em si, utilizando o comando *commit* com a opção *-m "descrição da atualização"*
- `git commit -m "adicionando meu nome na lista de presença"`

> É importante escrevermos uma breve descrição das alterações no commit, usando a opção -m, para facilitar entender e encontrar as modificações no projeto ao longo do histórico de versões do mesmo

## Enviando sua nova versão para o servidor

Depois que você fizer suas alterações e seus commits, utilizaremos o famoso comando *push* para enviar a atualização para o servidor remoto

Como é a primeira vez que faremos push neste projeto, precisamos configurar o push, então usaremos o seguinte comando:
- `git push --set-upstream origin nome-do-novo-branch`
> A opção '--set-upstream' indica que vamos salvar para qual servidor vamos enviar as atualizacoes nos proximos pushes
>
> A opção 'origin' indica que vamos enviar a atualização para o servidor de origem do projeto, aquele que fizemos git clone lá no início
> 
> E a opção 'nome-do-novo-branch'? Pois é, lembra que criamos o novo branch localmente, e ainda não falamos pro servidor que tem um novo branch? Essa opção indica para o servidor criar um novo branch remoto com as nossas alterações do branch local 'nome-do-novo-branch'

Após realizar esta configuração inicial e criar o branch remoto, podemos usar apenas `git push` para enviar as próximas atualizações para o servidor/repositório.

## Seu primeiro Pull Request!

Agora que fizemos todas as atualizações que queríamos, basta solicitar um novo Pull Request!

> Um PR (Pull Request) é um método de enviar contribuições para projetos de código aberto. Ele envia uma solicitação de alteração para os mantenedores do projeto analisarem caso a caso.

Para isso, vamos na página do projeto, abrimos a aba de *Pull requests* e clicamos em *New pull request*, como indicado no print:

![Novo PR no GitHub](https://user-images.githubusercontent.com/29382833/153617060-33751fda-f18d-4340-be98-22085ae078f9.png)

Caso você tenha feito um Fork do projeto, clique na opção de comparar entre Forks:

![Comparando forks no PR](https://user-images.githubusercontent.com/29382833/153617590-d384e0c6-73ab-4cf1-9204-eefce5bcb20c.png)

Agora selecione para qual branch você quer enviar as atualizações, na esquerda, e de qual branch você quer obter as atualizações, na direita, e clique em *Create pull request*, como indicado no print:

> Lembre-se que geralmente você quer enviar suas atualizações para o branch dev, beta, ou o branch indicado no README do projeto, vindo do seu fork, do seu novo branch.
>
> Você pode aproveitar e rever as mudanças realizadas antes ir para o próximo passo

![Selecionando os branches do PR](https://user-images.githubusercontent.com/29382833/153618257-67e032fa-e28a-4952-a0d2-46a9046e36f5.png)

Agora basta dar um nome pro PR e detalhar as mudanças na descrição e clicar em *Create pull request*!

![Detalhando o PR](https://user-images.githubusercontent.com/29382833/153619004-b8ae72d6-2806-4cad-b36f-be30c819a4f1.png)

Pronto, pode comemorar à vontade, você fez seu primeiro PR!

Agora cabe ao mantenedor do projeto verificar as mudanças e fazer merge se achar conveniente.

## Aceitando o PR (na visão de mantenedor do projeto)

Após verificar as mudanças, se o mantenedor do projeto gostar das atualizações e não pedir nenhum commit adicional, ele vai no GitHub, na página do PR criado, e realiza um commit de *merge*, como indicado nos prints abaixo:

> Merge é a ferramenta do Git para enviar as alterações de um branch para outro

![Aceitando o PR](https://user-images.githubusercontent.com/29382833/153620653-e1ffa5ce-f000-4029-ba33-74ce99bf357e.png)

![Confirmando o PR](https://user-images.githubusercontent.com/29382833/153621272-c33b4549-a980-4d62-bc16-2119a4597904.png)

# Resumo

- Se não for contribuidor do projeto, fazer fork dele
- `git clone repoitorio`
- `git checkout -b nome-do-novo-branch`
- fazer alterações
- `git status`
- `git add .`
- `git commit -m "resumo das alteracoes"`
- `git push origin nome-do-novo-branch`
- ir no github e fazer o pull request
- Prontinho!
