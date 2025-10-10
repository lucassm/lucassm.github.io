---
title: Introdução ao uso de OpenDSS
date: 25-09-25
permalink: /posts/2025/09/opendss-basics
tags:
  - opendss
  - power systems simulation
  - distribution systems
---

Este artigo irá abordar alguns aspectos básicos de openDSS para quem está
começando a utilizar essa poderosa ferramenta. Por tratar-se de uma ferramenta
com muitos recursos disponibilizados, só aqueles mais básicos serão abordados.
Para um aprofundamento sobre cada um dos conceitos mencionados neste documento,
sempre a [documentação oficial do OpenDSS](https://opendss.epri.com/) poderá ser
consultada.

## o que é o openDSS

O OpenDSS é no mínimo um software diferente. É diferente porque tem uma
abordagem completamente diferente daquela utilizada por ferramentas que
costumamos utilizar na análise de sistemas elétricos de potência.

A primeira diferença notável é que o OpenDSS não tem uma abordagem de interface
gráfica do tipo _arrastar e soltar componentes_ em um plano de trabalho. Essa é
a diferença que mais se destaca no início da utilização da ferramenta.

Na verdade só é possível entender o motivo de certas características do OpenDSS
quando entendemos como funciona sua arquitetura interna. É preciso entender que
quando falamos em OpenDSS na verdade podemos estar nos referindo a um dos
_componentes_ que fazem parte de sua arquitetura, a apenas alguns deles, ou até
mesmo a todos eles de uma vez só. Geralmente quando falamos OpenDSS queremos nos
referir à integração de cada um dos componentes do OpenDSS que juntos conseguem
nos entregar uma poderosa ferramenta de análise de sistemas elétricos de
distribuição.

Mas a verdade é que o OpenDSS é composto de uma junção de partes que estão
integradas e que geram saídas integradas às entradas de outras partes. A figura
abaixo expressa bem essa ideia.

![OpenDSS Engine](https://opendss.epri.com/lib/NewItem25.png)

Dessa forma, o OpenDSS pode ser pensado como tendo um componente básico que é
seu motor de cálculos, escrito atualmente em C++ (e que por muito tempo foi
escrito em Delphi), identificado na figura como _Main Simulation Engine_. Esse
motor de cálculo pode então ser acionado de diferentes formas. A forma mais
fácil e direta de interagir com o motor de cálculo é por meio da interface
gráfica disponibilizada pelo instalador padrão do OpenDSS, disponibilizado
gratuitamente no repositório
[source-forge](https://sourceforge.net/projects/electricdss/).

Essa interface gráfica é bem simples e apresenta basicamente uma tela em branco
em que o usuário pode digitar algum script e é aí, nesse primeiro contato, que
fica claro para o usuário uma característica essencial do OpenDSS, que é a
caracterização do modelo elétrico por meio de sua _linguagem de scripts_.

Pode parecer estranho no primeiro momento abrir mão de um ambiente 100% gráfico
para compor o modelo elétrico, mas quando se analisa redes elétricas de
distribuição reais, em que é comum haver circuitos com milhares de barras, e
milhares de trechos de linhas, então fica claro como é inapropriado o paradigma
de arrastar e soltar para a composição de modelos elétricos de circuitos de
distribuição reais.

![Interface gráfica do OpenDSS](https://opendss.epri.com/lib/NewItem13.png)

Existem outras formas de controlar o motor de cálculo do OpenDSS. A mais
poderosa delas, certamente é por meio de uma linguagem de programação, como por
exemplo _Python_, o que dá muito mais versatilidade e flexibilidade nas
análises, mas por enquanto vamos focar na linguagem de scripts do OpenDSS.

Essa linguagem de _scripts_ é realmente muito importante para um bom domínio da
modelagem de sistemas de distribuição utilizando o OpenDSS. Vou comentar aqui
somente sobre os pontos mais importantes, mas eu aconselho que você aprofunde
sobre esse tópico lendo a [documentação oficial](https://opendss.epri.com/) do
OpenDSS sobre o assunto.

Para iniciar, é importante saber que o OpenDSS divide os componentes da rede
elétrica em dois tipos principais:

- Power Delivery Elements.
- Power Conversion Elements.

Os elementos do tipo `power delivery` são aqueles que geralmente se encontram em
série com o sistema e não possuem dispositivos para conversão da energia
elétrica em outro tipo de energia. Os tipos mais comuns de elementos power
delivery são as linhas de transmissão e os transformadores de potência. Já os
elementos do tipo `power conversion`, na maioria dos casos se encontram em
paralelo com o sistema e apresentam mecanismo de conversão da energia elétrica
em outros tipos de energia, este é o típico caso de cargas elétricas presentes
no sistema.

Exemplos de elementos do tipo Power Delivery são:

- Line
- Transformer
- Capacitor
- Reactor

Exemplos de elementos do tipo Power Conversion são:

- Load
- Generator
- Vsource
- Isource
- Storage

Além desses elementos, que são elementos físicos, o OpenDSS possue outros
elementos não físicos que não se encaixam nessa categorias, podemos listar
alguns deles.

Elementos do tipo `Controls`:

- RegControl.
- CapControl.
- Relay.
- Reclose.
- Fuse.

Elementos do tipo `Meters`:

- Monitor.
- EnergyMeter.
- Sensor.

Elementos do tipo `General`:

- LineCode
- LineGeometry
- WireData
- LoadShape
- TCCcurve
- XfmrCode

Listados os principais elementos presentes no OpenDSS, agora podemos ver como
declará-los em um script utilizando a sintaxe própria do OpenDSS.

De acordo com a documentação oficial, as declarações na linguagem do OpenDSS
sempre irão seguir a seguinte combinação:

```txt
command param1, param2, param3, ...
```

Alguns exemplos de comandos comuns são:

- `New`: Create a new circuit element.
- `Edit`: Edit a specified circuit element.
- `Set`: Define solution options, like the mode.
- `Solve`: Perform a solution of the current circuit
- `Show`: Display power flow results in text format.
- `Export`: Export power flow results to a text/csv file.
- `Plot`: Plot power flow results.

O primeiro elemento que iremos demonstrar como exemplo aqui será o elemento
`Circuit`, que é obrigatório em qualquer circuito declarado em OpenDSS:

```txt
New circuit.IEEE13Nodeckt
~ basekv=115 pu=1.0001 phases=3 bus1=SourceBus
~ Angle=30
~ MVAsc3=20000 MVASC1=21000
```

Esse bloco de comandos realiza a declaração de um elemento `circuit` que fornece
alimentação elétrica para a rede a ser simulada. Dentro do bloco de declaração
desse elemento é importante destacar alguns comandos. O bloco é iniciado pelo
comando `New` e em seguida uma série de parâmetros seguidos de seus valores. O
tipo e o nome do novo elemento declarados, nesse caso são
`circuit.IEEE13Nodeckt` e estão separados por um `.`, já o operador `~` indica
que a lista de parâmetros do comando anterior irá se estender por mais uma
linha.

> É importante mencionar aqui que o OpenDSS **não é case sensitive**.

Cada um dos elementos do OpenDSS são declarados seguindo essa mesma lógica. Por
exemplo, observarmos o código de declaração do transformador do sistema teste
IEEE 13 barras, teremos:

```txt
New Transformer.Sub Phases=3 Windings=2   XHL=(8 1000 /)
~ wdg=1 bus=SourceBus conn=delta kv=115 kva=5000 %r=(.5 1000 /) XHT=4
~ wdg=2 bus=650 conn=wye kv=4.16 kva=5000 %r=(.5 1000 /) XLT=4
```

Aqui é importante mencionar que o OpenDSS tem uma certa _filosofia_ de não ter
um modo único de realizar determinadas ações. Por exemplo, o elemento
transformer, pode ser declarado de qualquer um dos modos abaixo:

```txt
New transformer.reg1a phases=3 windings=2 buses=[150 150r] conns=[wye wye]
~ kvs=[4.16 4.16] kvas=[5000 5000] XHL=.001 %LoadLoss=0.00001 ppm=0.0

New Transformer.XFM1 Phases=3 Windings=2 Xhl=2.72
~ wdg=1 bus=61s conn=Delta kv=4.16 kva=150 %r=0.635
~ wdg=2 bus=610 conn=Delta kv=0.48 kva=150 %r=0.635
```

Depois de entender como declarar os elementos que compõem um circuito elétrico
no OpenDSS, é natural que se faça a pergunta:

> como os elementos OpenDSS são conectados uns com os outros?

Isso é interessante porque as conexões estabelecidas pelo OpenDSS não são
conexões simples do tipo conectado ou não conectado, mas sim conexões que
precisam definir se a conexão pretendida será do tipo monofásica, bifásica ou
trifásica. Além disso, é preciso estabelecer ligações de um condutor neutro,
caso exista e também de aterramento desse condutor, e dos elementos elétricos
que estão sendo conectados, assim como saber a sequência correta de conexão
desses condutores. Para cumprir esses requisitos o OpenDSS utiliza as seguintes
definições terminológicas:

- Nó: É uma posição de conexão elétrica fixa em um barramento.
- Barramento: É uma coleção de nós.
- Condutor: Representa um ponto de conexão elétrica em um elemento, com
  potencial elétrico bem definido.
- Terminal: É uma coleção de condutores.

Utilizando essas definições é possível representar _qualquer tipo de conexão
elétrica entre elementos polifásicos_, considerando todas as características de
geometria importantes para a realização dos estudos elétricos pelo motor de
cálculo do OpenDSS.

De acordo com a documentação oficial do OpenDSS o usuário pode definir como os
condutores estão conectados aos nós do barramento de três formas distintas:

- A primeira forma de conexão entre elementos é também a mais simples. Nessa
  forma o terminal do elemento simplesmente é conectado à uma barra ou
  barramento, sem nenhuma indicação explícita de qual condutor estará conectado
  a qual nó do barramento. Quando isso é feito o OpenDSS realiza a ligação dos
  condutores fase em sequência com os nós do barramento e então conecta o
  condutor neutro no nó zero da barra em questão, que no OpenDSS, por padrão tem
  potencial de terra.
- Na segunda possibilidade de ligação, é indicada a conexão do primeiro condutor
  fase a um determinado nó j da barra em questão. Dessa forma, os demais
  condutores fase são conectados aos outros nós seguindo a sequencia de fase
  positiva, enquanto o condutor neutro será conectado no nó zero da barra, sendo
  forçado para o potencial de neutro.
- Por fim, na terceira possibilidade, um mapeamento explícito é realizado entre
  os condutores de fase e de neutro e os nós do barramento.

Para entender melhor esse processo os modelos abaixo podem servir de auxilio:

```txt
nome_da_barra.i.j.k em que i, j, k se referem aos nós do barramento
```

Esse comando é interpretado da seguinte forma: primeiro condutor fase do
elemento é conectado ao nó i, segundo condutor fase/neutro do elemento é
conectado ao nó j, terceiro condutor fase/neutro do elemento é conectado ao nó
k.

Se a conexão entre condutores e nós do barramento não forem especificados
explicitamente, o comportamento padrão do OpenDSS é o seguinte:

```txt
BUSNAME.1.0.0.0.0.0.0. … (Single-phase terminal)
BUSNAME.1.2.0.0.0.0.0. … (two-phase terminal)
BUSNAME.1.2.3.0.0.0.0 … (3-phase terminal)
```

Os exemplos abaixo para a conexão de um transformador _delta-estrela_ serão
elucidativos:

Conexão de transformador _delta-estrela-aterrado_:

```txt
New transformer.xfmr_name
~ phases=3 windings=2
~ Bus1=Bus_A.1.2.3
~ Bus2=Bus_B.1.2.3.0
~ conns=[delta, wye]
```

Conexão de transformador _delta-estrela-não-aterrado_:

```txt
New transformer.xfmr_name
~ phases=3 windings=2
~ Bus1=Bus_A.1.2.3
~ Bus2=Bus_B.1.2.3.4
~ conns=[delta, wye]
```

Conexão de transformador _delta-estrela-aterrado-por-reator_:

```txt
New transformer.xfmr_name
~ phases=3 windings=2
~ Bus1=Bus_A.1.2.3
~ Bus2=Bus_B.1.2.3.4
~ conns=[delta, wye]

New reactor.rg_name
~ phases=1
~ Bus1=Bus_B.4
~ Bus2=Bus_B.0
~ R=0.1 X=700.0
```

## Principais Elementos e suas características

Agora que está claro como a conexão dos elementos é realizada no OpenDSS, ou
mais especificamente, como é realizada a conexão entre os condutores dos
terminais dos elementos e os nós dos barramentos, é importante conhecer um pouco
das características dos principais elementos encontrados nas redes elétricas de
distribuição, são eles:

- Elemento Fonte de Tensão
- Elemento Linha de Distribuição
- Elemento Transformador
- Elemento Carga

Existem ainda os elementos de controle que também são bastante importantes:

- Controle de regulador de tensão
- Controle de bancos de capacitores

Outros elementos importantes são:

- Curva de cargas
- Medidor
- Monitor
- Geração fotovoltaica

A seguir será demonstrado como cada um dos elementos citados pode ser declarado
e utilizado de acordo com a linguagem de scrips do OpenDSS.

O primeiro elemento a ser analisado é o elemento fonte de tensão:

```txt
New circuit.IEEE13Nodeckt
~ basekv=115 pu=1.0001 phases=3 bus1=SourceBus
~ Angle=30
~ MVAsc3=20000 MVASC1=21000
```

Esse elemento já havia sido declarado acima, mas é interessante comentar sobre
algumas de suas características. Talvez os parâmetros mais importantes desse
elemento sejam os `MVAsc3=20000` e `MVAsc1=21000` que indicam respectivamente
_potência de curto-circuito monofásica_ e _potência de curto-circuito
trifásica_.

Além dos valores de potência de curto-circuito trifásico e monofásico também é
possível entrar com outros pares de valores para determinar todos os parâmetros
necessários na caracterização da fonte de tensão do circuito, são eles:

- Potências de curto-circuito trifásico e monofásico.
- Correntes de curto-circuito trifásico e monofásico.
- Impedâncias de sequência positiva e zero.

Um elemento essencial na representação de sistemas de distribuição é a linha de
distribuição. De maneira geral, a linha de distribuição deve ser determinada por
sua _matriz de impedância de fase_ assim como por sua matriz de admitância
shunt. Segue exemplo de declaração de uma linha de distribuição por meio dos
parâmetros de impedância séria da matriz de impedâncias de fase:

```
New linecode.mtx601 nphases=3 BaseFreq=60
~ rmatrix = (0.3465 | 0.1560 0.3375 | 0.1580 0.1535 0.3414 )
~ xmatrix = (1.0179 | 0.5017 1.0478 | 0.4236 0.3849 1.0348 )
~ units=mi

New Line.650632 Phases=3 Bus1=RG60.1.2.3 Bus2=632.1.2.3
~ LineCode=mtx601 Length=2000 units=ft
```

Nesse caso temos dois elementos distintos que se juntam para compor um elemento
físico único, ou seja, a linha de distribuição. Esses elementos são `LineCode` e
`Line`.

Repare que no elemento `LineCode` são passados os parâmetros de resistência e de
reatância indutiva, por meio de uma notação de matriz triangular superior, sendo
o carácter `|` responsável por separar as linhas da matriz de impedâncias.

Outro elemento físico presente no sistema de distribuição é o _transformador_.
Para a representação adequada dos elementos transformadores na rede elétrica,
diversos aspectos devem ser levados em consideração, tais como:

- potência do transformador.
- nível de tensão dos enrolamentos primário e secundário.
- tipo de conexão dos enrolamentos do transformador.
- defasamento angular entre primário e secundário.
- perdas ativas e reativas no núcleo e no cobre do transformador.
- entre outros parâmetros.

Abaixo segue um exemplo de declaração de um elemento transformador:

```txt

```

## A importância dos sistemas teste do IEEE no desenvolvimento do OpenDSS

Um famoso paper escrito pelo subcomitê de análise de sistemas de distribuição da
Power and Energy Society
[IEEE Radial Distribution Test Feeders](https://ewh.ieee.org/soc/pes/dsacom/testfeeders/testfeeders.pdf)
