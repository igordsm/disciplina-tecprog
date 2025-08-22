---
title: Análise de desempenho
subtitle: Técnicas de Programação
author: Igor Montagner
...

::: warn :::
Atenção

Esta atividade usa os algoritmos da aula passada. Tenha sua folha em mãos para facilitar o trabalho!
:::

## Parte 1 - comparando as buscas

Seja um algoritmo que faz $f(n)$ operações e um algoritmo que faz $g(n)$ operações, ambos no pior caso. O primeiro algoritmo cresce mais rápido que o segundo se e somente se:

$$
\lim_{n\rightarrow +\infty} \frac{f(n)}{g(n)} = +\infty
$$

**Exercício**: Escreva abaixo uma entrada de tamanho `8` e um valor a ser buscado que faça a busca sequencial e a busca binária fazerem o máximo de operações possível (ou seja, rodarem o **pior caso**). Ao lado, coloque o número de operções feitas. 

[spacer]

**Exercício**: Tente escrever o número de operações em função do tamanho $N$ do array.

[line-spacer]

**Exercício**: Calcule o limite $\lim_{n\rightarrow +\infty} \frac{n}{\log_2(n)}$. (**Use L'Hôpital**)

[break]

## Parte 2 - um outro exemplo prático

Vamos agora comparar os dois algoritmos acima com o seguinte algoritmo `Busca2a2` mostrado abaixo.

\begin{algorithm}[H]
\DontPrintSemicolon
\SetAlgoLined
\SetKwInOut{Input}{Input}\SetKwInOut{Output}{Output}
\Input{array $A$, int $V$}
\Output{int}
\BlankLine

$i \gets 0$;

\While{$i < A.length$}{
    \If{$A[i] = V$}{
        \Return{true};
    }
    \If{$i > 0 \textbf{ and } A[i] > V$}{
        \Return{$A[i-1] = V$};
    }
    $i \gets i + 1$;
}
\Return{$A.length > 0 \textbf{ and } A[A.length - 1] = V$};
\caption{Busca2a2}
\end{algorithm} 

**Exercício**: Qual seria uma entrada de tamanho $N=5$ para o algoritmo acima que resulta em seu pior caso? Escreva os valores de $A$ e $V$

[line-spacer]

**Exercício**: em termos de $N=A.length$, quantas operações são feitas no pior caso?

[line-spacer]

**Exercício**: Compare o algoritmo `Busca2a2` com a busca sequencial vista na aula passada. Use a definição de limite. 

[spacer]

**Exercício**: Compare o algoritmo `Busca2a2` com a busca binária vista na aula passada. Use a definição de limite. 
