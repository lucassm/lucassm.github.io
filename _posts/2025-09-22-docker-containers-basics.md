---
title: 'O básico de containers Docker'
date: 2025-09-23
permalink: /posts/2025/09/docker-containers-basic/
tags:
  - docker
  - linux
  - devops
---

Nesse post a ideia é apresentar conceitos básicos de containers `docker`, não do ponto de vista teórico, mas do ponto de vista prático para aplicações no desenvolvimento de software realizado pelos times de pesquisa do nosso laboratório.

Em poucas palavras, containers são uma tecnologia fantástica! É como se você conseguisse executar várias maquinas virtuais ao mesmo tempo no seu sistema operacional, mas sem a sobrecarga que isso poderia gerar. Isso só é possível por conta da forma como os containers são executados, utilizando boa parte do kernel que já está em execução pelo sistema operacional hospedeiro. Dessa forma, além de ser uma tecnologia fantástica para reprodutibilidade de ambiente de desenvolvimento, os containers docker são uma ferramenta poderosa para desenvolvimento e gerenciamento de aplicações distribuídas.

Nesse artigo irei assumir que o docker já está instalado na sua máquina e que o comando `sudo` antes do comando `docker` já não é necessário, pois um configuração extra já foi realizada. Isso pode ser feito seguindo as instruções presentes na [documentação]() do próprio docker.

Recomendo fortemente a utilização de um ambiente de desenvolvimento de software baseado no sistema operacional Linux. Especificamente, iremos utilizar um ambiente desenvolvimento baseado no `Ubuntu 24.04`, que é a útima versão LTS, longo tempo de suporte, do sistema, o que nos ofere um pouco mais de estabilidade e confiabilidade.

A utilização do Linux em um computador convencional pode ser realizada de duas formas principais, são elas:

- Dual Boot, executando o SO diretamente no hardware da máquina.
- Virtualizado com WSL, rodando via máquina virtual otimizada para Windows.

A escolha de uma das opções indicadas acima vai depender das preferências particulares de cada um. Eu, por exemplo, já uso Linux como SO principal da minha máquina há mais de 10 anos, estão fico com a primeira opção.

A documentação para instalação do ecossistema de desenvolvimento de execução de containers Docker de no Linux pode ser acessada por esse [link]().

## Começando a utilizar

o comando `docker run` geralmente é utilizado em tutoriais para iniciantes, pois ele na verdade agrega vários comandos docker em um único comando. Então é comum você encontrar esse tipo de comando para inciar um container com o sistema operacional ubuntu 24.04, por exemplo:

```sh
docker container run -it ubuntu:24.04 bash 
```

É um comando bem útil pois permite inciar com um container já sendo executado com apenas um comando, mas ele esconde um pouco como as coisas funcionam. E como o objetivo aqui é ser didático, vamos fazer as coisas uma de cada vez:

O primeiro passo é fazer o pull de uma imagem de container. Geralmente isso é possível de ser feito por meio de uma consulta fácil no principal repositório de imagens docker da internet, que é mantido pela própria Docker Inc. Chama-se [dockerhub](https://hub.docker.com/).

Assim, por exemplo, para obtermos uma imagem do ubuntu 24.04 LTS via dockerhub, basta digitar no terminal:

```sh
docker image pull ubuntu:24.04
```

Para visualizar se o download da imagem foi realizado com sucesso, basta então digitar:

```sh
docker image ls --all
```

Uma saída semelhante a essa será exibida na saída do terminal:

```txt
REPOSITORY                       TAG       IMAGE ID       CREATED         SIZE
ubuntu                           24.04     a04dc4851cbc   7 months ago    78.1MB
scadalts/scadalts                latest    40c1d6ddcf50   14 months ago   587MB
mysql/mysql-server               8.0.32    1d9c2219ff69   2 years ago     496MB
```

Pronto, agora já temos nossa imagem de ubuntu para utilizar como base para nossos desenvolvimentos.

Agora queremos transformar essa imagem em um container. É um processo semelhante a instanciar um classe em um objeto. Para fazer isso o comando que iremos utilizar é o `docker create` é com ele que iremos criar o container, mas ainda não iremos executá-lo. Para criar o container o comando a ser inserido no terminal é:

```sh
docker container create --name opentes-c1 -it ubuntu:24.04 /bin/bash
```

Esse comando cria o container que queremos a partir de uma imagem e associa um nome e um comando a ser executado sempre que o container for ativado, nesse caso o comando é a chamada de um terminal de comandos, `/bin/bash`.

Criado o container, agora podemos visualizá-lo dessa forma:

```sh
docker container ls --all
```

A saída produzida será algo parecido com:

```txt
CONTAINER ID   IMAGE         COMMAND      CREATED      STATUS      NAMES
c243ff4c7708   ubuntu:24.04  "/bin/bash"  5 hours ago  Exited (0)  goofy_shockley
bea59eaae5e0   ubuntu:24.04  "/bin/bash"  7 hours ago  Exited (0)  opentes1
f21cc17a52d3   ubuntu:24.04  "/bin/bash"  6 months ago Exited (0)  sleepy_mahavira
```

Com o container sendo criado, é possível agora inciá-lo. Para isto precisamos utilizar o comando `docker start` da seguinte forma:

```sh
docker container start -ai opentes-c1
```

Pronto, temos um container de ubuntu 24.04 funcionando e pronto para receber comandos. Vá em frentem, teste algum deles: `ls`, `cd /home`, `apt update`, etc.

Existem agora duas formas de se conectar a esse container que já está em execução para executar qualquer tipo de comando. A primeira forma é utilizando o comando `docker attach` e a segunda é executando o comando `docker exec`.

Para se *pendurar* em um container, basta digitar o seguinte comando no terminal:

```sh
docker container attach opentes-c1
```

Agora, para executar um comando qualquer no container, o comando a ser digitado é esse:

```sh
docker container exec -it opentes-c1 /bin/bash
```

No caso de execução de comando estamos executando o comando de um terminal, com a opção de uma execução persistente, por isso o resultado dos dois comandos, `attach` e `exec` são os mesmos.

Esses são os procedimentos mais básicos para iniciar um aprendizado de manipulação de containers docker. O próximo passo é a criação de containers personalizados utilizando arquivos com uma sintaxe especial para descrição de containers, o `Dockerfile`.

## Docker Files

