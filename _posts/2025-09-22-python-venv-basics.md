---
title: Gerenciamento de dependências e projetos em Python
date: 29-09-25
permalink: posts/2025/09/python-tools--venv-pyenv-e-uv
---

Este post tem como objetivo deixar registrado alguns conceitos básicos sobre gerenciamento de ambientes Python. Eu particularmente costumava utilizar o [anaconda](https://www.anaconda.com/download/success) como minha distribuição Python e o gerenciador de ambiente [conda](https://docs.conda.io/en/latest/) como meu gerenciador de pacotes e de ambientes virtuais Python. Sempre tive bons resultados com o *anaconda*, e foi assim durante algo em torno de cinco ou seis anos.

No entanto, pesquisando recentemente (2025), descobri que o ecossistema Python de ferramentas para gerenciar pacotes e versões da linguagem em si, evoluiu bastante, e resolvi testar *outras alternativas para gerenciar os ambientes virtuais do Python*.

Na verdade, a maior motivação para escrever esse artigo foi observar que a maioria dos alunos que trabalha com Python na engenharia elétrica sabem muito pouco sobre esse importante tópico para quem utiliza Python em seus desenvolvimentos. Também queria testar algo fora do ecossistema científico e mais voltado para projetos de propósito geral, já que muitas vezes essas ferramentas são as únicas disponíveis, ou talvez as mais eficientes para determinadas situações.

Além disso, há algum tempo escutei um colega falando algo do tipo:

> Python é muito bom, mas um grande defeito da linguagem é que se você tentar executar seu código alguns meses depois da última execução, ele provavelmente não funcionará mais. Isso não acontece com os códigos que desenvolvi em Matlab. Tenho códigos em Matlab desenvolvidos há 10 anos atrás que executam ainda hoje!

Talvez esse comentário seja mais comum do que possa parecer no meio acadêmico, principalmente nas áreas de engenharia que não têm a computação como objeto de estudo em si, mas tão somente como uma ferramenta de trabalho essencial. A verdade é que muitos de nós, já passamos pela situação de *não conseguir fazer um código Python rodar após apenas alguns meses terem se passado desde a última execução*, e isso é uma imensa dor de cabeça.

Essa questão tem dois motivos bem claros. O primeiro motivo é que a maioria dos estudantes de engenharia elétrica utilizou o `Matlab` como ferramenta base durante muito tempo, e nunca teve que de fato se preocupar com questões de compatibilidade relacionadas à versão da linguagem e das libs utilizadas no desenvolvimento. Tudo simplesmente funcionava.

Mas a verdade é que a vida real é mais complicada do que isso, principalmente quando estamos falando de uma linguagem tão dinâmica quanto tem se tornado Python. Python tem evoluído em um ritmo muito acelerado e incorporado funcionalidades inovadoras a cada novo lançamento de versão.

As bibliotecas do ecossistema Python também estão sempre evoluindo e muitas vezes sem os cuidados necessários para manter a compatibilidade de uma versão para outra. Isso pode gerar uma confusão enorme.

É preciso gerenciar o ambiente em que a sua aplicação Python é desenvolvida. É preciso, de algum forma, *congelar* esse ambiente exatamente do jeito que está na fase de desenvolvimento. Na hora de compartilhar o projeto, ou levar para um ambiente de produção, é preciso poder replicar o ambiente de execução utilizado na fase de desenvolvimento para que o projeto possa ser executar como deve.

Felizmente, esse é um problema recorrente no desenvolvimento de projetos em Python, por isso, desde o início foram desenvolvidas ferramentas que auxiliaram os desenvolvedores a contornar esse tipo de situação.

### As ferramentas mais básicas

A ferramenta padrão do Python para a criação de ambientes virtuais em Python é o [venv](https://docs.python.org/pt-br/3.13/library/venv.html). Seu uso é bem simples e como ele faz parte da biblioteca de aplicações padrão do Python, para utilizá-lo e criar seus próprios ambientes virtuais, basta ter alguma versão do python instalado e então invocá-lo pelo próprio comando python. Para o `ubuntu 24.04`, por exemplo, os seguintes comandos devem funcionar para criar um ambiente virtual chamado `.venv`. Veja:

Caso ainda não haja nenhuma versão do Python instalada no computador, digite o seguinte comando no terminal:

```sh
sudo apt install python3
```

Em seguida crie um diretório, entre nesse diretório e crie o ambiente virtual, que estará na pasta `.venv`:

```sh
mkdir project-python
cd project-python
python3 -m venv .venv
```

Agora que o ambiente virtual foi criado dentro da pasta do projeto, é possível ativá-lo da seguinte forma:

```sh
source .venv/bin/activate
```

Pronto, seu ambiente Python está pronto para ser utilizado, e no inicio da linha atual do seu terminal o nome do ambiente virtual aparecerá:

```sh
(.venv)$ 
```

Caso você esteja executando um projeto já existente, a abordagem tradicional de projetos python era a criação de um arquivo do tipo `requirements.txt` contendo todas as dependências do projeto, juntamente com as versões utilizadas para cada biblioteca. Para *povoar* o ambiente virtual recém criado com todas as dependências necessárias para o projeto bastava digitar o comando no terminal:

```sh
python -m pip install -r requirements.txt
```

Vejam o ponto em que chegamos. Aqui já existem argumentos para responder o questionamento colocado no início desse artigo:

> Por que seus códigos Python não funcionam após alguns meses de terem sido escritos?
>
> *Resposta*: Por que **você** não fez as coisas como deveria. Em Python, a responsabilidade por gerenciar as dependências de seu projeto é **sua** e não da linguagem.

A verdade é que da forma como o ecossistema de libs Python evolui hoje, não há mais como manter scripts isolados. Todo código Python deve estar associado a um projeto, que por sua vez deve conter um arquivo de configuração para poder montar um ambiente virtual com todas as dependências necessárias instaladas em suas versões corretas, inclusive a versão do próprio interpretador Python.

A resposta pode parecer arrogante, mas não há como fugir disso, não só em Python mas também em outras linguagens de programação, como Rust, Ruby, Julia, Javascript, etc. O MatLab foi quem nos acostumou mal a não prestar atenção em quais versões de bibliotecas estamos utilizando, pois como é um produto comercial, com um gerenciamento extremamente concentrado em sua equipe de desenvolvimento e muito voltado para engenheiros e não desenvolvedores de software, deixa essa tarefa transparente para o usuário.

Isso pode ser visto como uma vantagem para alguns, mas na minha opinião, se estamos desejando um ambiente inovador, que acompanha rápido as transformações e mudanças que todos os dias surgem no meio das comunidades de desenvolvimento open-source, temos que aprender a lhe dar, de forma organizada, claro, com essa selva de versões.

### Um passo em direção ao futuro do gerenciamento de projetos Python

O que foi mostrado até o momento é o jeito clássico de fazer as coisas. Mas muita coisa vem mudando no  ambiente Python e hoje o padrão de armazenar dependências de pacotes no `requirements.txt` já não é uma boa prática. O novo padrão para armazenar as informações do projeto é o descrito no [PEP 621](https://peps.python.org/pep-0621/) que estabelece a utilização de arquivos do tipo `pyproject.toml` para armazenar essas informações de projeto.

Um tutorial para utilização dos arquivo `pyproject.toml` pode ser encontrado nesse [link](https://packaging.python.org/en/latest/guides/writing-pyproject-toml/#writing-pyproject-toml). Não irei me preocupar com isso aqui pois iremos gerar esse arquivo de forma automatizada utilizando uma ferramenta de gerenciamento de projetos Python.

Com o avanço do desenvolvimento de versões Python cada vez mais rápido, gerenciar e especificar qual a versão do Python utilizada no seu projeto tem se tornado cada vez mais importante. O Python Packaging Authority (PyPA) tem se esforçado para oferecer uma grande quantidade de ferramentas que permitam aos usuários da linguagem de programação utilizar ferramentas que facilitem o gerenciamento de pacotes, a reprodutibilidade e distribuição de projetos escritos em Python. Uma lista dessas ferramentas pode ser encontrada nessa [página da PyPA](https://packaging.python.org/en/latest/key_projects/#pypa-projects).

### O futuro do gerenciamento de projetos Python

Recentemente uma ferramenta tem se destacado como um agregador das funcionalidades disponibilizadas pela maioria dessas ferramentas. Além de ser um facilitador por agregar as funcionalidades de diversas ferramentas para gerenciamento de projetos e pacotes Python, essa ferramenta promete ser mais rápida, por ser escrita em `Rust`, do que as já disponíveis, como o conhecido `Poetry`.

O nome dessa ferramenta é [uv](https://docs.astral.sh/uv) e ela que irei utilizar como base do workflow dos nossos projetos. É claro que a documentação oficial do projeto já oferece boas opções de exemplos, mas vamos listar aqui alguns dos procedimentos mais importantes nessa tarefa de gerenciamento de projetos Python.

A primeira coisa a ser feita é definir qual versão Python a ser utilizada no projeto. Com o `uv` é muito simples tanto instalar novas versões Python no seu ambiente quanto setá-las para um determinado projeto. Por exemplo, suponha que desejamos utilizar Python 3.12.11 para um determinado projeto e ainda não tenhamos essa versão instalada no ambiente de desenvolvimento. Com `uv` é possível instalar a versão desejada de Python dessa forma:

```sh
uv python install 3.12.11
```

Agora utilizamos um outro comando para criar a pasta do projeto, chamada aqui de `opentes-p1`:

```sh
uv init opentes-p1
```

Por meio do comando `uv init` um diretório com o nome do projeto passado como parâmetro do comando é criado. Entre no diretório por meio do comando `cd opentes-p1`. Dentro desse diretório existe uma estrutura muito básica, composta de apenas três arquivos:

- main.py
- pyproject.toml
- README.md

A partir de agora é possível já ir adicionando dependências ao projeto por meio do comando `uv add`, por exemplo para adicionar o pacote numpy em sua versão mais atual no momento da escrita desse artigo, basta digitar:

```sh
uv add numpy==2.3.3
```

> [!note] Importante!
> Para que o pacote requerido seja instalado no ambiente desejado é necessário que o comando seja executado dentro do diretório de projeto, nesse caso `opentes-p1`

Se você nesse momento abrir seu arquivo `pyproject.toml` que gerencia as configurações do seu ambiente, então essa dependência de projeto já estará listada lá:

```toml
[project]
name = "opentes-p1"
version = "0.1.0"
description = "Add your description here"
readme = "README.md"
requires-python = ">=3.12"
dependencies = [
    "numpy==2.3.3",
]
```
