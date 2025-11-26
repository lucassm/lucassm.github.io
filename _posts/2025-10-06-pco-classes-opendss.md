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

> O notebook com todos os procedimentos realizados nas aulas sobre OpenDSS em
> ambiente do google colab está disponível no link abaixo:
> [Utilizando o OpenDSS para realização de estudos elétricos](https://tinyurl.com/2h7u94c5)

## Aula 08 - 05-11-2025

Não houve encontro em decorrência dos encontros universitários 2025.

Foi encaminhada uma atividade com prazo de entrega para 19-11-2025.

A descrição da atividade está disponível
[neste link](https://tinyurl.com/yc3vrpjr)

## Aula 09 - 12-11-2025

Nesta aula foi dado inicio à discussão a respeito da modelagem de recursos
energéticos distribuídos (RED), ou no inglês _distributed energy resources_
(DER). Como visto nas aulas anteriores, o OpenDSS possui elementos padronizados
que modelam alguns dos principais tipos de RED presentes nos sistemas de
distribuição atuais, como por exemplo os elementos `pvsystem` e `storage`.

A questão é que os RED que já estão implementados no OpenDSS disponibilizam
apenas recursos básicos de modelagem, limitando assim a realização de certos
tipos de análises importantes de serem efetuadas no contexto de integração de
RED à rede elétrica.

Dessa forma, foi apresentado o padrão IEEE 1547-2018, que tem como título: _IEEE
Standard for Interconnection and Interoperability of Distributed Energy
Resources with Associated Electric Power Systems Interfaces_

Esse padrão disponibiliza diversas orientações e proposições de funcionalidades
que têm como objetivo principal possibilitar a expansão dos RED por meio de
funções avançadas de suporte à rede elétrica, tais como:

- auxílio à rede principal no suprimento de suporte de potência ativa, reativa e
  ajuste de tensão.
- suportabilidade à condições adversas na rede.
- suporte na melhoria dos índices de qualidade de energia.
- função de ilhamento em determinadas porções da rede elétrica.
- questões relacionadas à interoperabilidade e interface entre dispositivos RED.

Tendo em vista o potencial de aplicação e a importância que esse padrão tem em
um cenário de expansão de RED, o instituto americano EPRI, que também é o
principal responsável pelo desenvolvimento do OpenDSS, lançou outra importante
iniciativa, o `OpenDER`. Trata-se da implementação prática de todos os
requisitos estabelecidos e descritos pela IEEE 1547. Essa implementação prática
tem dois elementos principais:

- A biblioteca Python `OpenDER` disponibilizada livremente por meio de um
  [repositório público no `GitHub`](https://github.com/epri-dev/OpenDER)
- Um documento pdf, batizado de `modelo de especificação` da IEEE 1548-2018,
  também
  [disponibilizado livremente pelo EPRI em formato pdf](https://www.epri.com/research/products/000000003002030962).

Após a explicação dos principais conceitos relacionados ao padrão IEEE 1547
2018, foram explorados os conceitos mais básicos da biblioteca Python `OpenDER`
por meio de um notebook no google colab.

Todos os notebooks utilizados durantes as aulas de `OpenDER` e
`OpenDERinterface` serão disponibilizados para consulta e execução em uma pasta
compartilhada do google colab. O link para acesso à pasta compartilhada
encontra-se disponível ao final da descrição da próxima aula.

## Aula 10 - 19-11-25

Nesta aula foram aprofundados os conceitos relacionados à norma IEEE 1547 2018,
assim como a utilização da biblioteca Python `OpenDER`. O EPRI além de
disponibilizar a OpenDER, também disponibiliza livremente uma outra biblioteca
chamada `OpenDERinterface` que possibilita a integração das funcionalidades de
modelagem da biblioteca OpenDER com o simulador da rede elétrica, o OpenDSS.

A biblioteca `openDERinterface` utiliza como padrão a biblioteca
`OpenDSSinterface` para prover a comunicação com o OpenDSS. No entanto essa
biblioteca ainda possui algumas limitações em sua integração com o ambiente
Linux, dessa forma, foi disponibilizada uma adaptação que ao invés de utilizar a
OpenDSSinterface para a comunicação com o OpenDSS utiliza a biblioteca
`OpenDSSDirect` que possui um suporte ao Linux mais consolidado. Para instalar
essa adaptação nos notebooks do google colab basta digitar em uma célula de
código o seguinte comando:

```bash
pip install opender-interface-direct
```

Dessa forma foi possível utilizar todas as funcionalidade disponibilizadas pela
OpenDERinterface sem maiores problemas no ambiente do google colab. Os notebooks
utilizados nessa aula estão disponíveis em pasta compartilhada no google drive e
podem facilmente serem visualizados e executados utilizando um ambiente de
google colab.

Todos os notebooks com exemplos das bibliotecas Python `OpenDER` e
`OpenDERinterface` estão disponíveis por meio de notebooks do google colab nesse
link:
[notebooks com exemplos no google colab](https://drive.google.com/drive/folders/1xaI73wTas80vElbSRG5oGuMsSjnhgUwX?usp=sharing)

## Aula 11 - 26-11-25

Tema a ser abordado: Conceitos básicos de otimização.
