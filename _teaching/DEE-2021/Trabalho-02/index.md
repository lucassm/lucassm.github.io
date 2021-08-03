---
title: "Distribuição de Energia Elétrica - Trabalho de Disciplina - 02"
collection: teaching
type: conteudo
permalink: /teaching/DEE-2021/Trabalho-02
venue: Federal University of Ceara, Department of Electrical Engineering
date: 2021-08-03
location: Fortaleza, Brazil
---

## Dados

### Diagrama unifilar de sistema de distribuição trifásico desequilibrado:

<div class="text-center">
    <img src="{{ '/teaching/DEE-2021/Trabalho-02/rede.png'|url }}" alt="Rede-Trabalho-02" width="300">
</div>

### The Non-line data 
1. Equivalent source
    a. Balanced 115 kV line to line
    b. Zpos = 1.48 + j11.6 Ω
    c. Zzero = 4.73 + j21.1 Ω
    d. Bus voltage = 120 V
2.	Substation transformer
    a. 115 kV D–12.47 kV grd. Y
    b. kVA = 10,000
    c. Z = 8.026%, X/R = 8
3. Regulator
    a. CT rating = 600
    b. %Boost = 10
    c. Step size = 0.625
    d. Number of steps = 16
    e. Nodes: 1–2
    f. Specify the voltage level
    g. R + jX = ?
4. Single-phase transformer
    a. Connection: Y–D one
    b. kVA = 100
    c. Voltages: 7200 Y–240 D V
    d. Z = 2.326%, X/R = 2.1
    e. Nodes: 12–13

### The line data is
5. Three-phase OH lines
    a. Phase: 336,400 26/7 ACSR
    b. Neutral: 4/0 6/1 ACSR
    c. Phasing: a-b-c
    d. Spacings:
        i. Position 1: 0 + j29
        ii. Position 2: 2.5 + j29
        iii. Position 3: 7 + j29
        iv.  Neutral: 4 + j25
    e. OH 1: Nodes 2–3, 2500 ft
    f. OH 2: Nodes 3–4, 3000 ft
    g. OH 3: Nodes 4–5, 2500 ft
    h. OH 4: Nodes 5–6, 1000 ft
6. Two-phase OH line
    a. Phase: 336,400 26/7 ACSR
    b. Neutral: 4/0 6/1 ACSR
    c. Phasing: ac
    d. Spacings:
        i. Position 1: 0 + j29
        ii. Position 2: 7 + j29
        iii. Neutral: 4 + j25
    e. OH 5: Nodes 5–7, 1500 ft
7. Three-phase concentric neutral UG
    a. CN cable: 1/0 AA, 1/3 neutral
    b. No extra neutral
    c. Phasing: cba
    d. Spacings:
        i. Position 1: 0 − j40 in.
        ii. Position 2: 6 − j40 in.
        iii. Position 3: 12 − j40 in.
    e. UG 1: Nodes 4–10, 1500 ft
8. Two-phase concentric neutral UG
    a. CN cable: 1/0 AA, 1/3 neutral
    b.No extra neutral
    c. Phasing: cb
    d. Spacings:
        i. Position 1: 0 − j40 in.
        ii. Position 2: 6 − j40 in.
    e. UG 2: Nodes 10–11, 1000 ft
9. Single-phase concentric neutral UG
    a. CN cable: 1/0 AA, Full neutral
    b. No extra neutral
    c. Phase: c
    d. Spacings:
    i. Position 1: 0 − j40 in.
    e. UG 3: Nodes 10–12, 500 ft
10. Single-phase tape shield cable
    a. 1/0 AA tape shield UG
    b. Neutral: 1/0 7 strand AA
    c. Phase: c
    d. Spacings:
    i. Position 1: 0 − j40 in.
    ii. Neutral: 6 − j40 in.
    e. UG 4: Nodes 7–8, 500 ft
11.	Two-phase tape shield cable
    a. 1/0 AA tape shield UG
    b. Neutral: 1/0 7 strand AA
    c. Phase: c
    d. Spacings:
        i. Position 1: 0 − j40 in.
        ii. Position 2: 6 − j40 in.
        iii. Neutral: 12 − j40 in.
    e. UG 5: Nodes 7–9, 750 ft, phases a–c

### The load data

<div class="text-center">
    <img src="{{ '/teaching/DEE-2021/Trabalho-02/load-data.png'|url }}" alt="Rede-Trabalho-02" width="300">
</div>

## Questões
1. Modelo o sistema proposto no software OpenDSS.
2. Execute o fluxo de carga com o regulador desativado.
3. Calcule os parâmetros R e X e o nível de tensão para o regulador de tensão uma. Realize esses cálculos na mão.
4. Execute o fluxo de carga com as configurações ajustadas para os reguladores. Quais são as posições finais dos taps? O resultado é satisfatório?
5. Adicione capacitores shunt para que o fator de potência da fonte não seja inferior a 95% atrasado. Especifique os capacitores em múltiplos de 100 kvar.
6. Execute o fluxo de carga com os capacitores adicionados. Qual é o fator de potência por fase na fonte? Quais são as posições finais de tap para os reguladores?

## Outras instruções
- As equipes devem ser compostas por no máximo 5 integrantes; 
- [Vídeo explicativo]();
- [Lista com os nomes dos integrantes de cada equipe](/teaching/DEE-2021/Trabalho-01/Equipes)

## Dúvidas


## Data de Entrega
Prevista para **24/08/21**. Link para entrega será disponibilizado nesta página em breve.

