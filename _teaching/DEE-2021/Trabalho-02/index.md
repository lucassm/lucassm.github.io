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
    <img src="{{ '/teaching/DEE-2021/Trabalho-02/rede.png'|url }}" alt="Rede-Trabalho-02" width="500">
</div>

### The Non-line data 
1. Equivalent source
    - Balanced 115 kV line to line
    - Zpos = 1.48 + j11.6 Ω
    - Zzero = 4.73 + j21.1 Ω
    - Bus voltage = 120 V
2.	Substation transformer
    - 115 kV D–12.47 kV grd. Y
    - kVA = 10,000
    - Z = 8.026%, X/R = 8
3. Regulator
    - CT rating = 600
    - %Boost = 10
    - Step size = 0.625
    - Number of steps = 16
    - Nodes: 1–2
    - Specify the voltage level
    - R + jX = ?
4. Single-phase transformer
    - Connection: Y–D one
    - kVA = 100
    - Voltages: 7200 Y–240 D V
    - Z = 2.326%, X/R = 2.1
    - Nodes: 12–13

### The line data is
5. Three-phase OH lines
    - Phase: 336,400 26/7 ACSR
    - Neutral: 4/0 6/1 ACSR
    - Phasing: a-b-c
    - Spacings:
        + Position 1: 0 + j29
        + Position 2: 2.5 + j29
        + Position 3: 7 + j29
        + Neutral: 4 + j25
    - OH 1: Nodes 2–3, 2500 ft
    - OH 2: Nodes 3–4, 3000 ft
    - OH 3: Nodes 4–5, 2500 ft
    - OH 4: Nodes 5–6, 1000 ft
6. Two-phase OH line
    - Phase: 336,400 26/7 ACSR
    - Neutral: 4/0 6/1 ACSR
    - Phasing: ac
    - Spacings:
        + Position 1: 0 + j29
        + Position 2: 7 + j29
        + Neutral: 4 + j25
    - OH 5: Nodes 5–7, 1500 ft
7. Three-phase concentric neutral UG
    - CN cable: 1/0 AA, 1/3 neutral
    - No extra neutral
    - Phasing: cba
    - Spacings:
        + Position 1: 0 − j40 in.
        + Position 2: 6 − j40 in.
        + Position 3: 12 − j40 in.
    - UG 1: Nodes 4–10, 1500 ft
8. Two-phase concentric neutral UG
    - CN cable: 1/0 AA, 1/3 neutral
    - No extra neutral
    - Phasing: cb
    - Spacings:
        + Position 1: 0 − j40 in.
        + Position 2: 6 − j40 in.
    - UG 2: Nodes 10–11, 1000 ft
9. Single-phase concentric neutral UG
    - CN cable: 1/0 AA, Full neutral
    - No extra neutral
    - Phase: c
    - Spacings:
    - Position 1: 0 − j40 in.
    - UG 3: Nodes 10–12, 500 ft
10. Single-phase tape shield cable
    - 1/0 AA tape shield UG
    - Neutral: 1/0 7 strand AA
    - Phase: c
    - Spacings:
        + Position 1: 0 − j40 in.
        + Neutral: 6 − j40 in.
    - UG 4: Nodes 7–8, 500 ft
11.	Two-phase tape shield cable
    - 1/0 AA tape shield UG
    - Neutral: 1/0 7 strand AA
    - Phase: c
    - Spacings:
        + Position 1: 0 − j40 in.
        + Position 2: 6 − j40 in.
        + Neutral: 12 − j40 in.
    - UG 5: Nodes 7–9, 750 ft, phases a–c

### The load data

<div class="text-center">
    <img src="{{ '/teaching/DEE-2021/Trabalho-02/load-data.png'|url }}" alt="Rede-Trabalho-02" width="500">
</div>

## Questões
1. Modelo o sistema proposto no software OpenDSS.
2. Execute o fluxo de carga com o regulador de tensão desativado. Anaise os resultados obtidos.
3. Calcule os parâmetros R e X e o nível de tensão de ajuste adequado, na base de 120V, para o regulador de tensão. Demonstre a realização dos cálculos desses parâmetros.
4. Execute o fluxo de carga com as configurações ajustadas para o regulador de tensão. Quais as posições finais dos taps? Comente o resultado e conclua se foi satisfatório.
5. Adicione capacitores shunt para que o fator de potência da fonte não seja inferior a 0,95 indutivo. Especifique os capacitores em múltiplos de 100 kVAr.
6. Execute o fluxo de carga com os capacitores adicionados e o regulador de tensão ativo. Qual o fator de potência por fase na fonte? Quais as posições finais de tap para os reguladores?

## Outras instruções
- As equipes devem ser compostas por no máximo 5 integrantes; 
- [Vídeo explicativo]();
- [Lista com os nomes dos integrantes de cada equipe](/teaching/DEE-2021/Trabalho-01/Equipes)

## Dúvidas
Em breve.

## Data de Entrega
Prevista para **24/08/21**. Link para entrega será disponibilizado nesta página em breve.

