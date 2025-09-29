
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

::: warn :::
**Atenção**

1. Divisão de **int** resultará sempre em um **int** (como a operação **//** em *Python*).
2. Operações que misturam **int** e **float** fazem conversão para **float**.
:::

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


## Condicionais e Loops

Indentação representa o conteúdo de um loop ou condicional. Para facilitar, estamos usando a linha vertical para indicar onde cada bloco acaba. Veja abaixo.


::: side-by-side :::
\begin{algorithm}[H]
\DontPrintSemicolon
\SetAlgoLined
\KwResult{Calcula $\sum_{i}^{n} 2^i (-1)^i$ }
\SetKwInOut{Input}{Input}\SetKwInOut{Output}{Output}
\Input{int $i$, int $n$}
\Output{int}
\BlankLine
$\textbf{int } total \gets 0$\;
$\textbf{int } temp \gets 2^i$\;
\While{$i <= n$}{
  \uIf{$i \% 2 = 0$}{
    $total \gets total + temp$\;
  } \Else {
    $total \gets total - temp$\;
  }
  $i \gets i + 1$\;
  $temp \gets temp \times 2$\;
}
\Return{total}\;
\caption{Exemplo2}
\end{algorithm} 

```java
public static long Exemplo2(long i, long n) {
  long total = 0;
  long temp = Math.pow(2, i);
  
  while (i <= n) {
    if (i % 2 == 0) {
      total += temp;
    } else {
      total -= temp;      
    }
    i++;
    temp *= 2;
  }
  return total;
}
```
:::

[break]

Loops `for` serão sempre **exclusivos** em nossos algoritmos. Veja o trecho abaixo.


::: side-by-side :::
\begin{algorithm}[H]
\DontPrintSemicolon
\For{$\textbf{int } i \gets 5 \textbf{ to } 10$}{
  ....\;
}
\caption{Exemplo de for}
\end{algorithm} 

```java
// exemplo de for
for (long i = 5; i < 10; i++) {
  ...
}
```
:::

## Arrays

Um *Array* `A` é um tipo composto de um número **fixo** de elementos, todos do mesmo tipo. Usamos `A.length` para representar seu tamanho. O primeiro elemento tem índice `0` e o elemento `i` é acessado com `A[i]`. Veja um exemplo de uso abaixo.


::: side-by-side :::
\begin{algorithm}[H]
\DontPrintSemicolon
\SetAlgoLined
\KwResult{Calcula média de um array }
\SetKwInOut{Input}{Input}\SetKwInOut{Output}{Output}
\Input{array float $A$}
\Output{float}
\BlankLine
$\textbf{float } total \gets 0$\;
\For{$i = 0 \textbf{ to } A.length$}{
  $total \gets total + A[i]$\;
}
\Return{total / A.length}\;
\caption{Exemplo2}
\end{algorithm} 

```java
public static double Exemplo2(double[] A) {
  double total = 0;
  for (long i = 0; i < A.length; i++) {
    total += A[i];
  }
  return total / A.length;
}
```
:::


## Strings

Java tem muitas funções de conveniência com Strings. Neste disciplina iremos tratá-las como um array do tipo especial `char`, que representa um único caractere. Veja abaixo como passar por todos os caracteres de uma `String` (em Java).


::: side-by-side :::
\begin{algorithm}[H]
\DontPrintSemicolon
$\textbf{string } S = ....$\;
\For{$\textbf{int } i \gets 0 \textbf{ to } S.length$}{
  $\text{Faz algo com } S[i]$ \;
}
\caption{Acesso aos carateres de uma string}
\end{algorithm} 

```java
String S = ....;
for (int i = 0; i < S.length(); i++) {
  // faz algo com
  S.charAt(i);
}
```
:::


::: warn :::
**Cuidado com `char` em Java**

- `'a'` representa um único caractere (tipo `char`)
- `"a"` representa uma string de tamanho 1 (tipo `String`)

Essas duas coisas são diferentes em Java e costumam dar erros de compilação complicados. 
:::

## Referências

Todo array é recebido *por referência* em um algoritmo. Ou seja, o comportamento padrão é que modificar elementos de um array recebido como parâmetro em um algoritmo modifica também o array "original" passado.

Strings são sempre imutáveis. Ou seja, não é possível fazer uma atribuição e modificar o caractere no índice *i*. 

::: warn :::
**Um valor para "vazio"**

O valor especial `NIL` representa a ideia de *vazio* ou *inválido*. Ele pode ser usado tanto para *string* quanto para *array*s. Em Java, ele é representado pela constante `null`.

::: 
