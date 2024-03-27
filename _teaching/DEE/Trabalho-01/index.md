---
title: "Distribuição de Energia Elétrica - Trabalho de Disciplina - 01"
collection: teaching
type: conteudo
permalink: /teaching/DEE/Trabalho-01
venue: Federal University of Ceara, Department of Electrical Engineering
date: 2024-03-26
location: Fortaleza, Brazil
---

# Trabalho-Computacional-1-DIST

## Parte 1 (4,0 pts)
Utilizando a biblioteca Python Simbench carregue a rede com o seguinte código:
*1-LV-rural3-all-0-sw*

Realize as seguintes tarefas utilizando os dados da rede elétrica carregada:

1. Gere uma tabela e um gráfico de fatores de diversidade até o número máximo de consumidores presentes na rede elétrica. Utilize a metodologia de cálculo baseada em amostras de 30 consumidores para cada ponto da curva de fator de diversidade.
2. Execute o fluxo de carga para a rede e verifique suas condições operacionais (tensões e carregamento dos condutores) para o momento de pico do sistema.
3. Plote o gráfico de demanda elétrica vs. energia elétrica para o conjunto de prosumidores da rede.

## Parte 2 (4,0 pts)

Carregue a rede com o seguinte código:
*1-LV-rural1-all-0-sw*

1. Utilize o gráfico gerado no item 3 da parte 1 para calcular as demandas máximas de cada consumidor e compare com o valor real.
2. Com os valores estimados de demanda máxima de cada consumidor calcule a demanda máxima não co-incidente. 
3. Com o valor de demanda máxima não co-incidente encontrado no item anterior estime o valor de demanda máxima diversificada por meio da tabela de fatores de diversidade encontrada no item 1 da parte 1. Compare com o valor real de demanda diversificada para esta rede.


## Parte 3: Bônus! (4,0 pts)

Carregue a rede com o seguinte código:
1-MV-rural--0-sw

1. Utilize o método de alocação baseado em potência dos transformadores para obter os fluxos de potência na rede elétrica.
2. Substitua esses valores nas cargas e execute o fluxo de carga.
3. Execute o fluxo de carga na rede real no momento da demanda máxima e compare com os resultados reais.

**Obs: Nota do trabalho satura em 10,0 pts**


## Outras instruções
- As equipes devem ser compostas por 4 integrantes cada;
- Serão realizadas apresentações com o resultado do trabalho;
- Consultar material sobre alocação de cargas em alimentadores de distribuição e jupyter notebooks utilizados durante aula prática realizada no LI disponíveos no [repositório Github da disciplina de distribuição](https://github.com/lucassm/dist-ufc)

## Dúvidas
- Serão tiradas em sala de aula

## Data de Entrega
Prevista para **25/04/24**.

