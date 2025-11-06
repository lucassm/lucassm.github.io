---
title: Aulas de Prot. Cont. e Otim. em SmartGrids
date: 25-10-08
permalink: /posts/2025/10/pco-classes-2025
tags:
  - opendss
  - pós-graduação
  - python
  - simulação da rede elétrica
---

Este arquivo tem como objetivo servir de roteiro de acompanhamento das
discussões que vem sendo realizadas nas aulas da disciplina de pós-graduação
_Proteção, Controle e Otimização de sistemas elétricos e Redes Elétricas
Inteligentes (PCOSmartGrid)_.

Segue uma descrição ordenada temporalmente com os assuntos abordados em cada um
dos encontros, bem como os links para acesso aos materiais utilizados nas aulas:

## Aula 1 - 17-09-2025

Essa foi a primeira aula da disciplina. O primeiro procedimento realizado foi a
apresentação do conteúdo da disciplina. Como essa é uma disciplina
compartilhada, com o professor Raimundo Furtado, e os conteúdos a serem
abordados por cada professor são independentes, só a parte do conteúdo do
professor Lucas foi apresentada.

Essa parte da disciplina será dividida em três partes bem definidas, são elas:

- Modelagem da rede elétrica de distribuição utilizando OpenDSS.
- Tópicos básicos de técnicas de otimização.
- Aplicação de técnicas de otimização no contexto de redes elétricos
  inteligentes.

Um detalhamento mais abrangente dos temas a serem abordados na disciplina podem
ser encontrados [aqui](https://www.lucassm.pro/teaching/PCOSmartGrid).

Depois da apresentação do programa da disciplina, nessa mesma aula, foi dado
inicio à exposição do conhecido sistema de testes IEEE 13 barras. Esse sistema
possui alguns dos principais elementos que são particulares e característicos da
modelagem de sistemas de distribuição, como por exemplo:

- Linhas trifásicas, bifásicas e monofásicas em configuração aérea e
  subterrânea.
- Diferentes tipos de estruturas de linhas de distribuição.
- Cargas monofásicas e trifásicas conectadas em delta e estrela.
- transformadores com diferentes tipos de conexões.
- reguladores de tensão.
- bancos de capacitores.
- sequência de fase intercambiada.

Essas características permitem que os principais aspectos de modelagem de
sistemas de distribuição possam ser bem explorados.

O sistema IEEE 13 barras pode ser encontrado descrito em detalhes
[neste artigo](https://cmte.ieee.org/pes-testfeeders/resources/).

## Aula 2 - 24-09-2025

Nessa aula foi dado continuidade na descrição dos principais elementos do
sistema de testes IEEE 13 barras. Após o sistema 13 barras ter sido apresentado,
também foi dado inicio à apresentação do software OpenDSS, com uma breve
introdução sobre sua utilização.

O OpenDSS é um software aberto, desenvolvido sob a liderança do Instituto
Americano EPRI, e está disponível para
[download](https://sourceforge.net/projects/electricdss/) gratuitamente.

Outro recurso importante para o aprendizado do OpenDSS é a sua
[documentação oficial](https://opendss.epri.com/).

## Aula 3 - 01-10-2025

Nessa aula o modelo matemático de **linhas de distribuição trifásicas** foi
apresentado. O material utilizado na exposição faz parte do material de aula do
professor Vassilis Kekatos e está disponível
[aqui](https://engineering.purdue.edu/~kekatos/pdsa/Lecture4.pdf).

Após apresentados os conceitos teóricos matemáticos sobre linhas de
distribuição, a forma como os elementos elétricos são conectados uns aos outros
no OpenDSS foi apresentada, e os elementos elétricos `transformador` e `linhas`
foram exemplificados. O material utilizado nessa exposição está disponível
[aqui](https://tinyurl.com/3ce5cze3).

## Aula 4 - 08-10-2025

Inicialmente o conceito de **redução de Kron** foi discutido, e pode ser
aprofundado no material sobre modelagem de linhas de distribuição do professor
Kekatos. Logo em seguida foi realizado o link com o software OpenDSS. Foi
mostrado que o OpenDSS pode ser executado de duas formas principais:

- Localmente via instalação e execução de interface gráfica.
- Remotamente via google colab.

O [google colab](https://colab.research.google.com/) é uma plataforma executada
no ambiente web que disponibiliza um ambiente para construção notebooks Python,
muito semelhantes aos já populares [Jupyter notebooks](https://jupyter.org/).

Utilizando os Jupyter notebooks ou o google colab é possível executar o OpenDSS
integrado a um ambiente controlado pela linguagem de programação Python, e com
isso é possível ampliar bastante as possibilidades de análises a serem
realizadas com OpenDSS.

Alguns dos recursos mais importantes utilizados nessa aula foram:

- slides sobre conceitos básicos de OpenDSS, disponíveis nos
  [link 1](https://tinyurl.com/6fxecn4x) e
  [link 2](https://tinyurl.com/4jfunh7z).
- slides sobre modos de simulação no OpenDSS, disponíveis
  [aqui](https://tinyurl.com/4rzmnbxc).
- documentação do google colab.
- documentação da biblioteca
  [opendssdirect.py](https://dss-extensions.org/OpenDSSDirect.py/).

## Aula 5 - 15-10-2025

Encontro realizado de forma remota para permitir o acesso de todos os alunos ao
ambiente de programação Python disponibilizado pelo google colab.

Os temas abordados nesse encontro:

- Modo de execução `snapshot`, fluxo de carga único.
- Modelagem de fontes de energia equilibradas e desequilibradas, `circuit`,
  `vsource`.
- Modelagem de linhas de distribuição com e sem condutor neutro explícito,
  `line`, `linecode`, `linegeometry`.
- Modelagem de transformadores de distribuição, com conexão trifásica,
  `transformer`.
- Modelagem de cargas elétricas, `load`.

## Aula 6 - 22-10-2025

Continuação da aula passada com execução de scripts OpenDSS utilizando
`google colab`.

Temas abordados nesse encontro:

- Modo de execução `faltstudy`.
- Modo de execução `daily`.
- Curvas de carga `loadshape`.
- Elemento `meter`.
- Elemento `monitor`.
- Estudo de geração distribuída com utilização do elemento `pvsystem`.

Slides sobre o elemento `pvsystem` estão disponíveis
[neste link](https://tinyurl.com/ypk2dnt9)

## Aula 07 - 29-10-2025

Aula remota com utilização do google colab.

- Revisão dos tópicos abordados nas aulas anteriores.
- Revisão detalhada sobre o elemento `pvsystem`
- Apresentação do elemento `storage` e das suas principais características.
- Explicação rápida sobre a utilização da API da biblioteca Python
  `opendssdirect.py`.

O material explicativo sobre o elemento `storage` está disponível
[neste link](https://tinyurl.com/mwn28a4p)

## Aula 08 - 05-11-2025

Não houve encontro em decorrência dos encontros universitários 2025.

Foi encaminhada uma atividade com prazo de entrega para 19-11-2025.

A descrição da atividade está disponível
[neste link](https://tinyurl.com/yc3vrpjr)

## Aula 09 - 12-11-2025 (**Prevista**)

Nesta aula espera-se abordar aspectos importantes a respeito da modelagem de
Recursos Energéticos Distribuídos (_Distributed Energetic Resources_) utilizando
o `OpenDSS` e os módulos `openDER` e `openDER interface` que são baseados nas
diretrizes estabelecidas pela norma IEEE 1547.

- Estudo de impacto de inserção de **Recursos Energéticos Distribuídos** com o
  módulo `OpenDER`.

Com esta aula espera-se complementar a atividade computacional disponibilizada
na aula 08.

## Notebooks construídos nas aulas práticas

- Notebook
  [Utilizando o OpenDSS para realização de estudos elétricos](https://tinyurl.com/2h7u94c5)
- Notebook OpenDER 1
- Notebook OpenDER 2
- Notebook OpenDER 3
