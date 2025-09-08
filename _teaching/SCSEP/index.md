---
title: "Supervisão, Controle e Automação de Sistemas Elétricos de Potência"
collection: teaching
type: "Undergraduate course"
permalink: /teaching/SCSEP
venue: "Federal University of Ceara, Department of Electrical Engineering"
date: 2025-09-05
location: "Fortaleza, Brazil"
---

Nome oficial da disciplina: TH0194 - SUPERVISÃO E CONT. DE SIST. ELÉTRICOS DE POTENCIA

## Dias e Horários da Disciplina

No semestre de *2025.2* a disciplina de Supervisão e Controle de Sistemas Elétricos de Potência (SCSEP) será ofertada *presencialmente* às *terças e quintas* no horário de *16:00 as 18:00*.

Local: Sala ??, Bloco ???. Centro de tecnologia. Campus do Pici. UFC. Fortaleza. Ceará. Brasil.

## Conteúdo Abordado

Este curso tem como objetivo fornecer aos alunos da disciplina noções fundamentais nos seguintes temas:

- **Operação** de sistemas elétricos de potência: topologias, arranjos elétricos, equipamentos primários e secundários;
- **Evolução** dos sistemas de automação no Setor Elétrico;
- Topologias e Tecnologia de **Redes de computadores** LAN e WAN;
- **Sistemas de Aquisição de Dados e Controle Supervisório** - SCADA;
- Digitalização de Sistemas de Automação e Proteção de Subestação - Subestações Digitais;
- Noções básicas de Protocolos de comunicação: ModBus e DNP3;
- Protocolos da norma IEC 61850: MMS, GOOSE e Sampled Values;
- Noções de Sincronismo de tempo em subestações;
- Projetos de sistemas de automação e controle para uma subestação de energia elétrica;

## Detalhamento do Conteúdo

### Módulo 1: Introdução a automação de sistemas elétricos de potência

1. Conceitos básicos de subestações: diagrama unifilar, arranjos, equipamentos primários, sistemas de serviços auxiliares.
2. Conceitos básicos de automação de subestações: UTR, CLP IED, medidor, controlador de Bay, níveis hierárquicos, sistemas scada.
3. Evolução dos sistemas de automação no setor elétrico.

### Módulo 2: Tópicos básicos de redes de computadores

1. Noções básicas de protocolos TCP/IP: Ethernet, IP, TCP, LAN, WAN.
2. Requisitos de redes ethernet para automação de SEs: VLANs, IEEE 802.1q, RSTP.

### Módulo 3: Comunicação em Subestações

1. Sincronização de tempo.
2. Protocolo ModBUS.
3. Protocolo DNP3.
4. Padrões 101, 103, 104.

### Módulo 4: Norma IEC 61850

1. Conceitos básicos.
2. Modelo de dados.
3. Arquivos SCL.
4. MMS, GOOSE e SV.

### Módulo 5: Projetos de Automação de Subestações

1. Arquitetura de comunicação.
2. Documentação de projetos.
3. Demonstrações práticas de níveis de automação 0, 1 e 2.
4. VLANs e priorização de mensagens.

### Tópicos Complementares

1. Segurança Cibernética.
2. Gerenciamento de informação
   2.1. Coleta automática de oscilografias.
   2.2. Monitoramento de equipamentos e da rede de comunicação.
3. Procedimentos de rede do ONS.
4. Virtualização da proteção ou proteção centralizada.
5. Redes de comunicação definidas por software.

## Avaliações

As avaliações estão previstas para ocorrer conforme a data estabelecida no cronograma.

- Data de realização da Avaliação Parcial 01: 23/01/25
- Data de realização da Avaliação Parcial 02: 27/02/25

Conteúdo da **Avaliação Parcial 01**:
- **Unidade 01**: SCADA Fundamentals;
- **Unidade 02**: SCADA Communication (Redes e Protocolo ModBus);


Conteúdo da **Avaliação Parcial 02**:
- **Unidade 03**: SCADA Communication (Protocolos DNP3 e Norma IEC 61850);
- **Unidade 04**: Substation Automation;

[**Planilha de Notas**](/teaching/EE/notas)

## Seminários

**1a Fase**:

Temas retirados da revista IEEE Power and Energy Society Magazine Volume 17, Number 4, July/August 2019, com o título *Substations: The Heart and Brain of the Grid*

- **Seminário 1**: - xx/xx (Equipe 4);
- **Seminário 2**:  - xx/xx (Equipe 2);
- **Seminário 3**:  - xx/xx (Equipe 1);
- **Seminário 4**:  - xx/xx (Equipe 3);
- **Seminário 5**:  - xx/xx (Equipe 5);

**2a Fase**:

A ser definido.

## Trabalhos Complementares

- Trabalho Complementar 1 (xx/xx/xx): Trabalho individual. Com base no diagrama unifilar disponibilizado [aqui](https://drive.google.com/file/d/1_dujEn5-1ty2NOexEotcr9kTOkS3UItn/view?usp=sharing), liste em uma planilha cada um dos equipamentos presentes na SE do diagrama. Descreva o equipamento com base nas informações do diagrama. Apresente os códigos operacionais de cada elemento e indique o que significa o código de cada equipamento. Se houver mais de um equipamento do mesmo tipo, indique a quantidade. Entrega: **01/11/24** em arquivo .pdf pelo link de envio de trabalhos abaixo.
- Trabalho Complementar 2 (xx/xx/xx): Trabalho em dupla. Elaboração de planilha de pontos analógicos e digitais e suas respectivas ligações externas, conforme procedimento descrito [neste arquivo](https://github.com/lucassm/superv-control-ufc/blob/master/AC2/AC2.pdf). Anexo: [anexo](https://github.com/lucassm/superv-control-ufc/blob/master/AC2/1-funcionais-eq-campo-69-13_8.pdf). Data da entrega: **10/01/25** em arquivo .pdf pelo link de envio de trabalhos abaixo.;
- Trabalho Complementar 3 (xx/xx/xx): Lista de exercícios sobre redes locais e camada de enlace e introdução ao uso do pacote Python de análise de redes Scapy. Entrega: **17/01/25**. Arquivo disponível [neste link](https://drive.google.com/file/d/1qsO0F6IxDYElVru5qk1yEXNKBjcYJ1g7/view?usp=sharing)
- Trabalho Complementar 4 (xx/xx/xx): Trabalho a ser realizado em equipes de três membros cada. Desenvolvimento de um simulador de comunicação utilizando os protocolos dnp3 e modbus associados ao sistema SCADA-LTS para representação da subestação de 69,0 kV da UFC. Entrega: **06/03/25**. Arquivo contendo descrição detalhada do trabalho disponível neste [link](https://github.com/lucassm/superv-control-ufc/blob/master/AC4/main.pdf).

Link para envio dos trabalhos: [Envie os trabalhos por aqui](https://forms.gle/2JLAv9788Bdf3QwGA)

## Trabalhos de Avaliação

- [**Trabalho 1**: Integração de base de dados de subestação de 69,0/13,8 kV no SCADA-LTS via Modbus.](/teaching/SCSEP/Trabalho-01)
- [**Trabalho 2**: Parametrização de Relé SEL/Schenneider.](/teaching/SCSEP/Trabalho-02)

Link para envio dos trabalhos: [Envie os trabalhos por aqui](https://forms.gle/2JLAv9788Bdf3QwGA)

## Estrutura da nota

A nota da disciplina será composta pela média ponderada de avaliações escritas e trabalho final, da seguinte forma:

$$
  NF = 0,6 \cdot NAP + 0,4 \cdot NT
$$

Em que, $NF$ é a nota final da disciplina; $NAP$ é a média das notas das avaliações parciais; $NT$ é a média das notas dos trabalhos de avaliação.

$$
    NAP = \frac{NAP_1 + NAP_2}{2}
$$

## Informações adicionais

- Os trabalhos serão realizados em equipe (máx. 03 integrantes);
- A presença nas aulas é importante! Poderá ser motivo de reprovação;

## Softwares

Serão utilizados os softwares durante a disciplina:

- [Wireshark](https://www.wireshark.org/);
- [libiec61850/libiec60870](https://libiec61850.com/)
- [PyModbus](https://pymodbus.readthedocs.io/en/latest/)
- [PyModbusTCP](https://pymodbustcp.readthedocs.io/en/latest/)
- [Simulador modbus - ModbusPal](https://modbuspal.sourceforge.net/)
- [DNP3-python](https://pypi.org/project/dnp3-python/)
- [SCADA-LTS](http://scada-lts.com/)
- [Scapy](https://scapy.net/)

## Bibliografia Básica

- Título: Power System SCADA and Smart Grids, 1a ed, Autor: Mini S. Thomas and John D. McDonald ., Editora: Editora CRC Pres, Ano: 2015.

Além do livro texto, serão disponibilizados **slides** e **outros recursos de texto** que serão disponibilizados no decorrer da disciplina.

## Calendário de Planejamento da disciplina


| **#** | **Dia Semana** | **Data** | **Descrição do Conteúdo**                                                |
| ----- | -------------- | -------- | ------------------------------------------------------------------------ |
| 1     | Terça-Feira    | 22/10/24 | Palestra: O CIPP e seu sistema de Supriento para Cargas Eletrointensivas |
| 2     | Quinta-Feira   | 24/10/24 | Apresentação da Disciplina                                               |
| 3     | Terça-Feira    | 29/10/24 | Unidade 01: Power System Automation                                      |
| 4     | Quinta-Feira   | 31/10/24 | Unidade 03: SCADA Communication – Networking                             |
| 5     | Terça-Feira    | 05/11/24 | Encontros Universitários                                                 |
| 6     | Quinta-Feira   | 07/11/24 | Encontros Universitários                                                 |
| 7     | Terça-Feira    | 12/11/24 | Unidade 01: Power System Automation                                      |
| 8     | Quinta-Feira   | 14/11/24 | Unidade 03: SCADA Communication – Networking                             |
| 9     | Terça-Feira    | 19/11/24 | Unidade 02: SCADA Fundamentals                                           |
| 10    | Quinta-Feira   | 21/11/24 | Unidade 03: SCADA Communication – Networking / Seminário 1               |
| 11    | Terça-Feira    | 26/11/24 | Unidade 02: SCADA Fundamentals                                           |
| 12    | Quinta-Feira   | 28/11/24 | Unidade 03: SCADA Communication – Networking / Seminário 2               |
| 13    | Terça-Feira    | 03/12/24 | Unidade 02: SCADA Fundamentals                                           |
| 14    | Quinta-Feira   | 05/12/24 | Unidade 03: SCADA Communication - Protocolo ModBus / Seminário 3         |
| 15    | Terça-Feira    | 10/12/24 | Unidade 02: SCADA Fundamentals                                           |
| 16    | Quinta-Feira   | 12/12/24 | Unidade 03: SCADA Communication - Protocolo ModBus / Seminário 4         |
| 17    | Terça-Feira    | 17/12/24 | Unidade 03: SCADA Communication - Protocolo ModBus                       |
| 18    | Quinta-Feira   | 19/12/24 | AP 1                                                                     |
| -     | -              | 21/12/24 | Recesso de Fim de Ano – Início                                           |
| -     | -              | 06/01/25 | Recesso de Fim de Ano – Término                                          |
| 19    | Terça-Feira    | 07/01/25 | Unidade 04: Substation Automation                                        |
| 20    | Quinta-Feira   | 09/01/25 | Unidade 03: SCADA Communication - Protocolo DNP3 / Entrega Trabalho 1    |
| 21    | Terça-Feira    | 14/01/25 | Unidade 04: Substation Automation                                        |
| 22    | Quinta-Feira   | 16/01/25 | Unidade 03: SCADA Communication – Protocolo DNP3                         |
| 23    | Terça-Feira    | 21/01/25 | Unidade 04: Substation Automation                                        |
| 24    | Quinta-Feira   | 23/01/25 | Unidade 03: SCADA Communication - Protocolo DNP3                         |
| 25    | Terça-Feira    | 28/01/25 | Unidade 04: Substation Automation                                        |
| 26    | Quinta-Feira   | 30/01/25 | Unidade 03: SCADA Communication - Norma IEC 61850                        |
| 27    | Terça-Feira    | 04/02/25 | Implementação de Lógicas de Proteção/Automação                           |
| 28    | Quinta-Feira   | 06/02/25 | Unidade 03: SCADA Communication - Norma IEC 61850                        |
| 29    | Terça-Feira    | 11/02/25 | Implementação de Lógicas de Proteção/Automação                           |
| 30    | Quinta-Feira   | 13/02/25 | Unidade 03: SCADA Communication - Norma IEC 61850                        |
| 31    | Terça-Feira    | 18/02/25 | Implementação de Lógicas de Proteção/Automação                           |
| 32    | Quinta-Feira   | 20/02/25 | Unidade 03: SCADA Communication - Norma IEC 61850                        |
| 33    | Terça-Feira    | 25/02/25 | Implementação de Lógicas de Proteção/Automação                           |
| 34    | Quinta-Feira   | 27/02/25 | AP 2                                                                     |
| 35    | Terça-Feira    | 04/03/25 | Carnaval                                                                 |
| 36    | Quinta-Feira   | 06/03/25 | Livre / Entrega Trabalho 2                                               |
| -     | -              | 07/03/25 | Término do Semestre Letivo 2024.2                                        |
| -     | -              | 14/03/25 | Último dia para consolidação das notas                                   |
