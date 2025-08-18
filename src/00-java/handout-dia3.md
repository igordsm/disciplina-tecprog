---
title: Algoritmos básicos em Strings
subtitle: Técnicas de Programação
author: Igor Montagner
...

::: tip :::
Instruções

Vamos agora tentar **escrever** pseudo código. Cada exercício abaixo tem espaço para escrever e algumas entradas de teste. A ideia é só partir pra implementação **depois** de ter testado com sucesso para as entradas do material impresso. 

Não se esqueça de consultar o cheat sheet para ver como traduzir o pseudo código para Java e os slides do dia 2 para ver quais operações são possíveis. 
:::

## Prefixo

Dada uma string $S$, verifique se a string $Q$ é um prefixo de $S$. Ou seja, se os primeiros $Q.length$ caracteres de $S$ são exatamente iguais à string $Q$.

\begin{algorithm}[H]
\DontPrintSemicolon
\SetAlgoLined
\SetKwInOut{Input}{Input}\SetKwInOut{Output}{Output}
\Input{string $S$, string $Q$}
\Output{bool}

\vspace{15em}

\caption{Prefixo}
\end{algorithm} 

**Entradas de teste**:

- $S=\text{"aa"}, Q=\text{"a"}$
- $S=\text{"abcaas sdfsd a"}, \text{Q="abc"}$
- $S=\text{"a"}, Q=\text{"abc"}$
- $S=\text{"aabc"}, Q=\text{"abc"}$


[break]


## Sufixo

Dada uma string $S$, verifique se a string $Q$ é um sufixo de $S$. Ou seja, se os últimos $Q.length$ caracteres de $S$ são exatamente iguais à string $Q$.

\begin{algorithm}[H]
\DontPrintSemicolon
\SetAlgoLined
\SetKwInOut{Input}{Input}\SetKwInOut{Output}{Output}
\Input{string $S$, string $Q$}
\Output{bool}

\vspace{15em}

\caption{Sufixo}
\end{algorithm} 

**Entradas de teste**:

- $S=\text{"aa"}, Q=\text{"a"}$
- $S=\text{"abcaas sdfsd a"}, \text{Q="abc"}$
- $S=\text{"a"}, Q=\text{"abc"}$
- $S=\text{"aabc"}, Q=\text{"abc"}$

[break]

## Busca de termo 1

Dada uma string $S$, a string $Q$ está contida em $S$ em qual posição? Devolva a **primeira** posição em que isso acontece. Se a string $Q$ não estiver contida em $S$ devolva $-1$. Em Java este método se chama `indexOf`.

\begin{algorithm}[H]
\DontPrintSemicolon
\SetAlgoLined
\SetKwInOut{Input}{Input}\SetKwInOut{Output}{Output}
\Input{string $S$, string $Q$}
\Output{int}

\vspace{20em}

\caption{Busca}
\end{algorithm} 

::: tip :::
Dica

O algoritmo *Prefixo* pode te dar inspiração para este exercício. Você não irá chamá-lo diretamente, mas ele pode fazer parte da *Busca*
:::


**Entradas de teste**:

- $S=\text{"aa"}, Q=\text{"a"}$
- $S=\text{"saaabcaas sdfsd  a"}, \text{Q="abc"}$
- $S=\text{"a"}, Q=\text{"abc"}$
- $S=\text{"aabcbca abc bda"}, Q=\text{"abc"}$


[break]

## Busca de termo 2

Dada uma string $S$, a string $Q$ está contida em $S$ em qual posição? Devolva a **última** posição em que isso acontece. Se a string $Q$ não estiver contida em $S$ devolva $-1$. Em Java este método se chama `lastIndexOf`.

\begin{algorithm}[H]
\DontPrintSemicolon
\SetAlgoLined
\SetKwInOut{Input}{Input}\SetKwInOut{Output}{Output}
\Input{string $S$, string $Q$}
\Output{int}

\vspace{20em}

\caption{BuscaReversa}
\end{algorithm} 

::: tip :::
Dica

O algoritmo *Sufixo* pode te dar inspiração para este exercício. Você não irá chamá-lo diretamente, mas ele pode fazer parte da *Busca*
:::


**Entradas de teste**:

- $S=\text{"aa"}, Q=\text{"a"}$
- $S=\text{"saaabcaas sdfsd  a"}, \text{Q="abc"}$
- $S=\text{"a"}, Q=\text{"abc"}$
- $S=\text{"aabcbca abc bda"}, Q=\text{"abc"}$


[break]

## Substituição

Dada uma string $S$ e duas string $Q$ e $Nq$, devolva uma nova string $S2$ em que a primeira ocorrência de $Q$ é substituída por $Nq$. Em Java este método é chamdado de `replace`.

\begin{algorithm}[H]
\DontPrintSemicolon
\SetAlgoLined
\SetKwInOut{Input}{Input}\SetKwInOut{Output}{Output}
\Input{string $S$, string $Q$, string $Nq$}
\Output{string}

\vspace{24em}

\caption{Substitui}
\end{algorithm} 

::: tip :::
Dica

Este exercício é parecido com a busca, mas como agora temos que criar uma nova string precisamos usar a operação de concatenação. Você pode, inclusive, chamar o algoritmo *Busca* em seu pseudo código.

- $s_1 + s_2$ cria uma nova string com as duas strings anteriores concatenadas
- $s_1 = \text{""}$ cria uma string vazia (que você pode usar para ir concatenando o resto!)
:::

**Entradas de teste**:

- $S=\text{"abc bla bla"}, Q=\text{"a"}, Nq=\text{"b"}$
- $S=\text{"abc bla bla"}, Q=\text{"bla"}, Nq=\text{"bu"}$
- $S=\text{"abc bla bla"}, Q=\text{"a"}, Nq=\text{"bca"}$

[break]

## Substituir todos

Dada uma string $S$ e duas string $Q$ e $Nq$, devolva uma nova string $S2$ em que a **todas** ocorrência de $Q$ são substituídas por $Nq$. Em Java este método é chamdado de `replaceAll`.

\begin{algorithm}[H]
\DontPrintSemicolon
\SetAlgoLined
\SetKwInOut{Input}{Input}\SetKwInOut{Output}{Output}
\Input{string $S$, string $Q$, string $Nq$}
\Output{string}

\vspace{24em}

\caption{SubstituiTodos}
\end{algorithm} 

::: warn :::
Aviso

Este é um exercício **difícil**. As entradas abaixo são mais fáceis que as dos testes de unidade e vão ajudá-los a entender problemas comuns no algoritmo de vocês.
:::

**Entradas de teste**:

- $S=\text{"abc bla bla"}, Q=\text{"a"}, Nq=\text{"b"}$
- $S=\text{"abc bla bla"}, Q=\text{"bla"}, Nq=\text{"bu"}$
- $S=\text{"abc bla bla"}, Q=\text{"a"}, Nq=\text{"bca"}$



