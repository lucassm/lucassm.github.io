---
title: "Trabalho de Avaliação 1"
permalink: /teaching/RC/TA1
venue: "Federal University of Ceara, Department of Electrical Engineering"
date: 2023-09-06
location: "Fortaleza, Brazil"
---

**Título**: Desenvolvimento de uma API na arquitetura cliente/servidor para disponibilização de dados de medições elétricas, acompanhada de testes e validação.

# Especificação dos Requisitos da Aplicação

Com base nos dados de geração PV e de consumo de energia elétrica que estão armazenados nos arquivo disponibilizados abaixo, desenvolva uma **aplicação distribuída** utilizando uma **arquitetura cliente-servidor** que implemente as seguintes funcionalidades:

- Lado servidor que implementa um serviço de entrega dos dados mediante solicitações via sockets TCP/IP para cada um dos pontos de medição (consumo ou geração). O servidor deverá ter um comando que mostra a lista de usuários conectados ao serviço e o endereço IP de cada um. O servidor só disponibilizará o valor de medição mais recente para cada uma das unidades consumidoras; **Peso: 4**
- Lado cliente da aplicação que implemente um serviço de solicitação dos dados utilizando sockets TCP/IP; **Peso: 4**
- Aplicação que disponibilize uma interface de visualização dos dados obtidos no passo acima (dashboard de dados), com um tempo acelerado de solicitação de dados de forma que os dados de um dia sejam visualizados em 1 minuto. **Peso: 2**

Deve ser desenvolvido um procolo personalizado para a requisição e disponibilização dos dados, ou alguma ferramenta padronizada de API (p.e JSON e XML).

O servidor deve aceitar no máximo 10 conexões em paralelo. Quantidades maiores de conexões devem ser tratadas.

Os dados disponibilizados tratam-se dos seguintes arquivos:
- [Dados de Consumo](https://drive.google.com/file/d/1LjLFxxQkHeu7ApfvR0daAgdUrcewzSiL/view?usp=sharing): Medições de um ano a cada 15 minutos de 60 unidades consumidoras distintas;
- [Dados de Geração](https://drive.google.com/file/d/1cQXQLxY50Yu34i_abmkK49cDJz52OWX7/view?usp=sharing): Medições de um ano a cada 15 minutos de uma unidade de geração fotovoltáica;

É necessário um **pré-processamento** dos dados de forma que a curva de geração possa ser associada a **20 das 60 unidades consumidoras**, de forma aleatória.

Frameworks e bibliotecas de terceiros para implementação de aplicações web ou APIs de dados podem ser utilizados no desenvolvimento do trabalho.

## Metadados

- start_date: 2014-01-01 00:00,
- resolution: 15 min,
- unit: W, 
- num_profiles: 60.

## Informações Adicionais

Data de entrega: **04/10/23**
Formato da apresentação: **Oral com slides e execução da aplicação**
Envio dos arquivos (código e apresentação): **[Link](http://forms.google.com)**
