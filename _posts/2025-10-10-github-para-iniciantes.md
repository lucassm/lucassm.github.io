---
title: Introdução ao uso de Git e GitHub
date: 2025-10-10
permalink: /posts/25-10/introducao-git-github
tags:
  - git
  - github
  - linux
---

Este artigo tem como objetivo fornecer uma visão geral e básica da utilização de
duas tecnologias integradas entre si e que têm como propósito facilitar o
controle e a colaboração no desenvolvimento de projetos de software. Estamos
falando das tecnologias `Git` e `GitHub`.

Aqui serão abordados aspectos gerais de utilização das duas ferramentas. Para
uma visão mais aprofundada é recomendado que se busque a documentação oficial do
Git, disponível na [web](https://git-scm.com/).

Quanto ao GitHub apesar de ser um recurso mais simples e visual permitindo um
fluxo de utilização simplificado, também pode ser utilizado com _recursos
avançados_, principalmente com recursos que permitem a elaboração de _fluxos
automatizados_, como no caso da funcionalidade `GitHub Actions`, mas que não
iremos abordar aqui. A documentação completa do GitHub pode ser encontrada na
web.

Outra informação importante é que o que vai ser mencionado nesse artigo
pressupõe a existência de um ambiente _Linux já configurado_. Utilizaremos como
referência uma distribuição baseada em Debian, o Ubuntu em sua versão 24.04, que
é última versão de longo tempo de suporte até o presente momento.

Após a instalação do sistema operacional, abra um terminal de comando e instale
o `Git` no sistema operacional, antes porém é importante realizar a atualização
dos repositórios de software. Os comandos para realizar essas ações são:

```sh
sudo apt update && sudo apt install git
```

É importante ressaltar que o comando `sudo` serve para dar permissão de
administrador ao gerenciador de pacotes `apt`, responsável por instalar os
aplicativos do sistema.

Após instalado do `Git` é hora de abrir o navegador de internet e acessar a
página web do maior repositório de software da internet, o
[GitHub](https://githuub.com).

> O GitHub para a grande maioria dos serviços e 100% gratuito!

Para ter acesso às funcionalidades do GitHub é preciso criar uma conta na
plataforma. Depois desse passo é possível criar um repositório vinculado à sua
conta, um nome para o repositório será solicitado, assim como se o repositório
deverá conter um arquivo de licença, um `.gitignore` e um arquivo `README.md`.
Depois de configurados esses passos o repositório será criado e então será
possível realizar um passo importante em nosso fluxo de trabalho que é _clonar o
repositório remoto para um destino local_, no caso, nossa estação de trabalho.
Isso pode ser feito por meio do seguinte comando no terminal de comandos do
Linux:

```sh
git clone https://github.com/meu-nome-de-usuario/nome-do-meu-repositorio
```

Esse comando realiza o download automático do repositório GitHub para uma pasta
na estação de trabalho local, na mesma localização em que o terminal de comandos
está referenciando.

Ao entrar nessa pasta (o comando para isso seria `cd nome-do-meu-repositorio`)
será possível observar que além dos arquivos de README.md e de licença, haverá
também uma pasta oculta, denominada de `.git`. É nesse arquivo que todas as
informações do git estarão sendo armazenadas.

A partir desse ponto é importante mencionar que o que você tem agora é uma cópia
local do seu repositório criado no GitHub. Quaisquer alterações que forem
realizadas nos arquivos desse repositório local serão registradas. E aqui temos
um dos conceitos mais importantes quando se quer entender Git, que é como
registrar as alterações realizadas em um repositório.

Dentro de um repositório que está sendo _monitorado_ pelo `Git` um arquivo pode
ter um dos seguintes estados:

- não estar sendo monitorado.
- estar sendo monitorado, mas sem nenhum alteração em relação ao último registro
  realizado.
- estar sendo monitorado, e com alterações registradas em relação ao último
  registro realizado, mas não incluído para o próximo registro.
- estar sendo monitorado, com alterações registradas em relação ao último
  registro realizado e estar incluído para o próximo registro.

Essas possibilidades podem ser visualizada por meio do comando `git status`, que
dá uma boa visão de como estão os arquivos de todo o repositório local do Git.

Ou seja, um conceito central do Git é como reunir um conjunto de alterações que
tenha um objetivo único e assim registrar essas alterações juntamente com uma
mensagem que seja útil caso seja necessário rastrear essa alteração no futuro,
que pode não ser tão distante assim. A esse procedimento dá-se o nome de
`commit`.

Para ilustrar os conceitos mencionados vamos supor que exista um repositório com
dois arquivos chamados `main.py` e `foo.py`. Com o comando `git init` esse passa
a ser um repositório monitorado pelo `Git`. Inicialmente os dois arquivos estão
no modo não monitorado. Vamos supor que gostaríamos de monitorar inicialmente
somente o arquivo `main.py`, para adicioná-lo à base de arquivos do repositório
`Git` basta realizar o seguinte comando no terminal:

```sh
git add main.py
```

A partir desse momento o arquivo `main.py` está sendo monitorado pelo `Git`. Mas
para que esse registro passe a ser permanente é preciso um segundo passo, que é
registrar o arquivo em um `commit`, que registra tanto novos arquivos no
repositório quanto alterações realizadas em arquivos já monitorados. Para isso
precisamos inserir no terminal o comando:

```sh
git commit -a -m 'first commit, add main.py'
```

Com essa ação as alterações realizadas em todos os arquivos inseridos no commit
por meio do comando `git add` são registradas em bloco e identificadas no commit
por meio de uma mensagem que deve dar uma noção do conjunto de alterações
realizadas. É bom lembrar que uma boa prática de desenvolvimento é realizar
commits com frequência e sempre registrar mensagens que sejam curtas mas que
sintetizem ao máximo o objetivos das alterações ou inclusões de arquivos
realizadas.

Agora, o próximo passo é sincronizar as alterações realizadas por meio do commit
ao repositório remoto que foi clonado do GitHub, ou que foi associado à ele.
Para entender esse procedimento é importante entender o conceito de repositórios
remotos. Para verificar se o repositório em que você está tem algum repositório
remoto associado, basta digitar o comando `git remote --verbose`. A saída gerada
por esse comando deverá ser algo parecido com:

```txt
origin> git@github.com:grei-ufc/workshop-2025-opentes.git (fetch)
origin> git@github.com:grei-ufc/workshop-2025-opentes.git (push)
```

Esse comando mostra que existe um repositório remoto associado ao repositório
local. Dessa forma é possível se comunicar com esse repositório remoto tanto no
sentido remoto -> local quanto no sentido inverso, ou seja, local -> remoto.

Primeiro vamos verificar o sentido remoto -> local, que deve ser feito sempre
que quisermos enviar alterações para o repositório remoto, para não corrermos o
risco de enviar alterações com base em uma cópia antiga do repositório remoto,
mas não se preocupe, o Git foi feito para gerenciar justamente esse tipo de
situação. Enfim, a atualização da cópia local do repositório remoto no Git pode
ser realizada pelo comando `git fetch`. A saída desse comando, caso haja alguma
atualização deverá ser algo parecido com:

```txt
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 3 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (3/3), 578 bytes | 289.00 KiB/s, done.
From github.com:grei-ufc/workshop-2025-opentes
   a83d712..cb50d6e  main       -> origin/main
```

Em seguida é necessário sincronizar os repositórios local e remoto, isso pode
ser feito com o comando `git merge origin/main main`. Nesse ponto é importante
mencionar que o nome `main` refere-se ao `branch` principal do nosso
repositório. O conceito de `branch` será explicado logo em seguida.

Um atalho para realizar as operações de `git fetch` e `git merge`, que são
bastante comuns de serem realizadas em sequência, basta utilizar o comando
`git pull`, que nada mais é que um atalho para as duas operações.

Se não houver nenhum conflito entre os repositórios local e remoto, então o
merge é realizado e agora o `branch` local main, estará além de sincronizado com
o branch main remoto, também incorporando as alterações realizadas nos últimos
commits locais. É hora então de enviar essas alterações para o repositório
remoto, isso pode ser feito por meio do comando `git push origin main`
