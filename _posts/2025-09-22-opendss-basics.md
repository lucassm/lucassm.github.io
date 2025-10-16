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
com possibilidade de utilização em muitos tipos de cenários distintos e com
muitos recursos disponibilizados, só aqueles mais básicos serão abordados neste
artigo. Para um aprofundamento sobre cada um dos conceitos mencionados neste
documento, recomenda-se a consulta à
[documentação oficial do OpenDSS](https://opendss.epri.com/).

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
escrito em Delphi), identificado na figura como _Main Simulation Engine_.

Esse motor de cálculo pode então ser acionado de diferentes formas. A forma mais
fácil e direta de interagir com o motor de cálculo é por meio da interface
gráfica disponibilizada pelo instalador padrão do OpenDSS, acessível
gratuitamente no repositório
[source-forge](https://sourceforge.net/projects/electricdss/).

Essa interface gráfica é bem simples e apresenta basicamente uma tela em branco
em que o usuário pode digitar algum script. É aí, nesse primeiro contato, que
fica claro para o usuário uma característica essencial do OpenDSS, que é a
caracterização do modelo elétrico por meio de sua _linguagem de scripts_.

Pode parecer estranho no primeiro momento abrir mão de um ambiente 100% gráfico
para compor o modelo elétrico, mas quando se analisa redes elétricas de
distribuição reais, em que é comum haver circuitos com milhares de barras, e
milhares de trechos de linhas, então fica claro como é _inapropriado_ o
paradigma de arrastar e soltar para a composição de modelos elétricos de
circuitos de distribuição reais.

![Interface gráfica do OpenDSS](https://opendss.epri.com/lib/NewItem13.png)

Existem outras formas de controlar o motor de cálculo do OpenDSS. A mais
poderosa delas, certamente é por meio de uma linguagem de programação, como por
exemplo _Python_, o que dá muito mais versatilidade e flexibilidade nas
análises. Mas por enquanto vamos focar na linguagem de scripts do OpenDSS.

## Scripts OpenDSS

A linguagem de _scripts_ do OpenDSS é muito importante para um bom domínio da
modelagem de sistemas de distribuição utilizando o OpenDSS. Iremos comentar aqui
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

O primeiro elemento a ser demonstrado como exemplo aqui será o elemento
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

> É importante mencionar aqui que a linguagem de scripts do OpenDSS **não é case
> sensitive**.

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

## Conectando elementos no OpenDSS

Esse tópico é importante porque as conexões estabelecidas pelo OpenDSS não são
conexões simples do tipo conectado ou não conectado, mas sim conexões que
precisam definir se a conexão pretendida será do tipo monofásica, bifásica ou
trifásica. Além disso, é preciso estabelecer ligações de um condutor neutro,
caso exista e também de aterramento desse condutor, e dos elementos elétricos
que estão sendo conectados, assim como saber a sequência correta de conexão
desses condutores. Para cumprir esses requisitos o OpenDSS utiliza as seguintes
definições terminológicas:

- _Nó_: É uma posição de conexão elétrica fixa em um barramento.
- _Barramento_: É uma coleção de nós.
- _Condutor_: Representa um ponto de conexão elétrica em um elemento, com
  potencial elétrico bem definido.
- _Terminal_: É uma coleção de condutores.

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

## Montagem de sistema exemplo no OpenDSS

A seguir será demonstrado como cada um dos elementos citados pode ser declarado
e utilizado de acordo com a linguagem de scrips do OpenDSS. Para facilitar essa
abordagem será utilizado um sistema de exemplo, e cada um dos seus elementos e
parâmetros será descrito.

O Sistema a ser descrito está mostrado na figura abaixo:

![opendss example network](https://i.imgur.com/55P0jVQ.png)

O primeiro elemento a ser analisado é o elemento fonte de tensão:

```txt
New Circuit.Equivalente bus1=A pu=1.02 basekv=138
~ Z0=[0.025862916, 0.077588748] Z1=[0.023094242, 0.092376969]
```

Essa linha de comando declara um elemento fonte de tensão com as seguintes
características:

- fonte de tensão trifásica.
- tensão de base de 138kV
- nível de tensão atual de 1,02 pu.
- impedância equivalente de fonte em suas componentes de sequência positiva e
  zero.

Esse último parâmetros é um dos mais importantes e define como a fonte de tensão
irá se comportar mediante diferentes regimes de operação.

Uma fonte de tensão trifásica em OpenDSS por padrão apresenta o seguinte modelo
elétrico:

![modelo elétrico de uma fonte de tensão trifásica em OpenDSS](https://i.imgur.com/rZJZwkn.png)

Como é possível visualizar no modelo elétrico, o OpenDSS precisa calcular as
impedâncias próprias e mútuas da fonte, para isso é preciso que uma das opções
de pares de parâmetros sejam informadas:

- `MVAsc3` e `MVAsc1` que indicam respectivamente _potência de curto-circuito
  monofásica_ e _potência de curto-circuito trifásica_.
- `Isc3` e `Isc1` Correntes de curto-circuito trifásico e monofásico.
- `Z1` e `Z0` Impedâncias de sequência positiva e zero.

![modelo matemático da fonte de tensão do OpenDSS](https://i.imgur.com/RY0elm0.png)

O próximo elemento mostrado no diagrama da rede exemplo é um transformador
trifásico. O código abaixo declara esse transformador:

```txt
New Transformer.Trafo phases=3 windings=2 %loadloss=0.15 xhl=5
~ %noloadloss=0.015 %imag=2
~ wdg=1 bus=A kv=138 kva=3000 conn=delta
~ wdg=2 bus=B kv=13.8 kva=3000 conn=wye
~ sub=Yes subname=Subestacao
```

Trata-se de transformador trifásico, de dois enrolamentos, conectado em delta no
primário e em estrela no secundário, com o centro estrela aterrado. A potência
dos dois enrolamentos do transformador é de 3,0 MVA. As tensões estão
especificadas por enrolamentos e são de 138 kV no primário e 13,8 kV no
secundário. Além desse elementos são mais fáceis de serem identificados na
declaração, existem ainda os parâmetros que modelam as perdas no transformador,
são eles:

- `%loadloss`: representa a resistência do ramo série do transformador em valor
  percentual.
- `xhl`: representa a reatância do ramo série do transformador em valor
  percentual.
- `%noloadloss`: representa a resistência do ramo de magnetização, em valor
  percentual.
- `%imag`: representa a reatância indutiva do ramo de magnetização, em valor
  percentual.

O modelo elétrico desse elemento transformador pode ser visualizado na figura
abaixo:

![modelo elétrico de transformador trifásico no OpenDSS](https://i.imgur.com/1yOm0Hu.png)

Na rede exemplo que está sendo executada existem dois tipos de elementos linhas
de distribuição. Na figura abaixo é possível visualizar a representação elétrica
de uma linha de distribuição trifásica à quatro condutores, ou seja, com
condutor neutro explícito:

![diagrama elétrico de linha de distribuição 3p-1n](https://i.imgur.com/ktklInT.png)

Logo abaixo estão representados em termos de script OpenDSS, os dois seguimentos
de linha da rede exemplo:

```txt
// Modelos de Linhas
New Linecode.MeuArranjo4 nphases=4 basefreq=60 units=km
~ rmatrix = [0.249 |0.059 0.249 |0.059 0.059 0.249 |0.059 0.059 0.059 0.427] !ohm/km
~ xmatrix = [0.878 |0.529 0.878 |0.451 0.484 0.878 |0.467 0.488 0.476 0.960] !ohm/km
~ cmatrix = [9.353 |-3.028 9.858 |-1.160 -1.928 8.891 |-1.393 -1.772 -1.782 8.809] !nF/km
~ neutral=4 kron=No

New Linecode.MeuArranjo3 nphases=3 basefreq=60 units=km
~ rmatrix = [0.249 |0.059 0.249 |0.059 0.059 0.249]     !ohm/km
~ xmatrix = [0.878 |0.488 0.878 |0.488 0.488 0.878]     !ohm/km
~ cmatrix = [8.932 |-2.290 8.932 |-2.290 -2.290 8.932]  !nF/km

// Dados dos Trechos
New Line.LinhaBC bus1=B.1.2.3.0 bus2=C.1.2.3.4 length=0.8 units=km linecode=MeuArranjo4
New Line.LinhaCD bus1=C.1.2.3 bus2=D.1.2.3 length=0.6 units=km linecode=MeuArranjo3
```

No script é possível identificar a presença de dois elementos distintos:

- `Linecode`: Modelo de linha reutilizável
- `Line`: Trecho de linha que utiliza como modelo elétrico um elemento declarado
  pelo `Linecode`.

Além disso há uma diferença notável entre os dois modelos de linhas. No linecode
`MeuArranjo4` além do parâmetro `nphases=4` a quantidade de elementos declarados
nos parâmetros `rmatrix`, `xmatrix` e `cmatrix` excede em uma unidade os
elementos declarados no linecode `MeuArranjo3`, que tem o o parâmetro
`nphases=3`. O que essas diferenças representam?

Por fim, os últimos elementos físicos são declarados, ou seja, as cargas
conectadas nas barras do sistema:

```txt
// Dados das Cargas
// Model=1 -> Potencia Constante
New Load.CargaC phases=1 bus1=C.1.4 kv=7.9674 kw=500 pf=0.92 model=1
New Load.CargaD phases=3 bus1=D conn=wye kv=13.8 kw=2000 pf=0.92 model=1
```

Um elemento importante, principalmente no cálculo de perdas elétricas, é o
elemento `EnergyMeter`. A declaração do EnergyMeter pode ser vista abaixo:

```txt
// Medidor
New EnergyMeter.MedidorSub element=Transformer.Trafo terminal=1
```

A importância do elemento `EnergyMeter` ficará mais visível quando o modo de
simulação `Daily` for apresentado. Por enquanto, é possível pensar nesse
elemento como o elemento que permite o cálculo das perdas elétricas no circuito.

Por fim a declaração de elementos da rede é finalizada com alguns comandos de
configuração das tensões de base, além do importante comando de `Solve`, que é
quem executa o fluxo de carga. Comando `Set mode=snapshot` é desnecessário nesse
caso pois esse já é o modo padrão do OpenDSS.

```txt
// Definindo Tensoes de base
Set voltagebases=[138 7.9674 13.8]
Calcvoltagebases

// SnapShot Mode
Set mode=SnapShot
Solve
```

Os comandos listados abaixo atribuem coordenadas para as barras do circuito,
permitindo uma visualização georreferenciada do circuito em análise. Após esse
comando, diversos comandos de exibição de resultados são listados, sendo
possível, por meio desses comandos visualizar tensões, correntes, potências e
perdas elétricas.

```txt
// Coordenadas
BusCoords Coordenadas.csv

// Arquivos de Resultados
Show Voltage LN Nodes
Show Power Elements
Show Currents Elements
Show Losses
```

A final, alguns resultados da simulação são exibidos em forma de gráficos
utilizando o comando `Plot`.

```txt
// Perfil de Tensao
// Plot Profile

// Plot o Circuito
// Plot circuit Power Max=2200 dots=y labels=y subs=y C1=Blue

```

## Transformando uma análise estática em temporal

Para adaptar o circuito OpenDSS utilizado na análise de uma condição de
carga/geração fixa, algumas poucas alterações e inclusões precisarão ser
realizadas. É importante mencionar aqui que nada muda nos elementos físicos em
si, com exceção do elemento carga que precisa sofrer uma pequena alteração.

Para ser mais específico, uma análise de fluxo de carga temporal poderá ser
realizada utilizando os seguintes elementos:

- `LoadShape`: Declara uma curva de carga com valores relativos à potência da
  carga referida.
- `Set Mode=Daily`: Altera o modo de simulação para uma simulação temporal de
  24h.
- `Monitor`: Elemento que permite a visualização das grandezas elétricas após a
  realização da simulação temporal.

Abaixo estão listados alguns trechos de código necessários para transformar a
análise de fluxo de carga estático em fluxo de carga temporal:

```txt
// Dados das Curvas de Carga
New Loadshape.industrial npts=24 interval=1
~ mult=(0.1 0.1 0.2 0.3 0.3 0.4 0.6 1.2 1.8 1.8 1.9 1.9 1.4 1.6 1.8 1.7 1.7
1.1 0.8 0.6 0.5 0.4 0.2 0.2)
New Loadshape.residencial npts=24 interval=1
~ mult=(0.6 0.5 0.4 0.4 0.5 0.8 1.0 0.8 0.8 0.9 1.0 1.0 1.1 0.9 0.9 0.9 1.0
1.2 1.5 1.5 1.7 1.5 1.2 0.8)

// Dados das Cargas
// Model=1 -> Potencia Constante
New Load.CargaC phases=1 bus1=C.1.4 kv=7.9674 kw=500 pf=0.92 model=1 daily=residencial
New Load.CargaD phases=3 bus1=D conn=wye kv=13.8 kw=2000 pf=0.92 model=1 daily=industrial
```

```txt
// Medidor
New EnergyMeter.MedidorSub element=Transformer.Trafo terminal=1

// Monitores
// Monitores na Sub (deve ser conectado em um elemento e nao em uma barra)
New Monitor.PotenciaSub element=Transformer.Trafo terminal=1 mode=1 ppolar=no
New Monitor.TensaoSub element=Transformer.Trafo terminal=1 mode=0

// Monitores na CargaD
New Monitor.PotenciaCargaD element=Load.CargaD terminal=1 mode=1 ppolar=no
New Monitor.TensaoCargaD element=Load.CargaD terminal=1 mode=0
```

```txt
// Time-Series Mode
Set controlmode=Static
Set mode=Daily
Set stepsize=1h
Set number=24
Solve

// Resultados do Medidor
// Show meters
// Export meters
```

O trecho abaixo mostra os comandos necessários para a correta visualização das
grandezas armazenadas pelos monitores ao longo da simulação temporal.

```txt
// ==========================
// Resultados dos Monitores
// ==========================

// Monitor de Potencia da Sub
// Export monitors potenciasub
// Plot monitor object= potenciasub channels=(1 3 5 )

// // Monitor de Tensao da Sub
// Export monitors tensaosub
// Plot monitor object= tensaosub channels=(1 3 5 ) bases=[79674.3 79674.3 79674.3]

// // Monitor de Potencia da CargaD
// Export monitors potenciacargad
// Plot monitor object= potenciacargad channels=(1 3 5 )

// // Monitor de Tensao da CargaD
// Export monitors tensaocargad
// Plot monitor object= tensaocargad channels=(1 3 5 ) bases=[7967.4 7967.4 7967.4]
```

## A importância dos sistemas teste do IEEE no desenvolvimento do OpenDSS

Um famoso paper escrito pelo subcomitê de análise de sistemas de distribuição da
Power and Energy Society
[IEEE Radial Distribution Test Feeders](https://ewh.ieee.org/soc/pes/dsacom/testfeeders/testfeeders.pdf)
