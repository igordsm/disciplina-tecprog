---
footer: 'Igor Montagner (igorsm1@insper.edu.br)'
---

<!-- _class: front -->

# Enumeração Exaustiva

## Técnicas de Programação

------

# Problema

Enumerar todas as sequências de DNA com tamanho até $N$

- cada caractere pode ser `A, T, C, G`
- exemplos:
    - "AATC"
    - "TG"
    - "AA"

-------------------------


# Problema (exemplos de saída)

## $N=1$

<span class="height: 4em; display: block;">&nbsp;</span>

## $N=2$


--------

# Problema (tamanho da saída)

| $N=1$       | $N=2$ | $N=3$ | ........... | $N=??$   |
|:-----:      |:-----:|:-----:|:-----:      |:-----:|
| &nbsp;      |       |       |             |       |

------------

# E se implementar com $N=2$ fixo? Como seria o algoritmo?




--------------

# E se implementar com $N=3$ fixo? Como seria o algoritmo?


---------------

<!-- _class: front -->

# O número de `for` aninhados é o parâmetro!

------

# Recursão

## algoritmo que **chama a si mesmo** uma ou mais vezes

## passando uma instância **menor** do problema

--------

<!-- _class: front -->

# Atividade 1: revisão de simulação de algoritmo recursivos

## Exercícios no PrairieLearn - recursão com uma chamada só

--------

# Exemplo (recursivo) para $N=3$

------------

# Pensando em recursão

1. Para $N=1$, precisamos de chamada recursiva?


-----

# Pensando em recursão

2. Quais seriam os parâmetros do nosso algoritmo?


-------------


# Pensando em recursão

3. Para $N$ qualquer, quantas chamadas recursivas precisamos?

-----

# Juntando tudo isso



----------

<!-- _class: front -->

# Atividade 2 - implementação + conferência da saída

## Podem usar o que quiserem. O foco é pensar nas questões da atividade de hoje


