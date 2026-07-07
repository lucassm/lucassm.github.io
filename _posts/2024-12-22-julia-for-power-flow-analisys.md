---
title: Julia para engenheiros, minhas impressões
date: 25-12-23
permalink: /posts/2025/12/from-python-to-julia
tags:
  - Julia
  - scientific-programming
  - python
  - power-systems development
---

Desde meados de 2024 tenho iniciado um processo muito interessante de exploração
de uma linguagem de programação diferente daquela que já vinha utilizando ha um
bom tempo, ou seja, Python.

Python foi um bom companheiro durante pelo menos 10 anos de minha trajetória
acadêmica. Python me acompanhou na graduação, no mestrado e no doutorado! Essa
linguagem de programação incrível foi uma peça central em quase todos os meus
trabalhos acadêmicos durante todo esse tempo, e eu sinceramente não espero
deixar de utilizar Python na maioria dos trabalhos que tenho executado como
professor e pesquisador na área de sistemas elétricos de potência. Porém,
algumas alternativas podem ser interessantes de ser exploradas, na verdade, já
há um bom tempo existe uma alternativa para a área de computação numérica tem
ganhado um número cada vez maior de entusiastas. Essa linguagem de programação
que já tem pelo menos 15 anos de vida, chama-se `Julia` e tem um ecossistema de
bibliotecas vibrante e em pleno crescimento, pronto para ser explorado e
descoberto por quem se interessa pela área de computação científica.

É fato que essa área foi dominada durante muito tempo inicialmente pela
linguagem `Fortran` e depois disso, talvez pela linguagem `Matlab`, que tem sua
versão open-source definida pelo `Octave`. Matlab/Octave foram certamente meu
primeiro contato com as linguagem de programação científicas e eu pude trabalhar
com elas durante algum bom tempo na minha graduação, mas a descoberta de Python,
que estava integrada de um modo tão próximo do ambiente `Linux` me fizeram
deixar essas possibilidades de lado talvez de forma precoce para um acadêmico,
mas certamente de forma definitiva, de modo que evitei e continuo evitando essas
alternativas o máximo que pude ao longo de minha trajetória profissional.

A descoberta das bibliotecas Python `Numpy`, `Scipy` e `Matplotlib` foram algo
muito marcante na minha trajetória de aprendizado dessas novas tecnologias de
computação científica. A combinação dessas três bibliotecas ofereciam
basicamente tudo que o Matlab poderia oferecer, e o melhor de tudo, são software
livre e integradas com o ambiente Linux com facilidade. Além disso, por ser
Python uma linguagem de propósito geral, a possibilidade de integrar essas
ferramentas com outros frameworks como por exemplo, frameworks para construção
de sistemas web, interfaces gráficas, interação com bancos de dados, entre
outras infinitas possibilidades torna Python uma das ferramentas mais poderosas
para um cientista/programador aprender e utilizar na construção de aplicações.
Essa foi sem dúvida a minha visão.

Com a minha entrada na pós-graduação, as possibilidades certamente foram
ampliadas, com por exemplo, a descoberta de outras bibliotecas e aplicações do
mundo Python que o tornam ainda mais poderoso, como por exemplo as bibliotecas:
`Pandas`, `Scikit-Learn`, `Pyomo`, `Mosaik`, `Pandapower`, `Pypower` e até
mesmo, (por que não?) os frameworks web `Flask` e `Django`. E sem esquecer, é
claro, toda a facilidade que a distribuição científica de Python proporciona,
estou falando da distribuição Python `Anaconda`.

Outra aplicação que me marcou e que é simplesmente fantástica, foram os
`Jupyter Notebooks`, que são uma evolução do `IPython` terminal e que
proporcionam toda aquela integração entre código e texto markdown rodando
diretamente no navegador de internet! Simplesmente sensacional!

Um mundo de possibilidades se abre com a simples leitura de alguns poucos
tutoriais dessas bibliotecas Python. Mas aí vêm as primeiras limitações, que sem
dúvidas a mais importante é a velocidade de execução dos algoritmos quando
comparado à outras linguagens de programação, inclusive o próprio Matlab/Octave.

É nesse contexto, sem dúvida, que começa a nascer um crescente interesse por
essa linguagem de programação que nasce tímida meio que ofuscada pelo sucesso de
Python, mas que com o tempo vem se mostrando cada vez mais robusta e com um
ecossistema que cresce e se diversifica proporcionando a possibilidade de
utilização de diferentes ferramentas para o desenvolvimento de aplicações
científicas altamente profissionais, e o que é melhor, totalmente open-source em
sua grande maioria. Estou falando do `Julia`, é claro.

O Julia vem com uma promessa interessante de fusão do que há de melhor entre as
três linguagens de programação mais utilizadas por cientistas no mundo: Python,
Matlab e R. E ainda com um conceito de múltiplo despacho que o torna único, além
é claro do foco em velocidade de execução. Isso o torna uma opção muito
competitiva para ser utilizado no desenvolvimento de aplicações científicas,
além é claro, diferente de Python, por exemplo, de ter foco em computação
cientifica, o que deixa sua sintaxe muito mais clara, fácil e concisa na
realização de operações com matrizes. Veja:

Declaração de duas matrizes e a multiplicação entre elas usando Python:

```Python
import numpy as np

A = np.array([[1, 2], [3, 4]])
B = np.array([[5, 6], [7, 8]])

C = np.dot(A, B)
```

Declaração de duas matrizes e a multiplicação entre elas usando Julia:

```Julia
A = [1 2; 3 4]
B = [5 6; 7 8]

C = A * B
```

O ecossistema Julia já possui muitas bibliotecas que substituem de maneira muito
satisfatória suas equivalentes Python. Alguns exemplos mais notáveis são:

- `Numpy`: Julia já possui nativamente suporte à manipulação e operações de
  estruturas matriciais e de arranjos numéricos.
- `Scipy`: Julia também já possui nativamente suporte à diversas áreas de
  aplicação científica, como por exemplo Álgebra Linear, Probabilidade, Cálculo,
  etc. Além disso, como foco de Julia é computação científica, Julia não possui
  uma biblioteca que concentre várias funcionalidades de computação científica
  como o Scipy, mas ao invés disso diversas bibliotecas voltadas cada uma para
  determinada área do conhecimento. Ou seja, o ambiente de bibliotecas
  científicas é bem mais diverso do que o próprio ambiente Python.
- `Matplotlib`: A biblioteca Julia `Plots` faz um bom trabalho na plotagem de
  gráficos, embora existam outras boas alternativas como por exemplo, `Makie`.
- `Pandas`: A biblioteca `DataFrames` é um belo substituto ao `Pandas`.
- `Jupyter`: O projeto Jupyter já nasceu com a ideia de poder executar
  utilizando o mesmo _frontend_ diversos _kernels_ cada um fornecendo suporte à
  uma linguagem de programação. Na verdade, Julia faz parte do nome do projeto,
  uma vez que temos: _Ju_ de Julia, _Py_ de Python e _teR_ de R. Dessa forma, é
  natural poder utilizar um notebook Jupyter com um kernel Julia usando suas
  inúmeras funcionalidades. Para instalar um kernel Julia no Jupyter, basta
  instalar a biblioteca `IJulia` no ambiente Julia padrão e o kernel Julia é
  reconhecido de forma automática, sem nenhuma ação adicional necessária.

Nesse ponto acho apropriado mencionar um projeto muito popular na comunidade
Julia e que tem uma proposta muito interessante, que é o projeto `Pluto`
notebooks. Trata-se de um sistema de notebooks semelhante aos Jupyter mas com
uma interface muito mais elegante, minimalista e pensada na experiência do
usuário e além disso com uma diferença essencial, trata-se de um notebook
reativo, ou seja, o estado de cada célula é consistente com todas as outras
células do notebook, algo parecido com o que acontece em uma planilha de Excel.
Dessa forma, sempre que, por exemplo, uma variável é atualizada em uma célula,
essa alteração é refletida de forma automática em todas as outras células do
notebook. A primeira vista essa característica pode parecer uma limitação, mas é
uma peça chave para que os Pluto Notebook sejam muito mais voltados à
reprodutibilidade que os notebooks Jupyter. Outra característica excelente
desses notebooks é que ao contrário dos Jupyter notebooks, que têm um formato
próprio, `.ipynb`, os notebooks Julia têm extensão `.jl` e todas as informações
de configuração do notebooks são armazenadas em forma de comentário, isso
facilita muito a utilização de notebooks Pluto com sistemas de controle de
versão de código. Por fim, os notebooks Pluto possuem informações de
versionamento das bibliotecas utilizadas no próprio arquivo `.jl` o que reforça
muito essa característica de reprodutibilidade dos Pluto notebooks. Vale muito a
pena testar notebooks Pluto.

Para finalizar esse artigo, concluo dizendo que o ecossistema Julia é muito rico
e diverso, e que ao contrário de Python, que para computação científica muitas
vezes concentra as soluções na biblioteca `Scipy`, em Julia as soluções para os
problemas diversos das diversas áreas da ciência estão espalhadas por muitas
iniciativas em grupos de pesquisa espalhados pelo mundo todo e que encontraram
no Julia uma solução elegante e eficiente para utilizar em suas pesquisas. Um
bom exemplo disso é a biblioteca `PowerModels.jl` para quem é da área de
sistemas de potência, uma biblioteca excelente que mescla fluxo de carga com
otimização matemática por meio da biblioteca `JuMP` de forma que nenhum outro
projeto consegue e que é desenvolvida por um instituto de pesquisa de ponta, nos
Estados Unidos, em Los Alamos.

Em uma próxima postagem irei mencionar as principais ferramentas necessárias
para facilitar o desenvolvimento de aplicações em Julia.
