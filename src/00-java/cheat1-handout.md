
---
title: Cheat Sheet Java - Parte 1
subtitle: Técnicas de Programação
author: Igor Montagner
...

<!-- Escreveremos tudo em pseudo código nesta disciplina. Esta folha vai mostrar comandos em Java equivalentes para que possamos implementá-los corretamente. A coluna da esquerda sempre representa pseudo-código, enquanto a da direita sempre é código java. -->

<!-- Todas estruturas de controle (condicionais, loops, `print`) funcionam igual em Python, o que iremos fazer é **retirar as coisas específicas de Python** para que as ideias possam ser implementadas em qualquer linguagem. -->

## Algoritmos, Variáveis e Atribuições

Toda variável e valor de retorno deverá ter seu tipo declarado de maneira explícita. Veja abaixo uma tabela com as equivalências de tipos.

| Pseudo código       | Java         |
|---                  |---           |
| int                 | long         |
| float               | double       |
| character           | char         |
| string              | String       |

A parte inicial de todo algoritmo descreve seu nome, propósito, entradas e saídas. Veja abaixo um algoritmo que recebe dois inteiros e devolve sua soma. Note que declaramos os tipos das variáveis em **Input** e o tipo da saída em **Output** e que descrevemos em **Result** o que o algoritmo faz.  

::: side-by-side :::
\begin{algorithm}[H]
\DontPrintSemicolon
\SetAlgoLined
\KwResult{Soma as variáveis $a$ e $b$}
\SetKwInOut{Input}{Input}\SetKwInOut{Output}{Output}
\Input{int $a$, int $b$}
\Output{int}
\BlankLine
$\textbf{int } c \gets a + b$\;
\Return{c}\;
\caption{Exemplo1}
\end{algorithm} 

```java
public static long Exemplo1(long a, long b) {
  long c = a + b;
  return c;
}
```
:::

::: warn :::
**Cuidado!** Misturar tipos é complicado!

1. Divisão de **int** resultará sempre em um **int** (como a operação **//** em *Python*).
2. Operações que misturam **int** e **float** fazem conversão para **float**.
:::

## Condicionais e Loops

Indentação representa o conteúdo de um loop ou condicional. Para facilitar, estamos usando a linha vertical para indicar onde cada bloco acaba. Veja abaixo.


::: side-by-side :::
\begin{algorithm}[H]
\DontPrintSemicolon
\SetAlgoLined
\KwResult{Soma as variáveis $a$ e $b$}
\SetKwInOut{Input}{Input}\SetKwInOut{Output}{Output}
\Input{int $i$, int $n$}
\Output{int}
\BlankLine
$\textbf{int } total \gets 0$\;
\While{$i < n$}{
  \uIf{$i \% 2 = 0$}{
    ...\;
  } \Else {
    ....2\;
  }
  $i \gets i + 1$\;
}
\Return{total}\;
\caption{Exemplo2}
\end{algorithm} 

```java
public static long Exemplo2(long a, long b) {
  long c = a + b;
  return c;
}
```
:::
## Arrays

## Strings
