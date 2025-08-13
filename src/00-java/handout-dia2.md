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

## Entregador mais próximo

\begin{algorithm}[H]
\DontPrintSemicolon
\SetAlgoLined
\KwResult{Encontra o índice $(x_i, y_i)$ mais perto do ponto $o$}
\SetKwInOut{Input}{Input}\SetKwInOut{Output}{Output}
\Input{array float $x$, array float $y$, float $o_x$, float $o_y$}
\Output{int}
\BlankLine

$\textbf{int } mprox \gets 0$\;
$\textbf{float } dist\_mprox \gets = \sqrt{(x_0 - o_x)^2 + (y_0 - o_y)^2}$\;
\BlankLine
\For{$i \gets 1 \textbf{ to } x.length$}{
    $\textbf{float }d = \sqrt{(x_i - o_x)^2 + (y_i - o_y)^2}$\;
    \If{$d < dist\_mprox$}{
        $dist\_mprox \gets d$\;
        $mprox \gets i$\;
    }        
}
\Return{$mprox$}
\caption{Entregador mais próximo}
\end{algorithm} 

**Entrada 1**: $b=3, h=5$

[spacer]

**Entrada 2**: $b=9.5, h=4$

[spacer]

**Entrada 3**: $b=3, h=5.8$


[break]

## Diferença de listas

\begin{algorithm}[H]
\DontPrintSemicolon
\SetAlgoLined
\KwResult{Cria nova lista com diferença entre $A_1$ e $A_2$}
\SetKwInOut{Input}{Input}\SetKwInOut{Output}{Output}
\Input{array $A_1$, array $A_2$}
\Output{array $A_3$}
\BlankLine

$count \gets 0$\;
\For{$i \gets 0 \textbf{ to } A_1.length$}{
    $emA_2 \gets \textbf{false}$\;
    \For{$f \gets 0 \textbf{ to } A_2.length$}{
        \If{$A_1[i] = A_2[j]$}{
            $emA_2 \gets \textbf{true}$\;
        }
    }
    \If{$emA_2 = \textbf{false}$}{
        $count \gets count + 1$\;
    }
}
\BlankLine
$A_3 = \textbf{novo array}(count)$\;
$count \gets 0$\;
\For{$i \gets 0 \textbf{ to } A_1.length$}{
    $emA_2 \gets \textbf{false}$\;
    \For{$f \gets 0 \textbf{ to } A_2.length$}{
        \If{$A_1[i] = A_2[j]$}{
            $emA_2 \gets \textbf{true}$\;
        }
    }
    \If{$emA_2 = \textbf{false}$}{
        $A_3[count] = A_1[i]$\;
        $count \gets count + 1$\;
    }
}
\Return{$A_3$}
\caption{DiffListas}
\end{algorithm} 

**Entrada 1**: $V=\sqrt{9.8}, \theta=\pi/6, Y_0=1$

[spacer]

**Entrada 2**: $V=20, \theta=\pi/4, Y_0=1$


## Valor da nota

\begin{algorithm}[H]
\DontPrintSemicolon
\SetAlgoLined
\KwResult{Valor da Nota}
\SetKwInOut{Input}{Input}\SetKwInOut{Output}{Output}
\Input{array float $P$, array float $Q$}
\Output{float}
\BlankLine

$total \gets 0$\;
\For{$i \gets 0 \textbf{ to } P.length$}{
    $total \gets total + P[i] * Q[i]$\;
}
\Return{$total$}
\caption{ValorNota}
\end{algorithm} 

**Entrada 1**: $N=7$

[spacer]

**Entrada 2**: $N=22$

[spacer]

**Entrada 3**: $N=150$

[break]

-------------------------------

## Palavras iguais

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


## Conta Celulares

\begin{algorithm}[H]
\DontPrintSemicolon
\SetAlgoLined
\KwResult{Conta quantos algarismos "1" existem em um número.}
\SetKwInOut{Input}{Input}\SetKwInOut{Output}{Output}
\Input{int $N$}
\Output{int}
\BlankLine
CELULARES(T)
    COUNT_CELULARES := 0

    PARA CADA ITEM EM T FAÇA
        DIGITO1 := VAZIO
        SE TAMANHO(ITEM) = 14 ENTÃO
            DIGITO1 := ITEM[5]
            SE DIGITO1 = "9" ENTÃO
                COUNT_CELULARES := COUNT_CELULARES + 1
            FIM
        FIM
        SE TAMANHO(ITEM) = 11 ENTÃO
            DIGITO1 := ITEM[2]
            SE DIGITO1 = "9" ENTÃO
                COUNT_CELULARES := COUNT_CELULARES + 1
            FIM
        FIM

        SE TAMANHO(ITEM) = 9 ENTÃO
            DIGITO1 := ITEM[0]
            SE DIGITO1 = "9" ENTÃO
                COUNT_CELULARES := COUNT_CELULARES + 1
            FIM
        FIM
    FIM
\caption{ContaCelulares}
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





