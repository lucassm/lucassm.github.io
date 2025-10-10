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

Outra informação importante é que o que vai ser mencionado nesse artigo
pressupõe a existência de um ambiente Linux já configurado. Utilizaremos como
base uma distribuição baseada em Debian, o Ubuntu em sua versão 24.04, que é
última versão de longo tempo de suporte até o presente momento.

Após a instalação do sistema operacional, abra um terminal de comando e instale
o `git` no sistema operacional, ante porém é importante realizar a atualização
dos repositórios de software:

```sh
sudo apt update && sudo apt install git
```

Após instalado do `Git` é hora de abrir o navegador de internet e acessar a
página web do maior repositório de software da internet, o
[GitHub](https://githuub.com).

> [!NOTE] O GitHub para a grande maioria dos serviços e 100% gratuito!

Para ter acesso às funcionalidades do GitHub é preciso criar uma conta na
plataforma. Depois desse passo é possível criar um repositório vinculado à sua
conta, um nome para o repositório será solicitado, assim como se o repositório
deverá conter um arquivo de licença, um `.gitignore` e um arquivo README.md.
Depois de configurados esses passos o repositório será criado e então será
possível realizar um passo importante em nosso fluxo de trabalho que é clonar o
repositório remoto para um destino local, no caso, nossa estação de trabalho.
Isso pode ser feito por meio do seguinte comando no terminal de comandos do
Linux:

```sh
git clone https://github.com/meu-nome-de-usuario/nome-do-meu-repositorio
```

Isso irá realizar o download automático do repositório GitHub para uma pasta na
estação de trabalho local, na mesma localização em que o terminal de comandos
está referenciando.

Ao entrar nessa pasta (seguindo a mesma referência do comando descrito acima, o
comando para isso seria `cd nome-do-meu-repositorio`) será possível observar que
além dos arquivos de README.md e de licença, haverá também uma pasta oculta,
denominada de `.git`. É nesse arquivo que todas as informações do git estarão
sendo armazenadas.
