---
title: Python 3.0 is here!
date: 2026-04-21
permalink: /posts/2026/04/pade-3-0-release/
tags:
  - pade
  - multiagent systems
  - python
  - openTES
---

![pade-3-0-release](https://i.imgur.com/xjLIdw8.jpeg){width="80%"}

Depois de quase quatro anos sem novas versões do PADE, finalmente temos o
lançamento da versão 3.0 do nosso framework. Para complementar esse marco
importante para o PADE achei importante falar um pouco sobre a história desse
simples, porém importante, software e também falar algo sobre o que esperar para
o futuro dessa iniciativa.

Voltando ao início de tudo, a ideia de trabalhar com sistemas multiagentes veio
do grupo de professores da área de sistemas de energia do Departamento de
Engenharia Elétrica da Universidade Federal do Ceará, notadamente os professores
Raimundo Furtado, Ruth Leão e Giovanni Cordeiro. Nessa época, mais ou menos no
ano de 2010, eles estavam no início de um projeto de pesquisa e desenvolvimento
com a então Coelce, Companhia de Distribuição de Energia Elétrica do Ceará, que
tinha como objetivo o desenvolvimento de um sistema de recomposição automático
de alimentadores de distribuição. A ideia era entregar para a distribuidora um
sistema centralizado, mas dentro das pesquisas do projeto também se estudava
como seria um sistema desse tipo mas com uma abordagem distribuída, e
especificamente utilizando o conceito de sistemas multiagentes (SMA).

Na época eu era estudante de graduação e fui selecionado pelo professor Raimundo
Furtado como bolsista de iniciação científica para apoiar o projeto justamente
no desenvolvimento de um sistema de recomposição automático de alimentadores de
distribuição utilizando o conceito de SMA. Utilizamos para essa tarefa um
framework Java chamado JADE (Java Agent DEvelopment framework).

Os estudos foram bem produtivos, e permitiram que eu conseguisse produzir meu
trabalho de final de curso nesse tema e também que publicassemos artigos em
eventos nacionais e em periódicos internacionais. Essa pesquisa me estimulou a
buscar uma pós-graduação, e assim eu entrei no mestrado no Departamento de
Engenharia Elétrica em Fortaleza-Ce.

Nessa época meu interesse pela linguagem de programação Python estava bem alto e
eu não podia deixar de cogitar a possibilidade de desenvolver SMA utilizando
Python. Porém, algo era impeditivo, justamente a inexistência de boas opções em
Python de frameworks para desenvolvimento de SMA, tais como o estável e bem
estabelecido JADE do Java. É justamente nesse ponto que nasce o PADE (Python
Agent DEvelopment framework) em 2013.

O JADE tinha uma grande vantagem que era a implementação de diversos padrões
estabelecidos pela FIPA (Foundation for Interoperable and Physical Agents) e que
facilitavam e padronizavam a implementação de comportamentos nos agentes.
Tomando como bases esses mesmos princípios o PADE começou a ser desenvolvido e
continuou assim até a defesa de minha dissertação em 2015.

Após esse período o desenvolvimento do PADE continuou de forma mais lenta e
intermitente, até que em 2018 o professor Raimundo, utilizando o PADE, defende
sua tese de doutorado sendo um dos membros da banca o professor Felipe Saraiva
da UFPA, que se interessa bastante pelo projeto, envolvendo um de seus alunos de
graduação no desenvolvimento de funcionalidades para o PADE.

Essa parceria com a UFPA foi bem proveitosa gerando um trabalho bem interessante
sobre a integração do PADE com o framework de co-simulação em Python, Mosaik no
WESAAC de 2019 e que inclusive foi escolhido como um dos melhores trabalhos do
evento.

Com o desenvolvimento do meu doutorado o PADE foi bastante solicitado e algumas
correções de bugs e melhorias pontuais foram implementadas. Foi nesse período
que o lançamento dos agentes passou a acontecer por meio do comando `pade` ao
invés de simplesmente chamar o arquivo .py pelo comando `python`. Isso deu muito
mais flexibilidade e possibilidades de execução aos agentes PADE.

A integração com Mosaik também foi algo muito útil e inovador no ecossistema de
SMA. O artigo original do PADE foi então publicado no ano de 2020 e minha tese
de doutorado, com utilização massiva da integração do PADE com o ambiente de
co-simulação coordenado pelo Mosaik, defendida em 2022.

Desse ano em diante o desenvolvimento do framework de fato ficou reduzido a
quase zero e algumas tentativas de retomada no desenvolvimento foram realizadas
sem sucesso, até que no ano de 2025 o Grupo de Redes Elétricas Inteligentes -
GREI iniciou o projeto OpenTES e a necessidade de atualização do PADE foi
encarada como uma das prioridades do projeto.

Um dos bolsistas de IC foi designado para realizar essa tarefa de atualização e
uma estratégia eficiente para atacar o que se fazia necessário foi desenvolvida
por nós. O nome do bolsista que realizou essa atualização importante do PADE é
Francisco Douglas e aqui estamos lançando o PADE 3.0

Outro fato i que é importante ser mencionado nesse resumo da história do PADE é
que diversos pesquisadores e desenvolvedores do mundo todo tomaram conhecimento
do PADE e começaram a utilizá-lo eventualmente dando feedbaEck sobre algumas
funcionalidades, bugs e sugestões de melhoria.

## O que há de novo nessa atualização do PADE

Precisamente nesse mês de abril de 2026 as atualizações necessárias para ter o
PADE executando novamente em versões mais atuais de Python e de suas bibliotecas
foram concluídas e finalmente temos uma versão funcional do PADE 3.0.

Para que o PADE pudesse ser novamente utilizado nas versões atuais do Python
algumas decisões de simplificação do sistema como um todo tiveram que ser
tomadas, mas que se mostraram bem acertadas no final. Talvez a maior alteração
tenha sido a retirada total, pelo menos por enquanto, do suporte à interface
gráfica do PADE, que era realizada via aplicação web construída com Flask e que
utilizava como padrão de armazenamento de informações um banco de dados SQLite.

De fato a eliminação do Flask juntamente com seus inúmeros plugins auxiliares
permitiram uma simplificação profunda no código fonte do PADE. Tudo isso se dá
também em decorrência da comunicação que precisa ser realizada entre o PADE e o
banco de dados da aplicação, de forma assíncrona e não bloqueante, um dos
requisitos do framework base do PADE, o Twisted que é baseado em programação
assíncrona.

Com base nessas principais alterações, do ponto de vista do usuário, o que irá
mudar? Além da indisponibilidade da interface gráfica, algumas pequenas
alterações foram realizadas por conta principalmente dessa questão da interface
gráfica e do banco de dados. Todo o processo de troca de mensagens entre os
agentes e de registro de agentes na plataforma agora é registrado em arquivos
.csv o que torna o acesso dos usuários aos registros do sistema bem mais fácil e
simplificada.

O processo de instalação do PADE via `uv` também simplifica bastante o processo
de ter os agentes prontos para serem executados.

## Quais os planos para o futuro?

Para o futuro temos muito a ser feito. A primeira coisa a ser feita é testar a
integração do PADE com o Mosaik integrado a um simulador de comunicação e assim
implementar o modo simulação nos PADE para que os tempos de envio das mensagens
seja levado em consideração. Essa funcionalidade já está em desenvolvimento.

Outra necessidade é a integração dos agentes PADE com agentes de IA generativa,
algo bem importante no contexto atual.

Além disso é preciso inserir uma API mais assíncrona ao PADE, reforçando o
aspecto do framework ser baseado em comunicação assíncrona.

A integração nativa com containers Docker é também algo bastante importante a
ser implementado.

Enfim, muitas possibilidades podem ser perseguidas ainda e muitas melhorias
podem ser realizadas. Esperamos que novas parcerias possam ser realizadas e que
o PADE seja utilizado ainda em muitos trabalhos e projetos comerciais e
acadêmicos.
