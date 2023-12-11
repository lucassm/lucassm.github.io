---
title: 'Convite para Defesas de Trabalhos de Final de Curso'
date: 2023-12-11
permalink: /posts/2023/12/blog-post-1/
tags:
  - Trabalhos de Conclusão de Curso
  - Engenharia Elétrica
  - OpenDSS
  - Distribuição de Energia Elétrica
---

### Estudo Comparativo de PerdasTécnicas em Redes de Distribuição: Análise Entre Diferentes Considerações de Modelagem dos Elementos da Rede Utilizando OpenDSS
- **Aluno**: João Paulo Monteiro Lopes
- **Onde**: Presencial no Laboratório de Circuitos Elétricos (Bloco 706) 
- **Quando**: Segunda-feira (11/12) às 13:30h

<details style="text-align: justify;">
  <summary style="color: #4183c4; text-align: justify;"><b>Resumo</b></summary>
  O presente trabalho tem como objetivo realizar um estudo comparativo de perdas técnicas em um sistema de distribuição de energia em Média Tensão Média Tensão (MT), por meio do software OpenDss, no alimentador CCA01C3 localizado em Caucaia e regiões imediatamente adjacentes. Como é sabido, a ANEEL tem buscado o aprimoramento do método de cálculo de perdas na distribuição no intuito não só de subsidiar a determinação do nível de perdas (técnicas e não técnicas) como também uniformizar o procedimento de cálculo e reduzir a assimetria. Os dados reais do alimentador foram disponibilizados pela ENEL Ceará com a identificação dos elementos como linhas, transformadores, chaves seccionadoras, reguladores de tensão e banco de capacitores. Além disso, foram utilizados o banco de dados do BDGD, com o auxílio do software QGIS, para análise dos dados do alimentador. Com base na simulação do OpenDss, adotou-se dois modelos comparativos: o primeiro baseou-se na metodologia de cálculo com impedância de sequência positiva (R1 e X1), estipulada pela ANEEL. Nessa etapa, a simulação contemplou a inserção de banco de capacitores, regulador de tensão e resistências de aterramento; o segundo modelo, por sua vez, baseou-se na geometria dos condutores, em que foram analisadas duas estruturas da rede aérea de Média Tensão de condutores , N1 e B1, cuja avaliação considerou as perdas isoladamente e em conjunto. A partir das simulações implementadas, considerando a inserção dos elementos para regular o perfil de tensão e o fator de potência e a comparação com o segundo modelo, constatou-se que o nível de perdas técnicas foi relativamente próximo, variando de 3,64 a 6,51%. Portanto, neste estudo comparativo, a modelagem dos parâmetros de linhas por meio da impedância de sequência positiva representou um modelo mais efetivo para o cálculo das perdas técnicas. 
</details>

<br>

### Democratizando a Análise de Redes Elétricas de Distribuição Brasileiras com BDGD-Tools: Contribuições de Desenvolvimento de Aplicação Open Source para Conversão de BDGD em Modelos do OpenDSS
- **Aluno**: Miguel Casemiro
- **Onde**: Virtual por meio do link: https://meet.google.com/dnm-myxr-haq
- **Quando**: Terça-feira (12/12) às 16:00h

<details style="text-align: justify;">
  <summary style="color: #4183c4"><b>Resumo</b></summary>
    Estudos nas redes de distribuição de energia no Brasil desempenham um papel fundamental para garantir o funcionamento eficiente desse serviço vital, podendo ser feitos através de representações em softwares. A modelagem fiel dessas redes pode ser viabilizada através das informações fornecidas pela Base de Dados Geográfica da Distribuidora para simulações no OpenDSS. No entanto, os métodos disponíveis atualmente para esse processo impõem barreiras significativas, como complexidade elevada ou limitações de acesso. Nesse contexto, a aplicação livre BDGD-Tools surge como uma solução para a conversão das informações da BDGD em formato OpenDSS, buscando democratizar a análise das redes de distribuição do Brasil. O objetivo deste trabalho é contribuir para o desenvolvimento da BDGD-Tools, desde seu estágio inicial até uma versão totalmente funcional.A metodologia adotada envolveu o estudo aprofundado da biblioteca, identificação e implementação dos recursos essenciais remanescentes para sua funcionalidade e validação. Destacam-se, entre os recursos implementados, a definição das classes Python dos elementos, aprimoramentos nos módulos de conversão e utilidades, bem como a geração dos arquivos .dss para simulação. A validação da BDGD-Tools foi realizada através da comparação das redes elétricas modeladas pela ferramenta com o método oficial estabelecido pela ANEEL. Utilizou-se como estudo de caso representativo os dados da distribuidora Creluz do ano de 2022, localizada no Rio Grande do Sul. A avaliação concentrou-se na estrutura da rede elétrica convertida, no fluxo de potência e no perfil de tensão gerado. Os resultados obtidos demonstraram a consistência na representação dos elementos da rede elétrica, concordância significativa nos resultados de fluxo de potência e coerência nos perfis de tensão. Essa validação reforça a confiabilidade da BDGD-Tools na precisa tradução da rede elétrica da BDGD para o OpenDSS, proporcionando uma análise detalhada do desempenho da biblioteca em relação aos métodos convencionais da ANEEL. Por fim, são identificadas áreas potenciais para melhorias futuras, focando na experiência do usuário, flexibilidade na configuração da modelagem da rede e maior precisão na conversão.  
</details>

<br>

### Análise de Novas Conexões de Microgeração Distribuída no Alimentador CCA01C3: Análise de Impactos e Mitigações Utilizando o Software OpenDSS.
- **Aluno**: John Alisson de Oliveira Pereira
- **Onde**: Presencial no Laboratório de Circuitos Elétricos (Bloco 706)
- **Quando**: Quarta-feira (13/12) às 14:00h

<details style="text-align: justify;">
  <summary style="color: #4183c4"><b>Resumo</b></summary>
    Com o crescimento das fontes de energias renováveis, em especial a geração
    distribuída, torna-se interessante fazer análises das interações entre esse novo tipo
    de energia e a rede de distribuição já existente. Este trabalho tem como objetivo utilizar o software OpenDSS para modelar um alimentador real da ENEL Distribuição Ceará com a finalidade de se analisar, por meio de simulações, os impactos da microgeração distribuída no sistema de distribuição de energia elétrica, especificamente na curva de carga, a fim de mitigar para esse efeito utilizando elementos de armazenamento (bateria). As simulações foram feitas considerando 4 (quatro) cenários, onde para cada caso foi definido uma porcentagem de penetração de geração distribuída no sistema. No cenário 1, com uma penetração de 25% de GD, foi possível obter, com a adição de bateria no circuito, uma redução de 26% na variação de potência na curva de carga. No cenário 2, teve-se uma redução de 34% na variação de potência e uma redução de 26% na energia injetada referente a curva de carga com a presença de bateria. No cenário 3, obteve-se uma redução na variação de potência de 47% e uma redução na energia injetada na rede de 13%. Todos os valores se referem ao período correspondido entre 16h e 19h.
</details>

<br>