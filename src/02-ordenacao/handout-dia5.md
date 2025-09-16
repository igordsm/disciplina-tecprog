---
title: Algoritmos recursivos de ordenação
subtitle: Técnicas de Programação
author: Igor Montagner
...


Vamos olhar agora para a seguinte ideia:

1. divida o vetor em duas metades
2. ordene a metade da direita
3. ordene a metade da esquerda
4. combine as duas metades ordenadas tal que agora o vetor inteiro esteja ordenado

## Juntando arrays já ordenados (*MERGE*)

Já fizemos isso manualmente nos slides. Agora é hora de formalizar as variáveis que usaremos no algoritmo. Teremos:

- $\text{AUX}$ - array ordenado final, $\text{AUX}.length = A1.length + A2.length$ 
- $A1$ e $A2$ - sub arrays ordenados
- $K$ - índice de $\text{AUX}$ que será preenchido na iteração atual. Começa em $0$
- $I$ - índice do menor elemento de $A1$ que ainda não foi colocado em $\text{AUX}$. Começa em $0$
- $J$ - índice do menor elemento de $A2$ que ainda não foi colocado em $\text{AUX}$. Começa em $0$

Considere que

- $A1 = [ 4, 4, 7, 8 ]$
- $A2 = [ 1, 3, 5, 6 ]$
- $K = 0$
- $I = 0$
- $J = 0$

Quando fizemos junto na expositiva, registramos um valor em AUX para cada valor de $K$ e depois modificamos ou $I$ ou $J$. Registre esse progresso abaixo. A primeira linha já está feita.

| $K$  | $I$   | $J$  | $\text{AUX}[K]$     |
|:----:|:-----:|:----:|:-------------------:|
| 0    |  1    |  0   | $1$                 |
|      |       |      | \hspace{5em}        |
|      |       |      | \hspace{5em}        |
|      |       |      | \hspace{5em}        |
|      |       |      | \hspace{5em}        |
|      |       |      | \hspace{5em}        |
|      |       |      | \hspace{5em}        |
|      |       |      | \hspace{5em}        |
|      |       |      | \hspace{5em}        |
|      |       |      | \hspace{5em}        |

Agora escreva abaixo o valor final de AUX

$\textrm{AUX} = [ \hspace{10em} ]$

[break]

Mais uma vez, considerando agora que 

- $A1 = [ 4, 4, 7, 8 ]$
- $A2 = [ 1, 3, 5, 6 ]$
- $K = 0$
- $I = 0$
- $J = 0$

Quando fizemos junto na expositiva, registramos um valor em AUX para cada valor de $K$ e depois modificamos ou $I$ ou $J$. Registre esse progresso abaixo. A primeira linha já está feita.

| $K$  | $I$   | $J$  | $\text{AUX}[K]$     |
|:----:|:-----:|:----:|:-------------------:|
| 0    |  1    |  0   | $1$                 |
|      |       |      | \hspace{5em}        |
|      |       |      | \hspace{5em}        |
|      |       |      | \hspace{5em}        |
|      |       |      | \hspace{5em}        |
|      |       |      | \hspace{5em}        |
|      |       |      | \hspace{5em}        |
|      |       |      | \hspace{5em}        |
|      |       |      | \hspace{5em}        |
|      |       |      | \hspace{5em}        |

Agora escreva abaixo o valor final de AUX

$\textrm{AUX} = [ \hspace{10em} ]$

