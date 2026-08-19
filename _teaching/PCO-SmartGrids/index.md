---
title: 'Proteção, Controle e Otimização em Redes Elétricas Inteligentes'
collection: teaching
type: 'Graduate course'
permalink: /teaching/PCOSmartGrid
venue: 'Federal University of Ceara, Department of Electrical Engineering'
date: 2025-09-15
location: 'Fortaleza, Brazil'
---

- [Objetivos do Curso](#objetivos-do-curso)
- [Conteúdo do Curso (Módulos Prof. Lucas Silveira)](#conteúdo-do-curso-módulos-prof-lucas-silveira)
  - [Módulo 1: Métodos de otimização aplicados à SDEE - 10 h (5 aulas)](#módulo-1-métodos-de-otimização-aplicados-à-sdee-10-h-5-aulas)
  - [Módulo 2: Fluxo de potência ótimo e aplicações na rede de transmissão - 10 h (5 aulas)](#módulo-2-fluxo-de-potência-ótimo-e-aplicações-na-rede-de-transmissão-10-h-5-aulas)
  - [Módulo 3: Fluxo de Potência Ótimo e aplicações na rede de distribuição - 10 h (5 aulas)](#módulo-3-fluxo-de-potência-ótimo-e-aplicações-na-rede-de-distribuição-10-h-5-aulas)
- [Bibliografia](#bibliografia)
- [Alunos Participantes da Disciplina](#alunos-participantes-da-disciplina)
- [Trabalhos Computacionais](#trabalhos-computacionais)
- [Seminários](#seminários)
- [Links Importantes](#links-importantes)
- [Calendário de Planejamento da disciplina](#calendário-de-planejamento-da-disciplina)

## Objetivos do Curso

Explorar métodos e **algoritmos de otimização** aplicados nas fases de
planejamento, operação e gestão da rede elétrica com foco na utilização de
ferramentas computacionais e matemáticas modernas e no contexto de redes
elétricas inteligentes, ou seja, explorando esquemas inovadores de interação
entre os diferentes agentes que cooperam ou competem para a realização de
processos próprios dos sistemas elétricos. Além disso, o curso visa capacitar os
alunos a:

- Compreender os fundamentos de otimização e suas aplicações em problemas
  relacionados à engenharia elétrica.
- Compreender os fundamentos de modelagem matemática e computacional de sistemas
  elétricos de transmissão.
- Compreender os fundamentos de modelagem matemática e computacional de sistemas
  elétricos de distribuição.

Aplicar na resolução dos problemas propostos técnicas de machine learning,
levando em consideração a estocasticidade desses sistemas, seja na aquisição de
dados ou na intermitência das fontes geradoras da informação.

Realizar análises analíticas que gerem conhecimento inovador nos mais variados
tipos de problemas relacionados à engenharia elétrica e seus processos de
otimização, controle e proteção, com foco em sistemas elétricos de potência.

## Conteúdo do Curso (Módulos Prof. Lucas Silveira)

### Módulo 1: Métodos de otimização aplicados à SDEE - 10 h (5 aulas)

- Algoritmos de otimização clássica:
  - Programação Linear.
  - Programação Linear Inteira Mista.
  - Programação Não Linear e Convexa.
  - Programação estocástica.
- Heurísticas e meta-heurísticas:
  - Algoritmos Genéticos e Evolutivos.
  - Otimização por Enxame de Partículas.
  - Redes Neurais Artificiais.

### Módulo 2: Fluxo de potência ótimo e aplicações na rede de transmissão - 10 h (5 aulas)

- Fluxo de Potência.
- Fluxo de Potência Ótimo.
- Fluxo de Potência Ótimo Linearizado.
- Aplicações:
  - Economic Dispatch, Unit Commitment e Market Clearing.
- Aplicando o `PowerModels.jl` para resolver problemas de otimização em sistemas
  de transmissão.

### Módulo 3: Fluxo de Potência Ótimo e aplicações na rede de distribuição - 10 h (5 aulas)

- Aspectos gerais dos sistemas de distribuição.
- Modelando sistemas de distribuição com OpenDSS.
- Aplicando o `PowerModelsDistribution.jl` para resolver problemas de otimização
  em sistemas de distribuição.
- Aplicações:
  - Alocação eficiente de Recursos Energéticos Distribuídos (RED).
  - Gerenciamento de RED e Microrredes.
  - Recomposição e reconfiguração da rede elétrica.
  - Gerenciamento pelo lado da demanda e prestação de serviços ancilares.
  - Sistemas de Energia Transativos.

## Bibliografia

No Módulo 1 será utilizado como referência:

- Optimization in Engineering: Models and Algorithms. Ramteen Sioshansi and
  Antonio J Conejo. Springer, 2017. Capítulos 2, 3, 4, 5.

No Módulo 2 será utilizado como referência:

- Power Systems Operations. Antonio J. Conejo and Luis Baringo. Springer, 2018.
  Capítulos 4, 5, 6, 7.

No Módulo 3 será utilizado como referência:

- Distribution System Modeling and Analysis. William H. Kersting. CRC
  Press, 2012. Capítulos 1, 2, 3, 4, 5.
- Documentação do OpenDSS:
  [https://opendss.epri.com/](https://opendss.epri.com/)
- O artigo: "PowerModelsDistribution.jl: An Open-Source Framework for Exploring
  Distribution Power Flow Formulations" de autoria de Lucas Silveira, et al.
  publicado na revista IEEE Transactions on Power Systems, vol. 36, no. 5, pp.
  4300-4311, Sept. 2021.
- Documentação do PowerModelsDistribution.jl:
  [lanl-ansi.github.io/PowerModelsDistribution.jl](https://lanl-ansi.github.io/PowerModelsDistribution.jl/stable/)

## Alunos Participantes da Disciplina

| #   | Nome | Situação |
| --- | ---- | -------- |

## Trabalhos Computacionais

- Trabalho 1.
- Trabalho 2.

## Seminários

- Tema 1.
- Tema 2.

## Links Importantes

- [JuMP](https://jump.dev/JuMP.jl/stable/)
- [PowerModels.jl](https://lanl-ansi.github.io/PowerModels.jl/stable/)
- [PyOmo](https://pyomo.readthedocs.io/en/stable/)
- [Documentação do OpenDSS](https://opendss.epri.com/)
- [PyDSSDirect](https://dssextension.readthedocs.io/en/latest/)
- [PyDSSInterface](https://pydssdinterface.readthedocs.io/en/latest/)

## Calendário de Planejamento da disciplina

| # id | Data       | Descrição do conteúdo                                         |
| ---- | ---------- | ------------------------------------------------------------- |
| 1    | 19/08/2026 | Módulo 1: Fundamentos de Programação Matemática               |
| 2    | 26/08/2026 | Módulo 1: Programação Linear                                  |
| 3    | 02/09/2026 | Módulo 1: Programação Linear                                  |
| 4    | 09/09/2026 | Módulo 1: Programação Linear Inteira Mista                    |
| 5    | 16/09/2026 | Módulo 1: Programação não Linear                              |
| 6    | 23/09/2026 | Módulo 2: O problema de Fluxo de Carga                        |
| 7    | 30/09/2026 | Módulo 2: O problema de Fluxo de Carga Ótimo                  |
| 8    | 07/10/2026 | Módulo 2: Aplicações de FCO em Despacho Econômico             |
| 9    | 14/10/2026 | Módulo 2: Aplicações de FCO em Unit Commitment                |
| 10   | 21/10/2026 | Módulo 2: Aplicações de FCO em Mercado de Energia             |
| 11   | 28/10/2026 | Módulo 2: Utilizando o PowerModels.jl                         |
| 12   | 04/11/2026 | Módulo 3: Aspectos básicos de sistemas de distribuição        |
| 13   | 11/11/2026 | Módulo 3: Modelando sistemas de distribuição com OpenDSS      |
| 14   | 18/11/2026 | Módulo 3: Fluxo de Potência Ótimo em Sistemas de Distribuição |
| 15   | 25/11/2026 | Módulo 3: Utilizando o PowerModelsDistribution.jl             |
| 16   | 02/12/2026 | Módulo 3: Utilizando o PowerModelsDistribution.jl             |
| 17   | 09/12/2026 | Módulo 3: Apresentação de resultados                          |
| 18   | 16/12/2026 | Encerramento do semestre                                      |
