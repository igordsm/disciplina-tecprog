---
title: Condicionais e Loops
subtitle: Técnicas de Programação
author: Igor Montagner
...

::: tip :::
Para cada algoritmo abaixo:

1. leia o pseudo código
2. simule seu funcionamento usando as entradas de exemplo
3. confira o resultado usando os testes no exercício do PrairieLearn
4. use o *CheatSheet* para converter o pseudo código para Java
:::

## Área do triângulo

\begin{algorithm}[H]
\DontPrintSemicolon
\SetAlgoLined
\KwResult{Calcula área do Triângulo}
\SetKwInOut{Input}{Input}\SetKwInOut{Output}{Output}
\Input{float $b$, float $h$}
\Output{float}
\BlankLine
\Return{$\frac{b \times h}{2}$}\;
\caption{AreaTriangulo}
\end{algorithm} 

**Entrada 1**: $b=3, h=5$

[spacer]

**Entrada 2**: $b=9.5, h=4$

[spacer]

**Entrada 3**: $b=3, h=5.8$


[break]

## Lançamento de projétil

\begin{algorithm}[H]
\DontPrintSemicolon
\SetAlgoLined
\KwResult{Determina distância do lançamento de um projétil}
\SetKwInOut{Input}{Input}\SetKwInOut{Output}{Output}
\Input{float $V$, float $\theta$, float $Y_0$}
\Output{float}
\BlankLine

$G \gets 9.8$\;
$p_1 \gets \frac{V^2}{2G}$\;
\BlankLine
$seno\theta \gets \sin(\theta)$\;
$p2_1 \gets \frac{2 G Y_0}{V^2 * seno\theta^2}$\;
$p2_2 \gets 1 + \sqrt{1 + p2_1)}$\;
\BlankLine
$p3 \gets \sin(2 \theta)$\;
\Return{$p1 * p2 * p3$}\;

\caption{DistanciaLancamento}
\end{algorithm} 

**Entrada 1**: $V=\sqrt{9.8}, \theta=\pi/6, Y_0=1$

[spacer]

**Entrada 2**: $V=20, \theta=\pi/4, Y_0=1$

[spacer]

**Entrada 3**: $V=30, \theta=\pi/3, Y_0=1$

[break]

## FizzBuzz 

\begin{algorithm}[H]
\DontPrintSemicolon
\SetAlgoLined
\KwResult{FizzBuzz}
\SetKwInOut{Input}{Input}\SetKwInOut{Output}{Output}
\Input{int $N$}
\Output{string}
\BlankLine

\If{$N \% 2 = 0 \textbf{ and } N \% 3 \neq 0$}{
       \Return{"Ins"}\;
}
\If{$N \% 2 \neq 0 \textbf{ and } N \% 3 = 0$}{
       \Return{"per"}\;
}
\If{$N \% 2 = 0 \textbf{ and } N \% 3 = 0$}{
       \Return{"Insper"}\;
}
\Return{""}
\caption{Divisibilidade}
\end{algorithm} 

**Entrada 1**: $N=7$

[spacer]

**Entrada 2**: $N=22$

[spacer]

**Entrada 3**: $N=150$

[break]


## Jaca Wars

\begin{algorithm}[H]
\DontPrintSemicolon
\SetAlgoLined
\KwResult{Verifica se a jaca lançada acertou.}
\SetKwInOut{Input}{Input}\SetKwInOut{Output}{Output}
\Input{float $V$, float $\theta$}
\Output{string}
\BlankLine

$G \gets 9.8$\;
$\theta \gets \theta * \pi / 180$\;
$dist \gets \frac{V^2 * \sin(2\theta)}{G}$\;

\If{$dist < 98$}{\Return{"Muito perto"}}
\If{$dist > 102$}{\Return{"Muito longe"}}

\Return{"Acertou"}
\caption{JacaWars}
\end{algorithm} 

**Entrada 1**: $V=40, \theta=15^o$

[spacer]

**Entrada 2**: $V=40, \theta=40^o$

[spacer]

**Entrada 3**: $V=31.5, \theta=45^o$

[break]


## Quantos Uns

\begin{algorithm}[H]
\DontPrintSemicolon
\SetAlgoLined
\KwResult{Conta quantos algarismos "1" existem em um número.}
\SetKwInOut{Input}{Input}\SetKwInOut{Output}{Output}
\Input{int $N$}
\Output{int}
$count \gets 0$\;
\BlankLine
\While{$N > 0$}{
$d \gets N \% 10$\;
\If{d = 1}{
      $count \gets count + 1$\;
}
$N \gets N / 10$\;
}
\Return{$count$}\;
\caption{QuantosUns}
\end{algorithm} 

**Entrada 1**: $N=5$

[spacer]

**Entrada 2**: $N=11$

[spacer]

**Entrada 3**: $N=6531$

[break]

## Estimando valor de $\pi$

\begin{algorithm}[H]
\DontPrintSemicolon
\SetAlgoLined
\KwResult{Calcula o valor de $\pi$ usando uma série.}
\SetKwInOut{Input}{Input}\SetKwInOut{Output}{Output}
\Input{int $N$}
\Output{float}
\BlankLine
$pi^2 = 0$\;
\For{$i \gets 1 \textbf{ to } N+1$}{
	$pi^2 \gets pi^2 + \frac{6}{i^2}$\;
}
\Return{$\sqrt{pi^2}$}
\caption{CalculaPi}
\end{algorithm} 

**Entrada 1**: $N=3$

[spacer]

**Entrada 2**: $N=4$

[spacer]

**Entrada 3**: $N=10$

[break]


## Fatorial

\begin{algorithm}[H]
\DontPrintSemicolon
\SetAlgoLined
\KwResult{Calcula o fatorial de um número}
\SetKwInOut{Input}{Input}\SetKwInOut{Output}{Output}
\Input{int $N$}
\Output{int}
\BlankLine

$res \gets 1$\;
\For{$i \gets 1 \textbf{ to } N+1$}{
	$res \gets res * i$\;
}
\Return{$res$}
\caption{Fatorial}
\end{algorithm} 

**Entrada 1**: $N=4$

[spacer]

**Entrada 2**: $N=5$

[spacer]

**Entrada 3**: $N=8$

[break]





